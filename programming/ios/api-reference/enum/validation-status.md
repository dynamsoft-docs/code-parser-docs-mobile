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

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
typedef NS_ENUM(NSInteger, DSValidationStatus)
{
   /** The field has no validation specified. */
   DSValidationStatusNone = 0,
   /** The validation for the field has been succeeded. */
   DSValidationStatusSucceeded = 1,
   /** The validation for the field has been failed. */
   DSValidationStatusFailed = 2
};
```
>
```swift
public enum ValidationStatus : Int
{
   /** The field has no validation specified. */
   none = 0
   /** The validation for the field has been succeeded. */
   succeeded = 1
   /** The validation for the field has been failed. */
   failed = 2
}
```
