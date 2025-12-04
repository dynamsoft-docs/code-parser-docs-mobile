---
layout: default-layout
title: ParsedResult - Dynamsoft Capture Vision React Native Edition
description: Interface ParsedResult represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.
keywords: originalImageHashId, items, errorCode, ParsedResult, api reference, barcode result, capture, React Native, code parser
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ParsedResult
---

# Interface ParsedResult

Interface `ParsedResult` represents the result of a code parsing process. It provides access to the individual parsed items resulting from a document or an encrypted text.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface ParsedResult extends CapturedResultBase
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`items`](#items) | *Array\<ParsedResultItem\>* | A list of [`ParsedResultItem`](parsed-result-item.md), the basic unit representing a single parsed result from an encrypted text. |

The following properties are inherited from [`CapturedResultBase`]({{ site.dcv_react_native_api }}core/captured-result-base.html):

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`originalImageHashId`]({{ site.dcv_react_native_api }}core/captured-result-base.html#originalimagehashid) | *String* | The hash id of the original image. You can use this ID to get the original image via the `IntermediateResultManager` interface. |
| [`rotationTransformMatrix`]({{ site.dcv_react_native_api }}core/captured-result-base.html#rotationtransformmatrix) |  *Matrix4* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`]({{ site.dcv_react_native_api }}core/captured-result-base.html#errorcode) | *int* | The error code associated with the capture result. |
| [`errorMessage`]({{ site.dcv_react_native_api }}core/captured-result-base.html#errormessage) | *String* | The error message associated with the capture result. |

### items

A list of [`ParsedResultItem`](parsed-result-item.md), the basic unit representing a single parsed result from an encrypted text.

```js
items?: Array<ParsedResultItem>
```
