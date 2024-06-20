---
layout: default-layout
title: ParsedResultItem Class - DCP MAUI Edition API Reference
description: ParsedResultItem class of DCP MAUI is the basic unit of a parsed result. It stores the field name, value and additional information.
keywords: ParsedResultItem, api reference, Android
needAutoGenerateSidebar: true
---

# ParsedResultItem Class

`ParsedResultItem` is the basic unit of a parsed result. It stores the field name, value and additional information.

## Definition

*Namespace:* Dynamsoft.CodeParser.Maui

*Assembly:* Dynamsoft.CodeParser.Maui

```csharp
class ParsedResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`CodeType`](#codetype) | *string* | The code type of the parsed result. |
| [`JsonString`](#jsonstring) | *string* | The parsed result as a JSON formatted string. |
| [`ParsedFields`](#parsedfields) | *Dictionary* | The parsed result with name & value in a `Dictionary`. |

### CodeType

The code type of the parsed result.

```csharp
string CodeType { get; }
```

The code type will be one of the follows:

- "AADHAAR"
- "AAMVA_DL_ID"
- "AAMVA_DL_ID_WITH_MAG_STRIPE"
- "MRTD_TD1_ID"
- "MRTD_TD2_ID"
- "MRTD_TD2_VISA"
- "MRTD_TD3_PASSPORT"
- "MRTD_TD3_VISA"
- "MRTD_TD2_FRENCH_ID"
- "SOUTH_AFRICA_DL"
- "VIN"

### JsonString

The parsed result as a JSON formatted string.

```csharp
string JsonString { get; }
```

### ParsedFields

The parsed result with name & value in a `Dictionary`.

```csharp
Dictionary<string, ParsedField> ParsedFields { get; }
```
