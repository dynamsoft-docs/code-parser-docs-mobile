---
layout: default-layout
title: ValidationStatus - Dynamsoft Code Parser Enumerations
description: The enumeration ValidationStatus of Dynamsoft Code Parser describes the outcome of a validation process on a field.
keywords: Validation status
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: ValidationStatus
---

# Enumeration ValidationStatus

`ValidationStatus` describes the outcome of a validation process on a field.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumValidationStatus
{
   /** The field has no validation specified. */
   public static final int VS_NONE = 0;
   /** The validation for the field has been succeeded. */
   public static final int VS_SUCCEEDED = 1;
   /** The validation for the field has been failed. */
   public static final int VS_FAILED = 2;
}
```
