---
layout: default-layout
title: EnumValidationStatus - Dynamsoft Capture Vision React Native
description: Enumeration EnumValidationStatus of Dynamsoft Capture Vision React Native Edition defines the status of a field's value after the internal validation checks
keywords: captured result, react native, capture vision, mapping, code parser, validation
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumValidationStatus
---

# EnumValidationStatus

`EnumValidationStatus` is an enumeration that represents whether the associated field's value passed the internal validation checks.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
enum EnumValidationStatus {
  VS_NONE,
  VS_SUCCEEDED,
  VS_FAILED
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `VS_NONE` | No validation check has been performed. |
| `VS_SUCCEEDED` | The validation of this field was successful. |
| `VS_FAILED` | The validation of this field was unsuccessful. |
