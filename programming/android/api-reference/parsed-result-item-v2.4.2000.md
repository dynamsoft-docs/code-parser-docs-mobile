---
layout: default-layout
title: ParsedResultItem Class - Dynamsoft Code Parser SDK Android Edition API Reference
description: This page shows ParsedResultItem Class of Dynamsoft Code Parser SDK Android Edition.
keywords: ParsedResultItem, api reference, Android
needAutoGenerateSidebar: true
---

# ParsedResultItem Class

`ParsedResultItem` is the basic unit of a parsed result. It stores the field name, value and additional information.

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

Returns a string value representing the code type. It can be one of the following:

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

Gets the mapping status of a specified field from the parsed result. Certain fields in the parsed result, such as the residing province or state, are abbreviated (e.g. BC standing for British Columbia). The library takes such fields and maps them to their full form. If the mapping is successful, the `MappingStatus` will be `MS_SUCCEEDED`. To learn of the other options of `MappingStatus`, please refer to the link below.

```java
EnumMappingStatus getFieldMappingStatus(String fieldName);
```

**Parameters**

`[in] fieldName`: The name of the field.

**Return Value**

Returns a [MappingStatus]({{ site.dcv_enumerations }}code-parser/mapping-status.html?lang=android) enumeration value representing the mapping status of a specified field.

**See Also**

[MappingStatus]({{ site.dcv_enumerations }}code-parser/mapping-status.html?lang=android)

## getFieldValidationStatus

Gets the validation status of a specified field from the parsed result. Certain fields can be validated with one of four possible validation methods: certification, checksum, length, and regex. Whether a field is validated or not, as well as the validation method, is determined by the code specification e.g. AAMVA specification.

```java
EnumValidationStatus getFieldValidationStatus(String fieldName);
```

**Parameters**

`[in] fieldName`: The name of the field.

**Return Value**

Returns a [ValidationStatus]({{ site.dcv_enumerations }}code-parser/validation-status.html?lang=android) enumeration value saying whether the validation of a specified field was successful, failed, or if it did not require validation.

**See Also**

[ValidationStatus]({{ site.dcv_enumerations }}code-parser/validation-status.html?lang=android)

## getParsedFields

Get the field names and values of the parsed fields as a `HashMap`. The field names are stored as the key of the HashMap while the field values are stored as the value.

```java
HashMap<String, String> getParsedFields();
```

**Return Value**

A HashMap that contains the names and values of the parsed fields.
