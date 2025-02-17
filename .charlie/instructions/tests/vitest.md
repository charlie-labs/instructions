### Unit Testing

- **All unit tests should [Vitest](https://vitest.dev/)**
  - DO NOT attempt to install or use other testing libraries like Jest
- Write unit tests for individual components and utility functions
- Test files should be named `[target].test.ts` and placed in the same directory as the code they are testing (NOT a separate directory)
  - Good example: `src/my-file.ts` and `src/my-file.test.ts`
  - Bad example: `src/my-file.ts` and `src/test/my-file.test.ts` or `test/my-file.test.ts` or `src/__tests__/my-file.test.ts`
- Tests should be run with `bun run test` (you can't do just `bun test`)
- It's acceptable to use `any`/`unknown` in test files (such as `*.test.ts`) or test fixtures (like `**/test-data.ts`) to facilitate mocking or stubbing external modules or partial function arguments, referencing the usage guidelines in the TypeScript section. However, do not use `any` or `unknown` in production code.
