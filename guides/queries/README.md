# Queries 

```js
import { gql } from 'apollo-server-express';
import { GraphqlContext } from 'types/graphql.types';
import Anime from 'db/models/anime.model';

export const typeDefs = gql`
  type Anime {
    id: Int
    name: String
    rating: Int
    userId: Int
  }

  extend type Query {
    getAnime: [Anime]
  }
`;

export const resolvers = {
  Query: {
    getAnime: async (
      _parent: any,
      _arg: any,
      { actor }: GraphqlContext
    ) => Anime.query()
      .where({ user_id: actor.id }),
  },
};

export default {
  typeDefs,
  resolvers,
};
```
