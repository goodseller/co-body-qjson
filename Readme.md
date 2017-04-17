
# co-body-qjson
  inspired by [cojs/co-body](https://github.com/cojs/co-body).

## Installation

```bash
$ npm install co-body-qjson
```

## Options

  - `limit` number or string representing the request size limit (1mb for json and 56kb for form-urlencoded)
  - `strict` when set to `true`, JSON parser will only accept arrays and objects; when `false` will accept anything `JSON.parse` accepts. Defaults to `true`. (also `strict` mode will always return object).
  - `queryString` an object of options when parsing query strings and form data. See [qs](https://github.com/hapijs/qs) for more information.
  - `returnRawBody` when set to `true`, the return value of `co-body` will be an object with two properties: `{ parsed: /* parsed value */, raw: /* raw body */}`.
  - `jsonTypes` is used to determine what media type **co-body** will parse as **json**, this option is passed directly to the [type-is](https://github.com/jshttp/type-is) library.
  - `formTypes` is used to determine what media type **co-body** will parse as **form**, this option is passed directly to the [type-is](https://github.com/jshttp/type-is) library.
  - `textTypes` is used to determine what media type **co-body** will parse as **text**, this option is passed directly to the [type-is](https://github.com/jshttp/type-is) library.

more options available via [raw-body](https://github.com/stream-utils/raw-body#getrawbodystream-options-callback):

## Example

```js
// application/qjson
var body = yield parse.qjson(req);

// explicit limit
var body = yield parse.qjson(req, { limit: '10kb' });
```

## Koa

  This lib also supports `ctx.req` in Koa (or other libraries),
  so that you may simply use `this` instead of `this.req`.

```js
// application/qjson
var body = yield parse.qjson(this);
```

# License

  MIT
