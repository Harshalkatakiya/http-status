# @harshalkatakiya/http-status

A comprehensive collection of HTTP status codes and their standard phrases.

## Features

- 🚀 **Comprehensive**: Includes a wide range of HTTP status codes and phrases.
- 📘 **TypeScript Support**: Written in TypeScript with full type definitions.
- 📚 **Documentation**: Includes JSDoc comments with links to official RFC documentation for each status code.
- 📦 **Zero Dependencies**: Lightweight and easy to include in any project.
- 🔄 **Dual Export**: Access codes and phrases separately or together.

## Installation

You can install this package using your preferred package manager:

```bash
# npm
npm install @harshalkatakiya/http-status

# yarn
yarn add @harshalkatakiya/http-status

# pnpm
pnpm add @harshalkatakiya/http-status

# bun
bun add @harshalkatakiya/http-status
```

## Usage

### Importing Codes

You can import HTTP status codes directly:

```typescript
import { Codes } from "@harshalkatakiya/http-status";

console.log(Codes.OK); // 200
console.log(Codes.NOT_FOUND); // 404
console.log(Codes.INTERNAL_SERVER_ERROR); // 500

// Use in your response handling
if (response.status === Codes.UNAUTHORIZED) {
  // Handle unauthorized access
}
```

### Importing Phrases

You can also import the standard phrases associated with each status code:

```typescript
import { Phrases } from "@harshalkatakiya/http-status";

console.log(Phrases.OK); // "OK"
console.log(Phrases.NOT_FOUND); // "Not Found"
console.log(Phrases.INTERNAL_SERVER_ERROR); // "Internal Server Error"

// Send a response with a standard message
res.status(404).send(Phrases.NOT_FOUND);
```

### Using Both

You can use both codes and phrases together for clear and readable code:

```typescript
import { Codes, Phrases } from "@harshalkatakiya/http-status";

app.get("/", (req, res) => {
  res.status(Codes.OK).send(Phrases.OK);
});

app.post("/create", (req, res) => {
  // ... creation logic
  res.status(Codes.CREATED).send({ message: Phrases.CREATED });
});
```

### Direct Imports

You can also import specific codes and phrases directly from their subpaths. This is useful for tree-shaking and keeping your bundle size small.

```typescript
import {
  OK,
  NOT_FOUND,
  INTERNAL_SERVER_ERROR,
} from "@harshalkatakiya/http-status/codes";
import {
  OK as OK_PHRASE,
  NOT_FOUND as NOT_FOUND_PHRASE,
} from "@harshalkatakiya/http-status/phrases";

console.log(OK); // 200
console.log(OK_PHRASE); // "OK"

res.status(NOT_FOUND).send(NOT_FOUND_PHRASE);
```

## API Reference

The package exports two main objects: `Codes` and `Phrases`. Both objects share the same keys, representing the HTTP status.

### Common Status Codes

| Key                     | Code | Phrase                |
| ----------------------- | ---- | --------------------- |
| `OK`                    | 200  | OK                    |
| `CREATED`               | 201  | Created               |
| `ACCEPTED`              | 202  | Accepted              |
| `NO_CONTENT`            | 204  | No Content            |
| `MOVED_PERMANENTLY`     | 301  | Moved Permanently     |
| `BAD_REQUEST`           | 400  | Bad Request           |
| `UNAUTHORIZED`          | 401  | Unauthorized          |
| `FORBIDDEN`             | 403  | Forbidden             |
| `NOT_FOUND`             | 404  | Not Found             |
| `METHOD_NOT_ALLOWED`    | 405  | Method Not Allowed    |
| `INTERNAL_SERVER_ERROR` | 500  | Internal Server Error |
| `BAD_GATEWAY`           | 502  | Bad Gateway           |
| `SERVICE_UNAVAILABLE`   | 503  | Service Unavailable   |

_Note: This is not an exhaustive list. The package includes many more standard and non-standard status codes._

## License

This project is licensed under the MIT License.

## Author

### Harshal Katakiya

- Website: [https://github.com/Harshalkatakiya](https://github.com/Harshalkatakiya)
- Email: <katakiyaharshl001@gmail.com>
