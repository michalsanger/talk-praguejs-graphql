autoscale: true

# GraphQL gifts from Kiwi.com

### Michal Sänger

### `michal.sanger@kiwi.com`

^
Hello everyone...

---

# ESLint & Babel preset

- Consistent codebase
- Faster code reviews
- Modern JS features

---

# ESlint

`yarn add --dev @kiwicom/eslint-config`

- React, RN, Hooks, Relay
- Prettier, Jest
- Flow, Node
- extendable

---

# ESlint

```js
//.eslintrc.js
module.exports = {
  root: true,
  extends: [
    '@kiwicom/eslint-config',
  ],
};
```

---

# Do not ignore ESLint warnings!

```js
//.eslintrc.js
module.exports = {
  root: true,
  extends: [
    '@kiwicom/eslint-config/strict',
  ],
};
```
---

# Babel Preset

`yarn add --dev @kiwicom/babel-preset-kiwicom`

- Flow, JSX
- class properties
- Relay fragments
- Sugar: `a?.b; a ?? b; {...a}`

---

# Fetch

`yarn add @kiwicom/fetch`

- Retries
- Timeouts
- Error handling

---

# Fetch

```js
import fetchWithRetries from '@kiwicom/fetch';

fetchWithRetries(
  'https://example.api',
  {
    fetchTimeout: 15000,
    retryDelays: [1000, 3000],
    // ... standard Fetch options
  },
);

```

---

# Fetch

```js
import fetchWithRetries, { TimeoutError, ResponseError } from '@kiwicom/fetch';

try {
  const response = await fetchWithRetries('//localhost');
} catch (error) {
  if (error instanceof TimeoutError) {
    console.error('request timeouted');
  } else if (error instanceof ResponseError) {
    console.error('unsuccessful response', error.response);
  } else {
    console.error('unknown error');
  }
}
```

---

# Logz

`yarn add @kiwicom/graphql-logz`

- Apollo Engine alternative
- Logz.io backend & UI
- GraphQL Query, Variables
- Deprecated fields
- Duration, Headers,

---

![fit](images/graphql-logz01.png)

---

![fit](images/graphql-logz02.png)

---

# BC Checker

`yarn add --dev @kiwicom/graphql-bc-checker`

- Auto update schema snapshot
- Create BC changelog
- Fits into test pipeline
- DX focus

---

# BC Checker

```js
// scripts/test-bc.js
import path from 'path';
import testBC from '@kiwicom/graphql-bc-checker';

import Schema from './src/Schema';

testBC({
  allowBreakingChanges: false,
  snapshotLocation: path.join(__dirname, 'schema-snapshot.graphql'),
  schema: Schema,
});
```

---

# BC Checker DX

```
VALUE_REMOVED_FROM_ENUM - FUTURE was removed from enum type AllBookingsOnlyEnum.
VALUE_REMOVED_FROM_ENUM - PAST was removed from enum type AllBookingsOnlyEnum.

Tips how to avoid breaking changes:

- field removal/modification (introduce new field and only deprecate the old one)
- type removal/modification (just deprecate it and leave it there)
- removal from enum/union (introduce new enum/union)
- arguments removal/modification (introduce new query or graph node)
- change non-nullable -> nullable (just don't do it or introduce new field)
- change of default argument value (don't or introduce new argument/query)

error Command failed with exit code 1.
```

---

# Relay

`yarn add react @kiwicom/relay`

- Relay wrapper
- query logging during development
- response cache, batch requests
- uploadables, persistent queries
- flow

---

![inline](images/relay-logger.png)

---

# Relay example

`github.com/kiwicom/relay-example`

- HOW TO `@kiwicom/relay`
- simple fetching
- Endless pagination
- bi-directional pagination

---

![fit](images/relay-example.png)

---

# Margarita

`github.com/kiwicom/margarita`

- GraphQL, Relay
- Shareable UI, RN & RNW
- Kiwi.com Tequila API

---

![fit](images/margarita-demo.mov)

---

# Share your :heart:

![inline 150%](images/stars.png)
![inline 150%](images/issues.png)
![inline 150%](images/pull-requests.png)

---

# Links

- [npmjs.com/package/@kiwicom/eslint-config](https://www.npmjs.com/package/@kiwicom/eslint-config)
- [npmjs.com/package/@kiwicom/babel-preset-kiwicom](https://www.npmjs.com/package/@kiwicom/babel-preset-kiwicom)
- [npmjs.com/package/@kiwicom/fetch](https://www.npmjs.com/package/@kiwicom/fetch)
- [npmjs.com/package/@kiwicom/graphql-logz](https://www.npmjs.com/package/@kiwicom/graphql-logz)
- [npmjs.com/package/@kiwicom/graphql-bc-checker](https://www.npmjs.com/package/@kiwicom/graphql-bc-checker)
- [npmjs.com/package/@kiwicom/relay](https://www.npmjs.com/package/@kiwicom/relay)
- [github.com/kiwicom/relay-example](https://github.com/kiwicom/relay-example)
- [github.com/kiwicom/margarita](https://github.com/kiwicom/margarita)

---

# There is more

- [npmjs.com/package/@kiwicom/monorepo](https://www.npmjs.com/package/@kiwicom/monorepo)
- [npmjs.com/package/@kiwicom/npm-publisher](https://www.npmjs.com/package/@kiwicom/npm-publisher)
- [npmjs.com/package/@kiwicom/test-utils](https://www.npmjs.com/package/@kiwicom/test-utils)
- [npmjs.com/package/@kiwicom/js](https://www.npmjs.com/package/@kiwicom/js)
- [npmjs.com/package/@kiwicom/graphql-utils](https://www.npmjs.com/package/@kiwicom/graphql-utils)

---

# Thank you!
