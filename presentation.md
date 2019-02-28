build-lists: true

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

---

# Babel Preset

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

# JS & Test utils?

---

# Schema BC Checker

---

# GraphQL utils ?

---

# Relay

---

# Relay example

---

# Margarita
