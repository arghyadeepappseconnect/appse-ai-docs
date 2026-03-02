---
slug: /platform/key-concepts/nodes/built-in/aggregator
title: Aggregator Node
---

The Aggregator Node in appse ai allows you to combine multiple incoming records into a single structured output.

It helps you reshape, batch, and organize data before passing it to downstream nodes.

This is useful when you want to:
* Combine multiple records into one payload
* Prepare batch API requests
* Collect specific fields across all items
* Transform item-wise data into grouped arrays
* Build structured objects for integrations

---

## Aggregation Mode

When configuring the Aggregator node, the first step is to select the **Aggregation Mode**.

You can choose between:

1. **All Item Data**
2. **Individual Fields**

---

# All Item Data

This mode aggregates complete records into a single array wrapped inside a field you define.

It is commonly used when:
* Sending bulk data to APIs
* Creating batch database inserts
* Packaging workflow results into a structured object

---

## Configuration Fields

### 1. Output Field Name

This defines the wrapper field that will contain the aggregated array of items.

Example:

If you enter:
Orders


The output structure becomes:

```json
{
  "orders": [
    { ... },
    { ... },
    { ... }
  ]
}
```
## 2. Fields to Include

This determines which fields from each incoming record are included in the aggregated output.

You can select one of the following options:

### 2a. All Fields

Includes every field from each input record.

---

### 2b. Specified Fields

Includes only selected fields that you explicitly define.

When selected, an additional configuration field appears:

**Specified Fields**  
Enter comma-separated field names to include.

**Example:**
name, email, amount

Only these fields will be present in each aggregated object.

---

### 2c. All Fields Except

Includes all fields except the ones you explicitly exclude.

When selected, an additional configuration field appears:

**Fields to Exclude**  
Enter comma-separated field names to exclude.

**Example:**
internalId, debugInfo

All other fields will be included in the aggregation.

---

## Example (All Item Data Mode)

### Input:
```json
[
  { "name": "Alice", "amount": 500, "internalId": 101 },
  { "name": "Bob", "amount": 700, "internalId": 102 }
]
```