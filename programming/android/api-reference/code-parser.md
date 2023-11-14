---
layout: default-layout
title: CCodeParser Class - Dynamsoft Code Parser SDK Android Edition API Reference
description: This page shows CCodeParser Class of Dynamsoft Code Parser SDK Android Edition.
keywords: CCodeParser, api reference, Android
needAutoGenerateSidebar: true
---

# CodeParser Class

The `CodeParser` class enable users to configure the code parser settings or parse the content.

## Definition

*Namespace:* com.dynamsoft.dcp

*Assembly:* DynamsoftCodeParser.aar

```java
class CodeParser
```

| Method | Description |
| ------ | ----------- |
| [`CodeParser`](#codeparser) | The constructor.|
| [`initSettingsFromFile`](#initsettingsfromfile)  | Initialize runtime settings with the settings in a given JSON file. |
| [`initSettings`](#initsettings) | Initialize runtime settings with the settings in a given JSON string. |
| [`parse`](#parse) | Parses code data for readable results. |
| [`resetSettings`](#resetsettings) | Reset runtime settings to default. |

## CodeParser

Default constructor of a `CodeParser` object.

```java
CodeParser();
```

## Parse

Parses code data for human-readable results.

```java
ParsedResultItem parse(byte[] bytes, String taskSettingName) throws CodeParserException;
```

**Parameters**

`[in] bytes` The array of bytes which contain the code string.

`[in] taskSettingName`<sub>Optional</sub> The name of [`CodeParserTaskSetting`]({{site.parameters}}file/task-settings/code-parser-task-settings.html) which defines the settings used for code parsing.

**Return Value**

Returns [`ParsedResultItem`](parsed-result-item.md) which stores the human-readable results.

## ResetSettings

Reset all parameters to default values.

```java
void resetSettings();
```

## InitSettingsFromFile

Initialize settings from a given file.

```java
void initSettingsFromFile(String filePath) throws CodeParserException;
```

**Parameters**

`[in] filePath` The path of the settings file.

## InitSettings

Initialize settings from a given string.

```java
void initSettings(String content)  throws CodeParserException;
```

**Parameters**

`[in] content` A JSON string that represents the content of the settings.
