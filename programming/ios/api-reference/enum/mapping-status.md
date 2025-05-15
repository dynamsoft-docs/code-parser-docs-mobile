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

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
typedef NS_ENUM(NSInteger, DSMappingStatus)
{
   /** The field has no mapping specified. */
   DSMappingStatusNotSpecified = 0,
   /** Find a mapping for the field value. */
   DSMappingStatusSucceeded = 1,
   /** Failed to find a mapping for the field value. */
   DSMappingStatusFailed = 2
};
```
>
```swift
public enum MappingStatus : Int
{
   /** The field has no mapping specified. */
   none = 0
   /** Find a mapping for the field value. */
   succeeded = 1
   /** Failed to find a mapping for the field value. */
   failed = 2
}
```
