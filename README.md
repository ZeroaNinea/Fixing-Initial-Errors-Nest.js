# Fixing Initial Errors in Nest.js

This project shows how to create a Nest.js project properly by fixing all initial errors.

## Fixing `tsconfig.json`

Replce the `baseUrl` property with the `rootDir`. `baseUrl` is deprecated, and it will be removed in TypeScript 7.0.

```json
{
  // "baseUrl": "./",
  "rootDir": "./src"
}
```
