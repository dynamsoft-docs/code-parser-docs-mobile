---
layout: default-layout
title: ParsedField Class - Dynamsoft Capture Vision Flutter Edition
description: The ParsedField class represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.
keywords: originalImageHashId, items, errorCode, ParsedField, api reference, barcode result, capture, flutter, code parser
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ParsedField
---

# ParsedField Class

The `ParsedField` class represents a field from the [`ParsedResultItem`](parsed-result-item.md) output of an encrypted text coming from a document or a data source. It contains the parsed value along with its mapping and validation status.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ParsedField
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`value`](#value) | *String* | The processed value of the parsed field. |
| [`rawValue`](#value) | *String* | The raw string value of the field as obtained from the source data. |
| [`mappingStatus`](#mappingstatus) | [*EnumMappingStatus*]({{ site.dcv_flutter_api }}core/enum/mapping-status.html) | A status representing whether the field was mapped from the source data or not. |
| [`validationStatus`](#validationstatus) | [*EnumValidationStatus*]({{ site.dcv_flutter_api }}core/enum/validation-status.html) | The status of a field's value after the internal validation checks. |

### value

The processed value of the parsed field.

```dart
String value;
```

### rawValue

The raw string value of the field as obtained from the source data.

```dart
String rawValue;
```

### mappingStatus

A status representing whether the field was mapped from the source data or not, represented as a [`EnumMappingStatus`](./enum/mapping-status.md). If the field was unsuccessful during the mapping process, the mappingStatus would be `EnumMappingStatus.failed`.

```dart
EnumMappingStatus mappingStatus;
```

### validationStatus

The status of a field's value after the internal validation checks, represented as a [`EnumValidationStatus`](./enum/validation-status.md). Once a field is parsed by the Code Parser, it is run through validation checks to make sure that the information is accurate and correct. If a field's value does not pass, the validationStatus would be `EnumValidationStatus.failed`.

```dart
EnumValidationStatus validationStatus;
```
