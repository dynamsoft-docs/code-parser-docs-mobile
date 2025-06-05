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
class ParsedResult : CapturedResultBase
```

| Property | Type | Description |
|----------|------|-------------|
| [`Items`](#items) | *ParsedResultItem[]* | The parsed result item at the specified index. |

The following properties are inherited from [`CapturedResultBase`]({{ site.dcv_maui_api }}core/captured-result-base.html):

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`OriginalImageHashId`]({{ site.dcv_maui_api }}core/captured-result-base.html#originalimagehashid) | *string* | Represents the hash id of the original image. |
| [`RotationTransformMatrix`]({{ site.dcv_maui_api }}core/captured-result-base.html#rotationtransformmatrix) | *Matrix* | Represents the rotation transformation matrix of the original image relative to the rotated image. |
| [`ErrorCode`]({{ site.dcv_maui_api }}core/captured-result-base.html#errorcode) | *int* | Represents the error code of this result. |
| [`ErrorMessage`]({{ site.dcv_maui_api }}core/captured-result-base.html#errormessage) | *string* | Represents the error message of this result. |

### Items

The parsed result item at the specified index.

```csharp
ParsedResultItem[]? Items { get; }
```

**See Also**

[ParsedResultItem]({{ site.dcp_maui_api }}parsed-result-item.html)
