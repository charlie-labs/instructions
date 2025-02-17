# Packages

All packages must follow these `package.json` rules:

- `type` must be set to `module`
- `exports` should be used instead of `main` or `module`
  - ALL source code should be exported from the root (`.`) path
  - Any test-specific code should be exported from a `test` path
  - Exports should use the `.ts` extension
  - Good example:
    - `"exports": "./src/index.ts"`
    - `"exports": { ".": "./src/index.ts", "./test": "./src/test/index.ts" }`
  - BAD example:
    - `"main": "./src/index.ts"` (don't use `main` or `module`)
    - `"exports": "./src/index.js"` (don't use `.js` for exports)
    - `"exports": { ".": "./src/index.ts", "./test": "./src/test/index.ts", "./test/mocks": "./src/test/mocks.ts" }` (don't export multiple paths: "./test" and "./test/mocks")
- `types` should be used instead of `typings`
- NEVER use TypeScript path resolution (`paths` in `tsconfig.json`)
  - Use ESM subpath imports instead if this is desired (eg: `"imports": { "#/ui": "./ui/index.ts" }`)


# Directory Structure

All packages must be placed in `packages/<package-name>/`. Each package should have the following:

- A `src/` directory containing the core source code.
- A single entrypoint in `src/index.ts` that exports the package's public API.
- Place test helpers, utilities, or mocks in `src/test/` with a single entrypoint in `src/test/index.ts`.
- Tests should be placed beside source code like `src/my-file.ts` and `src/my-file.test.ts` (NOT `src/test/my-file.test.ts` or `test/my-file.test.ts`).
- A standard set of config files (like `package.json` and `tsconfig.json`) to ensure consistency.
- The `package.json` must define an "exports" object with `"." : "./src/index.ts"` and optionally `"./test": "./src/test/index.ts"`, ensuring clearly defined entrypoints for production and test.

Example:

```
packages/foo/package.json
packages/foo/tsconfig.json
packages/foo/src/index.ts
packages/foo/src/bar.ts
packages/foo/src/bar.test.ts
packages/foo/test/index.ts
packages/foo/test/setup.ts
```
