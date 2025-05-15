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

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`getFieldRawValue`](#getfieldrawvalue) | Gets the raw value of the specified field. |
| [`getFieldValue`](#getfieldvalue) | Gets the value of a specified field from the parsed result. |

## Property Summary

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`codeType`](#codetype) | *NSString* | Gets the code type of the parsed result. |
| [`jsonString`](#jsonstring) | *NSString* | Gets the parsed result as a JSON formatted string. |
| [`parsedFields`](#parsedfields) | *NSDictionary* | A `NSDictionary` object stores the field names and values of the parsed fields. |

## Method Detail

### getFieldMappingStatus

Gets the mapping status of a specified field from the parsed result. Certain fields in the parsed result, such as the residing province or state, are abbreviated (e.g. BC standing for British Columbia). The library takes such fields and maps them to their full form. If the mapping is successful, the `MappingStatus` will be `DSMappingStatusSucceeded`. To learn of the other options of `MappingStatus`, please refer to the link below.

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

Gets the validation status of a specified field from the parsed result. Certain fields can be validated with one of four possible validation methods: certification, checksum, length, and regex. Whether a field is validated or not, as well as the validation method, is determined by the code specification e.g. AAMVA specification.

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

Returns a [ValidationStatus]({{ site.dcv_enumerations }}code-parser/validation-status.html?lang=objc,swift) enumeration value saying whether the validation of a specified field was successful, failed, or if it did not require validation..

### getFieldRawValue

Gets the raw value of the specified field.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString *)getFieldRawValue(NSString *)fieldName;
```
2. 
```swift
func getFieldRawValue(_ fieldName:String) -> String
```

**Parameters**

`fieldName`: The name of the field.

**Return Value**

Returns a string representing the specified field raw value.

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

> [View more information about the field names of all supported code types]({{ site.code_types }}).

**Return Value**

Returns a string representing the specified field value.

## Property Detail

### codeType

Returns the code type of the parsed result. It can be one of the following:

- "AADHAAR"
- "AAMVA_DL_ID"
- "AAMVA_DL_ID_WITH_MAG_STRIPE"
- "MRTD_TD1_ID"
- "MRTD_TD2_ID"
- "MRTD_TD2_VISA"
- "MRTD_TD3_PASSPORT"
- "MRTD_TD3_VISA"
- "MRTD_TD2_FRENCH_ID"
- "SOUTH_AFRICA_DL"
- "VIN"

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

> [View more information about the field names of all supported code types]({{ site.code_types }}).
