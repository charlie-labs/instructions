
# TypeScript

- Prefer `const` over `let` (never use `var`)
- NEVER use `any`/`unknown` or cast values like `(value as any)` or `value!` in TypeScript outside of test files e.g. `*.test.ts` or test fixtures e.g. `**/test-data.ts`.
- Don't rely on `typeof`, `ReturnType<>`, `Awaited<>`, etc for complex type inference (it's ok for simple types)
- Use `as const` for better type inference
- Use type guards to narrow types in conditional blocks
- Create custom types for complex data structures used throughout the application
- Utilize TypeScript's utility types (e.g., `Partial`, `Pick`, `Omit`) to manipulate existing types
- Never use `React.FC`. Use a function declaration instead
- Functions should accept an object parameter (like `args` or `props`) instead of multiple parameters
  - Good examples:
    ```ts
    function myFunction(args: { foo: boolean; bar: string }) {}
    function VideoPlayer(props: { sid: string }) {}
    ```
  - Bad examples:
    ```ts
    function myFunction(foo: boolean, bar: string, baz: number) {}
    ```
- Arguments should be destructured in the function body, not the function definition. It's ok for React components to destructure props in the function definition.
  - Good example:
    ```ts
    function myFunction(args: { foo: boolean; bar: string }) {
      const { foo, bar } = args;
    }
    ```
  - Bad example:
    ```ts
    function myFunction({ foo, bar }: { foo: boolean; bar: string });
    ```

- Promises (and `async` functions which implicitly create Promises) must always be properly handled, either via:
  - Using `await` to wait for the Promise to resolve successfully
  - Using `.then` or `.catch` to handle Promise resolution
  - Returning a Promise to a calling function which itself has to handle the Promise. If you can't infer this from the available context, add a warning that the promise may not be handled properly.
