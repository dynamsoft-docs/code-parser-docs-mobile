---
layout: default-layout
title: ParsedField Class - DCP MAUI Edition API Reference
description: ParsedField class defindes the parsed field with its name, value and addtitional information.
keywords: ParsedField, api reference, Android
needAutoGenerateSidebar: true
---

# ParsedField Class

`ParsedField` class defindes the parsed field with its name, value and addtitional information.

## Definition

*Namespace:* Dynamsoft.CodeParser.Maui

*Assembly:* Dynamsoft.CodeParser.Maui

```csharp
class ParsedField
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Name`](#name) | *string* | The field name. |
| [`Value`](#value) | *string* | The field value. |
| [`MappingStatus`](#mappingstatus) | *EnumMappingStatus* | The mapping status of the field. |
| [`ValidationStatus`](#validationstatus) | *EnumValidationStatus* | The validation status of the field. |

### Name

The field name.

```csharp
string Name { get; }
```

### Value

The field value.

```csharp
string Value { get; }
```

### MappingStatus

The mapping status of the field.

```csharp
EnumMappingStatus MappingStatus { get; }
```

### ValidationStatus

The validation status of the field.

```csharp
EnumValidationStatus ValidationStatus { get; }
```
