---
layout: default-layout
title: ParsedResultItem - Dynamsoft Capture Vision React Native Edition
description: Interface ParsedResult represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.
keywords: originalImageHashId, items, errorCode, ParsedResultItem, api reference, barcode result, capture, React Native, code parser
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ParsedResultItem
---

# Interface ParsedResultItem

Interface `ParsedResultItem` represents the most basic unit of a parsed result. It includes specific details relevant to the parsed data, including the code type, the raw JSON string, and a map of the individual parsed fields.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface ParsedResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`parsedFields`](#parsedfields) | *Map\<String, ParsedField\>* | A map of parsed fields extracted from the parsed result. |
| [`jsonString`](#jsonstring) | *String* | The raw JSON string representation of the parsed result. |
| [`codeType`](#codetype) | *String* | The type of the encrypted code associated to the attached parsed result. |

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_react_native_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`targetROIDefName`]({{ site.dcv_react_native_api }}core/captured-result-item.html#targetroidefname) | *String* | The name of the target region of interest (ROI) where the captured result was found. |
| [`taskName`]({{ site.dcv_react_native_api }}core/captured-result-item.html#taskname) | *String* | The name of the recognition task that produced the CapturedResultItem. |
| [`type`]({{ site.dcv_react_native_api }}core/captured-result-item.html#type) | [*EnumCapturedResultItemType*]({{ site.dcv_react_native_api }}core/enum/captured-result-item-type.html) | The type of the captured result item. |

### parsedFields

A map of the parsed fields extracted from the parsed result.

- Key: The field names of the code. [Check the available field names]({{ site.code_types }})
- Value: [`ParsedField`](parsed-field.md)

```js
parsedFields?: Record<string, ParsedField>
```

### jsonString

The text of the parsed result as a JSON string.

```js
jsonString: string
```

### codeType

The type of the encrypted code associated to the attached parsed result. The code can be a MRZ document (passport, visa, etc.), a driver license (North America or South Africa), or an Aadhar card. 

```js
codeType: string
```
