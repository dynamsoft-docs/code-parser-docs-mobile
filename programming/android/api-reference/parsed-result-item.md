---
layout: default-layout
title: ParsedResultItem Class - Dynamsoft Code Parser SDK Android Edition API Reference
description: This page shows ParsedResultItem Class of Dynamsoft Code Parser SDK Android Edition.
keywords: ParsedResultItem, api reference, Android
needAutoGenerateSidebar: true
---

# ParsedResultItem Class

`ParsedResultItem` it the basic unit of a parsed result. It stores the field name, value and additional information.

## Definition

*Namespace:* com.dynamsoft.dcp

*Assembly:* DynamsoftCodeParser.aar

```java
class ParsedResultItem extends CapturedResultItem
```

  | Method               | Description |
  |----------------------|-------------|
  | [`getCodeType`](#getcodetype) | Gets the code type of the parsed result. |
  | [`getFieldMappingStatus`](#getfieldmappingstatus) | Gets the mapping status of a specified field from the parsed result. |
  | [`getFieldValidationStatus`](#getfieldvalidationstatus) | Gets the validation status of a specified field from the parsed result. |
  | [`getFieldValue`](#getfieldvalue) | Gets the value of a specified field from the parsed result. |
  | [`getJsonString`](#getjsonstring) | Gets the parsed result as a JSON formatted string. |
  
## getCodeType

Gets the code type of the parsed result.

```java
String getCodeType();
```

**Return Value**

Returns a string value representing the code type.

## getJsonString

Gets the parsed result as a JSON formatted string.

```java
String getJsonString();
```

**Return Value**

Returns a JSON formatted string representing the parsed result.

## getFieldValue

Gets the value of a specified field from the parsed result.

```java
String getFieldValue(String fieldName);
```

**Parameters**

`[in] fieldName`: The name of the field.

**Return Value**

Returns a string representing the specified field value.

## getFieldMappingStatus

Gets the mapping status of a specified field from the parsed result.

```java
EnumMappingStatus getFieldMappingStatus(String fieldName);
```

**Parameters**

`[in] fieldName`: The name of the field.

**Return Value**

Returns a [MappingStatus]({{ site.enumerations }}code-parser/mapping-status.html?lang=android) enumeration value representing the mapping status of a specified field.

**See Also**

[MappingStatus]({{ site.enumerations }}code-parser/mapping-status.html?lang=android)

## getFieldValidationStatus

Gets the validation status of a specified field from the parsed result.

```java
EnumValidationStatus getFieldValidationStatus(String fieldName);
```

**Parameters**

`[in] fieldName`: The name of the field.

**Return Value**

Returns a [ValidationStatus]({{ site.enumerations }}code-parser/validation-status.html?lang=android) enumeration value representing the validation status of a specified field.

**See Also**

[ValidationStatus]({{ site.enumerations }}code-parser/validation-status.html?lang=android)

## getParsedFields

Get the field names and values of the parsed fields as a `HashMap`. The field names are stored as the key of the HashMap while the field values are stored as the value.

```java
HashMap<String, String> getParsedFields();
```

**Return Value**

A HashMap that contains the names and values of the parsed fields.
