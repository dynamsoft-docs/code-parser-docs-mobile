---
layout: default-layout
title: EnumMappingStatus - DCP MAUI Edition API Reference
description: Enumeration EnumMappingStatus of 
keywords: Mapping status
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumMappingStatus
---

# EnumMappingStatus

`MappingStatus` represents the outcome of a mapping operation on a field.

## Definition

*Namespace:* Dynamsoft.CodeParser.Maui

*Assembly:* Dynamsoft.CodeParser.Maui

```csharp
public enum EnumMappingStatus
{
    /** The field has no mapping specified. */
    MS_NONE = 0,
    /** Find a mapping for the field value. */
    MS_SUCCEEDED = 1,
    /** Failed to find a mapping for the field value. */
    MS_FAILED = 2
}
```
