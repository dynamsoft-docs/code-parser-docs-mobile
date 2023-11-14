---
layout: default-layout
title: CodeParserModule Class - Dynamsoft Code Parser SDK iOS Edition API Reference
description: This page shows CodeParserModule Class of Dynamsoft Code Parser SDK iOS Edition.
keywords: CodeParserModule, api reference, iOS
needAutoGenerateSidebar: true
---

# CodeParserModule Class

`CodeParserModule` class defines general functions of the code parser module.

## Definition

*Assembly:* DynamsoftCodeParser.xcframework

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

## getVersion

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
