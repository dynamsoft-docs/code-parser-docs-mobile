---
layout: default-layout
title: ParsedResult Class - Dynamsoft Code Parser SDK Android Edition API Reference
description: This page shows ParsedResult Class of Dynamsoft Code Parser SDK Android Edition.
keywords: ParsedResult, api reference, Android
needAutoGenerateSidebar: true
---


# ParsedResult Class

```java
class ParsedResult
```

| Method               | Description |
|----------------------|-------------|
| [`getOriginalImageHashId`](#getoriginalimagehashid) | Gets the hash ID of the source image. |
| [`getOriginalImageTag`](#getoriginalimagetag) | Gets the tag of the source image. |
| [`getItems`](#getitems) | Gets the parsed result item at the specified index. |
| [`getErrorCode`](#geterrorcode) | Gets the error code of the parsed result, if an error occurred. |
| [`getErrorString`](#geterrormessage) | Gets the error message of the parsed result, if an error occurred. |

### getOriginalImageHashId

Gets the hash ID of the source image.

```java
String getOriginalImageHashId();
```

**Return value**

Returns a pointer to a null-terminated string containing the hash ID of the source image.

### getOriginalImageTag

Gets the tag of the source image.

```java
ImageTag getOriginalImageTag();
```

**Return value**

Returns a pointer to a CImageTag object representing the tag of the source image.

**See Also**

[ImageTag]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)

### getItems

Gets the parsed result item at the specified index.

```java
ParsedResultItem[] getItems();
```

**Return value**

Returns an array of `ParsedResultItem`.

**See Also**

[ParsedResultItem]({{ site.dcp_android_api }}parsed-result-item.html)

### getErrorCode

Gets the error code of the parsed result, if an error occurred.

```java
int getErrorCode();
```

**Return value**

Returns the error code of the parsed result, or 0 if no error occurred.

### getErrorMessage

Gets the error message of the parsed result, if an error occurred.

```java
String getErrorMessage();
```

**Return value**

Returns a pointer to a null-terminated string containing the error message of the parsed result, or a pointer to an empty string if no error occurred.
