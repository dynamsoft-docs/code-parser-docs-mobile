---
layout: default-layout
title: MappingStatus - Dynamsoft Code Parser Enumerations
description: The enumeration MappingStatus of Dynamsoft Code Parser represents the outcome of a mapping operation on a field.
keywords: Mapping status
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: MappingStatus
---

# Enumeration MappingStatus

`MappingStatus` represents the outcome of a mapping operation on a field.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumMappingStatus {
   /** The field has no mapping specified. */
   public static final int MS_NONE = 0;
   /** Find a mapping for the field value. */
   public static final int MS_SUCCEEDED = 1;
   /** Failed to find a mapping for the field value. */
   public static final int MS_FAILED = 2;
}
```
