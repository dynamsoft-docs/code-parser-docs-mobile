---
layout: default-layout
title: DSParsedResult Class - Dynamsoft Code Parser SDK iOS Edition API Reference
description: This page shows DSParsedResult Class of Dynamsoft Code Parser SDK iOS Edition.
keywords: DSParsedResult, api reference, iOS
needAutoGenerateSidebar: true
---


# DSParsedResult Class

`DSParsedResult` class stores all parsed result items that are obtained from a single image. It carries additional information such as the original image data or error messages.

## Definition

*Assembly:* DynamsoftCodeParser.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSParsedResult : NSObject
```
2. 
```swift
class ParsedResult : NSObject
```

## Property Summary

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`items`](#items) | *NSArray<DSParsedResultItem*> \** | Gets the parsed result item at the specified index. |

The following attributes are inherited from [`DSCapturedResultBase`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html):

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`originalImageHashId`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#originalimagehashid) | *NSString \** | The hash id of the original image. |
| [`originalImageTag`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#originalimagetag) | *DSImageTag \** | The [DSImageTag](image-tag.md) of the original image. |
| [`rotationTransformMatrix`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#rotationtransformmatrix) | *CGAffineTransform* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#errorcode) | *NSInteger* | Get the error code of this result. |
| [`errorMessage`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#errormessage) | *NSString \** | Get the error message of this result. |

## Method Detail

### items

Gets the parsed result item at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, readonly) NSArray<DSParsedResultItem*>* items;
```
2. 
```swift
var items: [ParsedResultItem]? { get }
```

**Return value**

Returns an array of [`ParsedResultItem`](parsed-result-item.html).
