# Models

```js
import { Model, snakeCaseMappers } from 'objection';
import db from '../index';

Model.knex(db);

class Anime extends Model {
  id: number;
  name: string;
  rating: number;
  userId: number;

  static tableName = 'anime';
  static columnNameMappers = snakeCaseMappers();
}

export default Anime;
```
