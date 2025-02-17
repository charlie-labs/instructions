# Web Standard APIs

Always prefer using standard web APIs like `fetch`, `WebSocket`, and `ReadableStream` when possible. Avoid Node.js-specific modules (like `Buffer`) or redundant libraries (like `node-fetch`).

- Prefer the `fetch` API for making HTTP requests instead of Node.js modules like `http` or `https`
  - Use the native `fetch` API instead of `node-fetch` or polyfilled `cross-fetch`
  - Use the `ky` library for HTTP requests instead of `axios` or `superagent`
- Use the WHATWG `URL` and `URLSearchParams` classes instead of the Node.js `url` module
- Use `Request` and `Response` objects from the Fetch API instead of Node.js-specific request and response objects
- Utilize `Blob` and `File` APIs for handling binary data when possible
- Use `TextEncoder` and `TextDecoder` for encoding and decoding text
