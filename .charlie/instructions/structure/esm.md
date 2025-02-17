### Imports & Exports

- Always use ESM `import` and `export` (never use CJS `require`)
  - File imports should end with `.js` (NOT `.ts` or `.tsx`). Module or subpath imports don't need the extension.
  - GOOD examples:
    - `import { Foo } from './foo.js';`
    - `import { type Route } from './+types/root.js';`
    - `import zod from 'zod';`
    - `import { logger } from '@dx/core-utils';`
  - BAD examples:
    - `import { Foo } from './foo';` (missing `.js` extension)
    - `import { type Route } from './+types/root';` (missing `.js` extension)
    - `import { Foo } from './foo.ts';` (should be `.js` not `.ts`)
    - `import { AnInternalClass } from 'zod/dist/internals';` (shouldn't import internals)
    - `import { logger } from '@dx/core-utils/src/logger.js';` (shouldn't import source files or use `.js` for packages)
- Always prefer named exports over default exports
  - It's OK to use a default export in `.tsx` files (like Remix/React Router routes)
  - It's OK to use default exports in the CLI because it is required by oclif
