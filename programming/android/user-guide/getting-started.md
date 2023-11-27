---
layout: default-layout
title: User Guide - Dynamsoft Code Parser SDK Android Edition
description: This is the user guide of Dynamsoft Code Parser SDK Android Edition.
keywords: user guide, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Dynamsoft Code Parser - Android User Guide

- [Dynamsoft Code Parser - Android User Guide](#dynamsoft-code-parser---android-user-guide)
  - [Requirements](#requirements)
  - [Add the Libraries](#add-the-libraries)
    - [Add the Libraries Manually](#add-the-libraries-manually)
    - [Add the Libraries via Maven](#add-the-libraries-via-maven)
  - [Build Your First Application](#build-your-first-application)
    - [Create a New Project](#create-a-new-project)
    - [Include the Library](#include-the-library)
    - [Initialize the License](#initialize-the-license)
    - [Initialize Code Parser And Parse the Code Bytes](#initialize-code-parser-and-parse-the-code-bytes)
    - [Display Parsed Results](#display-parsed-results)
    - [Build and Run the Project](#build-and-run-the-project)

## Requirements

- Supported OS: Android 5.0 (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 3.4+ (Android Studio 4.2+ recommended).

## Add the Libraries

The Dynamsoft Code Parser (DCP) Android SDK comes with four libraries:

   | File | Description |
   |---------|-------------|
   | `DynamsoftCodeParser.aar` | The Dynamsoft Code Parser library, which includes code parsing logic and related APIs. |
   | `DynamsoftCore.aar` | The core library, which includes common basic structures and intermediate result related APIs. |
   | `DynamsoftLicense.aar` | The license library, which includes license related APIs. |
   | `DynamsoftCodeParserDedicator.aar`| The code parser helper library, which includes some validation functions used by the SDK.|

There are two ways to add the libraries into your project - **Manually** and **Maven**.

### Add the Libraries Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/survey/dlr/?utm_source=docs" target="_blank">Dynamsoft Website</a>. After unzipping, four **aar** files can be found in the **Dynamsoft\Libs** directory:

   - **DynamsoftCodeParser.aar**
   - **DynamsoftCore.aar**
   - **DynamsoftLicense.aar**
   - **DynamsoftCodeParserDedicator.aar**

2. Copy the above seven **aar** files to the target directory such as `[App Project Root Path]\app\libs`

3. Open the file `[App Project Root Path]\app\build.gradle` and add the reference in the dependencies:

   ```groovy
   dependencies {
         implementation fileTree(dir: 'libs', include: ['*.aar'])
   }
   ```

4. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

### Add the Libraries via Maven

1. Open the file `[App Project Root Path]\app\build.gradle` and add the Maven repository:

   ```groovy
   repositories {
        maven {
           url "https://download2.dynamsoft.com/maven/aar"
        }
   }
   ```

2. Add the references in the dependencies:

   ```groovy
   dependencies {
      implementation 'com.dynamsoft:dynamsoftcodeparser:2.0.20'
   }
   ```

3. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

## Build Your First Application

In this section, we are going to explain how to create a simple `HelloWorld` app for parsing text or bytes.

>Note:
>
>- Android Studio 2022.3.1 is used here in this guide.
>- You can get similar source code from
>    - <a href="https://github.com/Dynamsoft/code-parser-mobile-samples/tree/main/android/HelloWorld" target="_blank">HelloWorld Sample (Java)</a>

### Create a New Project

1. Open Android Studio and select New Project… in the File > New > New Project… menu to create a new project.

2. Choose the correct template for your project. In this sample, we'll use `Empty Activity`.

3. When prompted, choose your app name (`HelloWorld`) and set the Save location, Language, and Minimum SDK (21)
    >Note: With minSdkVersion set to 21, your app is available on more than 94.1% of devices on the Google Play Store (last update: March 2021).

### Include the Library

Add the SDK to your new project. Please read [Add the Libraries](#add-the-libraries) section for more details.

### Initialize the License

1. Initialize the license in the file `MainActivity.java`.

    ```java
    import com.dynamsoft.license.LicenseManager;
    public class MainActivity extends AppCompatActivity {
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
            LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9",  this, (isSuccess, error) -> {
                if (!isSuccess) {
                    error.printStackTrace();
                }
            });
        }
    }
    ```

   >Note:  
   >  
   >- The license string here grants a time-limited free trial which requires network connection to work.
   >- You can request for a 30-day trial license via the <a href="https://www.dynamsoft.com/customer/license/trialLicense?product=dlr&utm_source=guide&package=android" target="_blank">Customer Portal</a>. Offline trial license is also available by <a href="https://www.dynamsoft.com/contact/" target="_blank">contacting us</a>.
   >- If you download the <a href="https://www.dynamsoft.com/survey/dlr/?utm_source=docs" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

### Initialize Code Parser And Parse the Code Bytes

1. Import and initialize the `CodeParser`.

    ```java
    import com.dynamsoft.dcp.CodeParser;
    public class MainActivity extends AppCompatActivity {
        private CodeParser mParser;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            ...
            mParser = new CodeParser(this);
        }
    }
    ```

2. In the Project window, open **app > res > layout > `activity_main.xml`**, create a "Parse" button control under the root node.

    ```xml
    <Button
        android:id="@+id/btn_parse"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="50dp"
        android:text="Parse"
        android:textAllCaps="false"
        android:textSize="20sp"
        android:backgroundTint="@android:color/holo_blue_dark"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />
    ```

3. Parse the code bytes when the user clicks the "Parse" button. Here we use the passport MRZ string as an example.

    ```java
    public class MainActivity extends AppCompatActivity {
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            ...
            final String passportMRZStr = "P<D<<ADENAUER<<KONRAD<HERMANN<JOSEPH<<<<<<<<1234567897D<<7601059M6704115<<<<<<<<<<<<<<<2";

            Button ParseButton = findViewById(R.id.btn_parse);
            ParseButton.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View view) {
                    new Thread(() -> parseCode(passportMRZStr.getBytes())).start();
                }
            });
        }

        private void parseCode(byte[] codeBytes) {
            try {
                ParsedResultItem parsedResultItem = mParser.parse(codeBytes, "");
                showResults(parsedResultItem);
            } catch (CodeParserException e) {
                e.printStackTrace();
            }
        }
   }
   ```
  
   >Note:
   >- Check out the complete <a href="https://www.dynamsoft.com/code-parser/docs/core/code-types/" target="_blank">supported code types and fields </a>for details.

### Display Parsed Results

1. Display the parsed result(s) in an alert dialog box.

    ```java
    public class MainActivity extends AppCompatActivity {
        ...
        private void showResults(ParsedResultItem item) {
            StringBuilder result = new StringBuilder();

            for (HashMap.Entry<String, String> entry : item.getParsedFields().entrySet()) {
                String key = entry.getKey();
                String value = entry.getValue();

                result.append(key).append(":").append(value).append("\n");
            }

            runOnUiThread(() -> {
                new AlertDialog.Builder(this)
                        .setTitle("Result")
                        .setMessage(result.toString())
                        .setPositiveButton("OK", null)
                        .setCancelable(true)
                        .show();
            });
        }
    }
    ```

### Build and Run the Project

1. Select the device that you want to run your app on from the target device drop-down menu in the toolbar.

2. Click the **Run app** button, then Android Studio installs your app on the connected device and launches it.

You can also download the full source code of all the steps above:

- <a href="https://github.com/Dynamsoft/code-parser-mobile-samples/tree/main/android/HelloWorld" target="_blank">HelloWorld Sample (Java)</a>
