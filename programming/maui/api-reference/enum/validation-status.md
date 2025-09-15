---
layout: default-layout
title: EnumValidationStatus - DCP MAUI Edition API Reference
description: Enumeration EnumValidationStatus of DCP MAUI edition describes the outcome of a validation process on a field.
keywords: validation status
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumValidationStatus
---

# EnumValidationStatus

`ValidationStatus` describes the outcome of a validation process on a field.

## Definition

*Namespace:* Dynamsoft.CodeParser.Maui

*Assembly:* Dynamsoft.CodeParser.Maui

```csharp
public enum EnumValidationStatus
{
    /** The field has no validation specified. */
    VS_NONE = 0,
    /** The validation for the field has been succeeded. */
    VS_SUCCEEDED = 1,
    /** The validation for the field has been failed. */
    VS_FAILED = 2
}
```
