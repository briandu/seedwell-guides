# Standard Component Style

### Create new component

Most general components would be created in `app/src/components`. The files would usually consider of the following 2-3 files:

#### 1. `index.tsx`

```jsx
import React from 'react';
import { useQuery } from '@apollo/client';

import { GET_DATA } from './data.graphql';
import {
  Heading,
  Paragraph
} from './styles';

const Component = () => {
  const { data, loading } = useQuery(GET_DATA);

  if (loading) return null;

  const { data } = data;

  return (
    <div>
      <Heading>Heading</Heading>
      <Paragraph>Some text</Paragraph>
    </div>
  );
};

export default Component;
```

#### 2. `styles.tsx`

```js
import styled from 'styled-components/macro';

import { color, general } from 'variables';

export const Heading = styled.h1`
  margin-bottom: 1.5em;
  color: ${color.brandPurple};
`;

export const Paragraph = styled.p`
  color: ${color.brandPink};
`;
```

#### 3. `data.graphql.ts` (Optional)

> Obviously, if nothing from the database is used, we wouldn't need this file.

```js
import { gql } from '@apollo/client';

export const GET_DATA = gql`
  query {
    getData {
      id
    }
  }
`;
```




