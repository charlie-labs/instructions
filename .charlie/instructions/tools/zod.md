# Zod

- Zod should be used to parse untrusted data, but not for data that is trusted like function arguments
- Zod unions should always be used instead of enums
  - For example, this union `z.union([z.literal('youtube'), z.literal('spotify')])` is better than this enum `z.enum(['youtube', 'spotify'])`