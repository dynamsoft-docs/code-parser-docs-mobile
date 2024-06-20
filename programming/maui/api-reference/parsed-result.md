---
layout: default-layout
title: ParsedResult Class - DCP MAUI Edition API Reference
description: ParsedResult class of DCP MAUI stores all parsed result items that are obtained from a single image.
keywords: ParsedResult, api reference, Android
needAutoGenerateSidebar: true
---


# ParsedResult Class

`ParsedResult` class stores all parsed result items that are obtained from a single image. It carries additional information such as the original image data or error messages.

## Definition

*Namespace:* Dynamsoft.CodeParser.Maui

*Assembly:* Dynamsoft.CodeParser.Maui

```csharp
class ParsedResult
```

| Property | Type | Description |
|----------|------|-------------|
| [`OriginalImageHashId`](#originalimagehashid) | *string* | The hash ID of the source image. |
| [`Items`](#items) | *List<ParsedResultItem>* | The parsed result item at the specified index. |
| [`ErrorCode`](#errorcode) | *int* | The error code of the parsed result, if an error occurred. |
| [`ErrorString`](#errormessage) | *string* | The error message of the parsed result, if an error occurred. |

### OriginalImageHashId

The hash ID of the source image.

```csharp
string OriginalImageHashId { get; }
```

### Items

The parsed result item at the specified index.

```csharp
List<ParsedResultItem> Items { get; }
```

**See Also**

[ParsedResultItem]({{ site.dcp_maui_api }}parsed-result-item.html)

### ErrorCode

The error code of the parsed result, if an error occurred.

```csharp
int ErrorCode { get; }
```

### ErrorMessage

The error message of the parsed result, if an error occurred.

```csharp
string ErrorMessage { get; }
```
