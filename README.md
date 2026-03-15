# Fixing Initial Errors in Nest.js

This project shows how to create a Nest.js project properly by fixing all initial errors.

## Fixing `tsconfig.json`

Replce the `baseUrl` property with the `rootDir`. `baseUrl` is deprecated, and it will be removed in TypeScript 7.0.

```json
{
  "compilerOptions": {
    // "baseUrl": "./",
    "rootDir": "./src"
  }
}
```

Add the `types` property to the `compilerOptions` object to allow VS Code to recognize Jest test files.

```json
{
  "compilerOptions": {
    "types": ["node", "jest"]
  }
}
```

## Fixing `eslint.config.mjs`

Replace `tseslint.config` with `defineConfig` imported from `eslint/config`. `tseslint.config` is deprecated.

```mjs
import {defineConfig} from 'eslint/config';

export default defineConfig(...);
```

## Fixing `main.ts`

Await the `bootstrap` function instead of calling it synchronously. Replace this:

```ts
bootstrap();
```

With this:

```ts
bootstrap()
  .then(() =>
    console.log(` 🚀 Server started on the port ${process.env.PORT ?? 3000}`),
  )
  .catch((err) => console.error(err));
```

## Medium Link

[https://medium.com/@heghine.dev357/fixing-common-initial-errors-in-a-nest-js-project-d9683c31e04c](https://medium.com/@heghine.dev357/fixing-common-initial-errors-in-a-nest-js-project-d9683c31e04c)
