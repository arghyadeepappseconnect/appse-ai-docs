---
title: "OpenAI"
slug : /app-integrations/openai/
---

OpenAI provides powerful LLM (large language model) APIs for text generation, embeddings, code completion and more. Integrating OpenAI into appse ai enables you to add natural language understanding, generation, summarization, and semantic search to workflows and agents.


## Set Up Credential

:::info

Before you create a credential for OpenAI using appse ai, make sure your OpenAI account has sufficient tokens to perform the actions disruption-free.

:::

### Required Fields

You’ll be asked to fill in the following details:

| Field             | Description                                      |
|------------------|--------------------------------------------------|
| Connection Name   | A name to help you identify this connection      |
| API Secret Key  | Your personal API Secret key from OpenAI     |


### Step-by-Step Guide

#### 1. Sign In / Create an account in OpenAI

Go to the [OpenAI platform](https://auth.openai.com/log-in) and sign in or sign up.

#### 2. Create API Secret Key

Navigate to **API Keys** in the sidebar and click on the “Create a new secret key” button.

<img src="\img\credentials\openai\api-keys.png" alt="APPSeAI OpenAI api keys" width="700"/>
<br/>

Next, give a name to your key and click on “Create Secret Key”

<img src="\img\credentials\openai\create-secret-key.png" alt="APPSeAI OpenAI Create Secret Key" width="700"/>


#### 3. Copy and store your API key

Once you get your API secret key, paste it in appse ai’s credential form. And click on “save”. Your OpenAI credential should be connected.

<img src="\img\credentials\openai\secret-key.png" alt="APPSeAI OpenAI secret key" width="700"/>

<br/>

:::warning

Make sure you save your **API secret key** somewhere safe, as you **won’t be able to see it again**.

:::
---

## Response Format

The **Response Format** option allows you to define the exact structure of the AI's output. Instead of receiving a plain text response, the model returns a structured JSON object that conforms precisely to the schema you provide.



### Supported Types

The following data types are supported when defining schema fields.

| Type | Description | Example Value |
|---|---|---|
| `string` | A sequence of characters (text) | `"hello"`, `"2024-01-01"` |
| `integer` | A whole number without decimals | `1`, `42` |
| `number` | A numeric value including decimals | `9.99`, `3.14` |
| `boolean` | A binary true or false value | `true`, `false` |
| `object` | A structured group of named fields | `{ "name": "John" }` |
| `array` | An ordered list of items | `["a", "b", "c"]` |
| `enum` | A field restricted to a fixed set of allowed values | `"active"`, `"inactive"` |
| `anyOf` | A field that accepts one of multiple specified types | `string` or `null` |

> **Note:** `anyOf` is supported on individual fields only. The **root-level object of a schema cannot use `anyOf`** as its type.



### Keyword Reference

The following keywords are used to construct a valid schema.

| Keyword | Purpose | Usage |
|---|---|---|
| `type` | Specifies the data type of a field | Required on every field |
| `properties` | Defines the fields within an object | Required inside every `object` |
| `items` | Describes the structure of a single item in a list | Required inside every `array` |
| `enum` | Restricts a field to a predefined list of values | Use when a field has fixed options |
| `required` | Declares which fields must always be present in the response | List every field that is mandatory |
| `additionalProperties: false` | Prevents any fields outside the schema from appearing | Add to every object in your schema |
| `strict: true` | Enforces exact compliance with the defined schema | Always set to `true`, nested inside `json_schema` |
| `name` | A unique identifier for your schema | Use underscores instead of spaces, nested inside `json_schema` |



### Additional Constraints

Beyond the `type` declaration, the following optional constraints allow you to enforce specific rules on field values.

#### String Constraints

| Property | Description | Example |
|---|---|---|
| `pattern` | The value must match the specified regular expression | `"pattern": "^[A-Z]{3}$"` |
| `format` | The value must conform to a predefined format | `"format": "email"` |

**Supported `format` values:**

| Format | Expected Value |
|---|---|
| `date-time` | Full date and time — `"2024-01-15T10:30:00Z"` |
| `date` | Date only — `"2024-01-15"` |
| `time` | Time only — `"10:30:00"` |
| `duration` | A time duration — `"P1Y2M3D"` |
| `email` | A valid email address |
| `hostname` | A valid domain name |
| `ipv4` | A valid IPv4 address |
| `ipv6` | A valid IPv6 address |
| `uuid` | A valid UUID string |

### Number Constraints

| Property | Description | Example |
|---|---|---|
| `minimum` | The value must be greater than or equal to this number | `"minimum": 0` |
| `maximum` | The value must be less than or equal to this number | `"maximum": 100` |
| `exclusiveMinimum` | The value must be strictly greater than this number | `"exclusiveMinimum": 0` |
| `exclusiveMaximum` | The value must be strictly less than this number | `"exclusiveMaximum": 1000` |
| `multipleOf` | The value must be a multiple of this number | `"multipleOf": 5` |

### Array Constraints

| Property | Description | Example |
|---|---|---|
| `minItems` | The array must contain at least this many items | `"minItems": 1` |
| `maxItems` | The array must contain no more than this many items | `"maxItems": 50` |



## Building a Schema — Step by Step

> The schema structure used in this documentation follows the OpenAI Structured Outputs specification. To learn more, visit the official documentation: [Structured model outputs | OpenAI API](https://platform.openai.com/docs/guides/structured-outputs)

The following walkthrough demonstrates how to construct a complete schema from the ground up.

**Reference format (OpenAI Structured Outputs):**

```json
{
  "type": "json_schema",
  "json_schema": {
    "name": "math_response",
    "strict": true,
    "schema": {
      "type": "object",
      "properties": {
        "steps": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "explanation": { "type": "string" },
              "output":      { "type": "string" }
            },
            "required": ["explanation", "output"],
            "additionalProperties": false
          }
        },
        "final_answer": { "type": "string" }
      },
      "required": ["steps", "final_answer"],
      "additionalProperties": false
    }
  }
}
```

> **Key structure points:**
> - `type` is set to `"json_schema"` at the top level.
> - Everything else — `name`, `strict`, and `schema` — is **nested inside the `json_schema` object**.
> - `strict: true` must always be included inside `json_schema`.

Following the same structure, the steps below build a complete product list schema.

**Objective:** Define a schema that returns a list of products, where each product contains the fields: `id`, `name`, `sku`, `price`, `currency`, `status`, and `created_at`.



### Step 1 — Start with the base wrapper

Every schema begins with the same outer structure. The `name`, `strict`, and `schema` fields are always required — and all three must be nested inside the `json_schema` object.

```json
{
  "type": "json_schema",
  "json_schema": {
    "name": "product_list_response",
    "strict": true,
    "schema": {
      ...
    }
  }
}
```

> Set `name` to a meaningful label for your schema. Use underscores in place of spaces.



### Step 2 — Define the top-level structure

The root of every schema must be an `object`. Inside its `properties`, declare the top-level fields expected in the response. In this case, the response contains a single field: `products`.

```json
"schema": {
  "type": "object",
  "properties": {
    "products": {
      ...
    }
  },
  "required": ["products"],
  "additionalProperties": false
}
```



### Step 3 — Define `products` as an array

Since `products` is a list of multiple items, its type is `array`. The `items` property is then used to describe the structure of a single product within that list.

```json
"products": {
  "type": "array",
  "items": {
    ...
  }
}
```



### Step 4 — Describe a single product

Each product is an `object` containing several fields. The appropriate type is assigned to each field based on the nature of its value.

| Field | Value Type | Reason |
|---|---|---|
| `id` | `integer` | A numeric identifier with no decimals |
| `name` | `string` | A text value |
| `sku` | `string` | A text-based product code |
| `price` | `number` | A decimal numeric value |
| `currency` | `string` | A text value |
| `status` | `string` + `enum` | Restricted to three fixed values only |
| `created_at` | `string` + `format: date-time` | A standardized date-time string |

```json
"items": {
  "type": "object",
  "properties": {
    "id":       { "type": "integer" },
    "name":     { "type": "string" },
    "sku":      { "type": "string" },
    "price":    { "type": "number" },
    "currency": { "type": "string" },
    "status": {
      "type": "string",
      "enum": ["active", "inactive", "out_of_stock"]
    },
    "created_at": {
      "type": "string",
      "format": "date-time"
    }
  },
  "required": ["id", "name", "sku", "price", "currency", "status", "created_at"],
  "additionalProperties": false
}
```



### Step 5 — Complete Schema

The following is the final, assembled schema incorporating all steps above.

```json
{
  "type": "json_schema",
  "json_schema": {
    "name": "product_list_response",
    "strict": true,
    "schema": {
      "type": "object",
      "properties": {
        "products": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "id":       { "type": "integer" },
              "name":     { "type": "string" },
              "sku":      { "type": "string" },
              "price":    { "type": "number" },
              "currency": { "type": "string" },
              "status": {
                "type": "string",
                "enum": ["active", "inactive", "out_of_stock"]
              },
              "created_at": {
                "type": "string",
                "format": "date-time"
              }
            },
            "required": ["id", "name", "sku", "price", "currency", "status", "created_at"],
            "additionalProperties": false
          }
        }
      },
      "required": ["products"],
      "additionalProperties": false
    }
  }
}
```



## JSON Mode

If a structured schema is not required and you only need the response to be returned as valid JSON, JSON Mode can be enabled as a simpler alternative.

Set `text.format` to the following:

```json
{
  "type": "json_object"
}
```

> **Note:** JSON Mode guarantees that the output is valid JSON, but does not enforce any specific field structure. Use a full schema when consistent field names and types are required.



## Schema Validation Rules

The following rules must be respected for a schema to function correctly.

1. Every `object` must include a `properties` block, a `required` array, and `"additionalProperties": false`.
2. Every `array` must include an `items` block that defines the structure of a single element.
3. Every field must have a `type` declared.
4. The `name`, `strict`, and `schema` fields must always be nested inside the `json_schema` object — never at the top level alongside `type`.
5. `anyOf` cannot be used as the type of the root object. It is only valid on individual fields within a schema.

## Support

Need help? Contact our support team at hello@appse.ai
