## Comments

Comments should be used to document and explain code. They should complement the use of descriptive variable and function names and type declarations.

- Add comments to explain complex sections of code
- Add comments that will improve the autocompletion preview in IDEs (eg: functions and types)
- Don't add comments that just reword symbol names or repeat type declarations

### Comment Format

- Use **JSDoc** formatting for comments (not TSDoc or inline comments)
- Common JSDoc tags to use:
  - `@param`: define a parameter on a function
  - `@returns`: define the return type of a function
  - `@throws`: define an exception that can be thrown by a function
  - `@example`: provide an example of how to use a function or class
  - `@deprecated`: mark a function or class as deprecated
  - `@see`: define an external reference related to the symbol
  - `{@link}`: create a link to the namepath or URL
  - `@TODO`: mark a task that needs to be completed
- **DO NOT** use the following tags: `@file`, `@async`