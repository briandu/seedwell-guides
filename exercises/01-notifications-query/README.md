# Querying for notifications

This exercise is to learn the steps to creating a `notifications` table and the query that can be accessed from front-end application.

## Acceptance Criteria

* `notifications` migration with the following fields:
  * `id` as `number`
  * `name` as `string`
  * `message` as `string`
  * `created_at` as `timestamp`
  * `update_at` as `timestamp`

* `notifications` model
* `notifications` schema for the resolver and type definitions
* Add 3 notifications with the details of your choice
* `getNotifcations` query that returns all the notifications

## Notes

* go to http://localhost:8000/api/v1/graphql to test queries
* don't forget to import `typeDef` and `resolver` to `api/src/services/graphql/graphql.server.ts`

## References

* [`seedwell-guides/guides/knex-migrations`](https://github.com/briandu/seedwell-guides/tree/master/guides/knex-migrations/README.md)
* [`seedwell-guides/guides/queries`](https://github.com/briandu/seedwell-guides/tree/master/guides/queries/README.md)
* [`seedwell-guides/guides/models`](https://github.com/briandu/seedwell-guides/tree/master/guides/models/README.md)

