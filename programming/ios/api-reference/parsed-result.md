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
| [`getOriginalImageHashId`](#getoriginalimagehashid) |  | Gets the hash ID of the source image. |
| [`getOriginalImageTag`](#getoriginalimagetag) |  | Gets the tag of the source image. |
| [`getItems`](#getitems) |  | Gets the parsed result item at the specified index. |
| [`getErrorCode`](#geterrorcode) |  | Gets the error code of the parsed result, if an error occurred. |
| [`getErrorString`](#geterrormessage) |  | Gets the error message of the parsed result, if an error occurred. |

## Method Detail

### getOriginalImageHashId

Gets the hash ID of the source image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, readonly) NSString* originalImageHashId;
```
2. 
```swift
var originalImageHashId: String? { get }
```

**Return value**

Returns a pointer to a null-terminated string containing the hash ID of the source image.

### getOriginalImageTag

Gets the tag of the source image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, readonly) DSImageTag* originalImageTag;
```
2. 
```swift
var originalImageTag: ImageTag? { get }
```

**Return value**

Returns a pointer to a CImageTag object representing the tag of the source image.

**See Also**

[ImageTag]({{ site.dcv_ios_api }}core/basic-structures/image-tag.html)

### getItems

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

### getErrorCode

Gets the error code of the parsed result, if an error occurred.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) NSInteger errorCode;
```
2. 
```swift
var errorCode: Int { get }
```

**Return value**

Returns the error code of the parsed result, or 0 if no error occurred.

### getErrorMessage

Gets the error message of the parsed result, if an error occurred.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) NSString * errorMessage;
```
2. 
```swift
var errorMessage: String? { get }
```

**Return value**

The error message in a string.
