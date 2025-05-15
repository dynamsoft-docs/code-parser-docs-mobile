---
layout: default-layout
title: DSCodeParserModule Class - Dynamsoft Code Parser SDK iOS Edition API Reference
description: This page shows DSCodeParserModule Class of Dynamsoft Code Parser SDK iOS Edition.
keywords: DSCodeParserModule, api reference, iOS
needAutoGenerateSidebar: true
---

# DSCodeParserModule Class

`DSCodeParserModule` class defines general functions of the code parser module.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSCodeParserModule : NSObject
```
2. 
```swift
class CodeParserModule : NSObject
```

## Method Summary

| Method | Description |
| ------ | ----------- |
| [`getVersion`](#getversion) | Get version information of SDK.|

## Method Detail

### getVersion

Get version information of SDK.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (NSString *)getVersion;
```
2. 
```swift
class func getVersion() -> String
```

**Return Value**

The version information string.
