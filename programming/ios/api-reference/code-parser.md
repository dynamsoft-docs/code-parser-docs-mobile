---
layout: default-layout
title: CCodeParser Class - Dynamsoft Code Parser SDK Android Edition API Reference
description: This page shows CCodeParser Class of Dynamsoft Code Parser SDK Android Edition.
keywords: CCodeParser, api reference, Android
needAutoGenerateSidebar: true
---

# CodeParser Class

## Definition

*Assembly:* DynamsoftCodeParser.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSCodeParser : NSObject
```
2. 
```swift
class CodeParser : NSObject
```

| Method | Description |
| ------ | ----------- |
| [`init`](#init) | The constructor.|
| [`initSettingsFromFile`](#initsettingsfromfile)  | Initialize runtime settings with the settings in a given JSON file. |
| [`initSettings`](#initsettings) | Initialize runtime settings with the settings in a given JSON string. |
| [`parse`](#parse) | Parses code data for readable results. |
| [`resetSettings`](#resetsettings) | Reset runtime settings to default. |

## init

Default constructor of a `CodeParser` object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype)init;
```
2. 
```swift
```

## Parse

Parses code data for human-readable results.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable DSParsedResultItem *)parse:(NSData *)bytes
                       taskSettingName:(NSString *)taskSettingName
                                 error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
func parse() -> ParsedResultItem
```

**Parameters**

`[in] bytes` The array of bytes which contain the code string.

`[in] taskSettingName`<sub>Optional</sub> The name of [`CodeParserTaskSetting`]({{site.parameters}}file/task-settings/code-parser-task-settings.html) which defines the settings used for code parsing.

**Return Value**

Returns [`ParsedResultItem`](parsed-result-item.md) which stores the human-readable results.

## ResetSettings

Reset all parameters to default values.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)resetSettings;
```
2. 
```swift
```

## InitSettingsFromFile

Initialize settings from a given file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)initSettingsFromFile:(NSString *)filePath
                       error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
```

**Parameters**

`[in] filePath` The path of the settings file.

## InitSettings

Initialize settings from a given string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)initSettings:(NSString *)content
               error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
```

**Parameters**

`[in] content` A JSON string that represents the content of the settings.
