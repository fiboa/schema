# fiboa Schema

As fiboa is targeting multiple encodings, there's no single solution for validation.
We must define our own validation vocabulary, based on the fiboa Schema [data types](datatypes.md).
Nevertheless, fiboa Schema can be translated into JSON Schema.

- Schema identifier: `https://fiboa.github.io/schema/v0.1.0/schema.json`
- [Metaschema](https://fiboa.github.io/schema/v0.1.0/schema.json) (as JSON Schema)

The following keyword is generally supported:

- `type`: The [fiboa data types](datatypes.md) as a string, **required**.

Additionally, the following validation vocabulary is defined by JSON Schema:

For strings:

- `format` (values: `email`, `idn-email`, `iri`, `uri`, `uuid`)
- `pattern`
- `minLength`
- `maxLength`
- `enum`

For numerical data types:

- `minimum`
- `maximum`
- `exclusiveMinimum`
- `exclusiveMaximum`
- `enum` (for integer data types only)

For arrays:

- `items` (required, object only, sub-schema must be compliant to fiboa Schema)
- `minItems`
- `maxItems`
- `uniqueItems`

For objects:

- `required`
- `properties` (required, sub-schemas must be compliant to fiboa Schema)
- `additionalProperties`
  (Note: In objects additional properties are disallowed by default, i.e. the default value is `false`.
  In JSON Schema the default value is `true`.)