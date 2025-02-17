
## Bun

Server-side code is written using Bun. Use native Bun (and the Node APIs it supports) when possible.

- Use standard lib modules like `Bun.file`, `$` shell commands, `Glob`, etc
- Prefer standard lib modules over third-party alternatives
- Utilize the `node:` protocol when importing Node.js modules (e.g., `import fs from 'node:fs/promises'`)
- Prefer the promise-based APIs over Node's legacy sync methods
- Use `Error` objects for operational errors, and consider extending `BaseError` for specific error types
- Use environment variables for configuration and secrets (avoid hardcoding sensitive information)
