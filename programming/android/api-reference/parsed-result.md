---
layout: default-layout
title: ParsedResult Class - Dynamsoft Code Parser SDK Android Edition API Reference
description: This page shows ParsedResult Class of Dynamsoft Code Parser SDK Android Edition.
keywords: ParsedResult, api reference, Android
needAutoGenerateSidebar: true
---


# ParsedResult Class

`ParsedResult` class stores all parsed result items that are obtained from a single image. It carries additional information such as the original image data or error messages.

## Definition

*Namespace:* com.dynamsoft.dcp

*Assembly:* DynamsoftCodeParser.aar

```java
class ParsedResult
```

| Method               | Description |
|----------------------|-------------|
| [`getItems`](#getitems) | Gets the parsed result item at the specified index. |

The following methods are inherited from [`CapturedResultBase`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html):

| Method | Description |
| ------ | ----------- |
| [`getOriginalImageHashId`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#getoriginalimagehashid) | Gets the hash id of the original image. |
| [`getOriginalImageTag`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#getoriginalimagetag) | Gets the [ImageTag](image-tag.md) of the original image. |
| [`getRotationTransformMatrix`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#getrotationtransformmatrix) | Gets the rotation transformation matrix of the original image relative to the rotated image. |
| [`getErrorCode`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#geterrorcode) | Gets the error code of this result. |
| [`getErrorMessage`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#geterrormessage) | Gets the error message of this result. |

### getItems

Gets the parsed result item at the specified index.

```java
ParsedResultItem[] getItems();
```

**Return value**

Returns an array of `ParsedResultItem`.

**See Also**

[ParsedResultItem]({{ site.dcp_android_api }}parsed-result-item.html)
