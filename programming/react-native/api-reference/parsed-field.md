---
layout: default-layout
title: ParsedField - Dynamsoft Capture Vision React Native Edition
description: Interface ParsedField represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.
keywords: originalImageHashId, items, errorCode, ParsedField, api reference, barcode result, capture, React Native, code parser
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ParsedField
---

# Interface ParsedField

Interface `ParsedField` represents a field from the [`ParsedResultItem`](parsed-result-item.md) output of an encrypted text coming from a document or a data source. It contains the parsed value along with its mapping and validation status.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface ParsedField
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`value`](#value) | *String* | The processed value of the parsed field. |
| [`mappingStatus`](#mappingstatus) | [*EnumMappingStatus*](enum/mapping-status.md) | A status representing whether the field was mapped from the source data or not. |
| [`validationStatus`](#validationstatus) | [*EnumValidationStatus*](enum/validation-status.md) | The status of a field's value after the internal validation checks. |

### value

The processed value of the parsed field.

```js
value?: string
```

### mappingStatus

A status representing whether the field was mapped from the source data or not, represented as a [`EnumMappingStatus`](enum/mapping-status.md). If the field was unsuccessful during the mapping process, the mappingStatus would be `EnumMappingStatus.failed`.

```js
mappingStatus?: EnumMappingStatus | number
```

### validationStatus

The status of a field's value after the internal validation checks, represented as a [`EnumValidationStatus`](enum/validation-status.md). Once a field is parsed by the Code Parser, it is run through validation checks to make sure that the information is accurate and correct. If a field's value does not pass, the validationStatus would be `EnumValidationStatus.failed`.

```js
validationStatus?: EnumValidationStatus | number
```
