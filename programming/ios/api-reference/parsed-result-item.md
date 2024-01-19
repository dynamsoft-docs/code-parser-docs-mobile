---
layout: default-layout
title: DSParsedResultItem Class - Dynamsoft Code Parser SDK iOS Edition API Reference
description: This page shows DSParsedResultItem Class of Dynamsoft Code Parser SDK iOS Edition.
keywords: DSParsedResultItem, api reference, iOS
needAutoGenerateSidebar: true
---


# DSParsedResultItem Class

`ParsedResultItem` it the basic unit of a parsed result. It stores the field name, value and additional information.

## Definition

*Assembly:* DynamsoftCodeParser.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSParsedResultItem: DSCapturedResultItem
```
2. 
```swift
class ParsedResultItem : CapturedResultItem
```

## Method Summary

| Method | Description |
| ------ | ----------- |
| [`getFieldMappingStatus`](#getfieldmappingstatus) | Gets the mapping status of a specified field from the parsed result. |
| [`getFieldValidationStatus`](#getfieldvalidationstatus) | Gets the validation status of a specified field from the parsed result. |
| [`getFieldValue`](#getfieldvalue) | Gets the value of a specified field from the parsed result. |

## Property Summary

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`codeType`](#codetype) | *NSString* | Gets the code type of the parsed result. |
| [`jsonString`](#jsonstring) | *NSString* | Gets the parsed result as a JSON formatted string. |
| [`parsedFields`](#parsedfields) | *NSDictionary* | A `NSDictionary` object stores the field names and values of the parsed fields. |

## Method Detail

### getFieldMappingStatus

Gets the mapping status of a specified field from the parsed result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSMappingStatus *)getFieldMappingStatus(NSString *)fieldName;
```
2. 
```swift
func getFieldMappingStatus(_ fieldName:String) -> MappingStatus
```

**Parameters**

`fieldName`: The name of the field.

**Return Value**

Returns a [MappingStatus]({{ site.dcv_enumerations }}code-parser/mapping-status.html?lang=objc,swift) enumeration value representing the mapping status of a specified field.

### getFieldValidationStatus

Gets the validation status of a specified field from the parsed result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSValidationStatus *)getFieldValidationStatus(NSString *)fieldName;
```
2. 
```swift
func getFieldValidationStatus(_ fieldName:String) -> ValidationStatus
```

**Parameters**

`fieldName`: The name of the field.

**Return Value**

Returns a [ValidationStatus]({{ site.dcv_enumerations }}code-parser/validation-status.html?lang=objc,swift) enumeration value representing the validation status of a specified field.

### getFieldValue

Gets the value of a specified field from the parsed result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString *)getFieldValue(NSString *)fieldName;
```
2. 
```swift
func getFieldValue(_ fieldName:String) -> String
```

**Parameters**

`fieldName`: The name of the field.

**Return Value**

Returns a string representing the specified field value.

## Property Detail

### codeType

Gets the code type of the parsed result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly) NSString * codeType;
```
2. 
```swift
var codeType: String? { get }
```

### jsonString

The parsed result as a JSON formatted string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly) NSString * jsonString;
```
2. 
```swift
var jsonString: String? { get }
```

### parsedFields

A `NSDictionary` object stores the field names and values of the parsed fields. The field names are stored as the key of the HashMap while the field values are stored as the value.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly) NSDictionary<NSString *, NSString *> * parsedFields;
```
2. 
```swift
var parsedFields: NSDictionary { get }
```
