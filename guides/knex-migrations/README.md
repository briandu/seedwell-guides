# Knex Migrations

## Migrations

#### Create new migration

``
npx knex migrate:make migration_name --cwd src/db
``

#### Running a single migration

``
npx knex migrate:up migration_name --cwd src/db
``

#### Running all migration

``
npx knex migrate:latest --cwd src/db
``

#### Rollback the last migration

``
npx knex migrate:down --cwd src/db
``

#### Creating table

```js
import * as Knex from "knex";

export async function up(knex: Knex): Promise<any> {
  return knex.schema.createTable("table_name", (table: Knex.TableBuilder) => {
    table.increments();
    table.string("name").notNullable();
    table.string("description").notNullable();
    table
      .integer("user_id")
      .notNullable()
      .references("id")
      .inTable("users");
    knex 
  });
}

export async function down(knex: Knex): Promise<any> {
  return knex.schema.dropTable("table_name");
}
```

**Breakdown**

`table.increments()`

Each new row will automically increment the `id`.

`table.string("name")`

Specifies a new column as well as the data type.

```js
table
  .integer("user_id") // integer data type
  .notNullable() // field can't be `null`
  .references("id") // references the `id` field of...
  .inTable("users"); // the `users` table
```
