---
layout: default-layout
title: User Guide - Dynamsoft Code Parser SDK iOS Edition
description: This is the user guide of Dynamsoft Code Parser SDK iOS Edition.
keywords: user guide, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Dynamsoft Code Parser - iOS User Guide

- [Dynamsoft Code Parser - iOS User Guide](#dynamsoft-code-parser---ios-user-guide)
  - [Requirements](#requirements)
  - [Add the xcframeworks](#add-the-xcframeworks)
    - [Add the xcframeworks Manually](#add-the-xcframeworks-manually)
    - [Add the xcframeworks via CocoaPods](#add-the-xcframeworks-via-cocoapods)
  - [Build Your First Application](#build-your-first-application)
    - [Create a New Project](#create-a-new-project)
    - [Include the Library](#include-the-library)
    - [Initialize the License](#initialize-the-license)
    - [Initialize Code Parser And Parse the Code Bytes](#initialize-code-parser-and-parse-the-code-bytes)
    - [Display Parsed Results](#display-parsed-results)
    - [Build and Run the Project](#build-and-run-the-project)

## Requirements

- Supported OS: iOS 11 or higher (iOS 13 and higher recommended).
- Supported ABI: arm64 and x86_64.
- Development Environment: Xcode 13 and above (Xcode 14.1+ recommended).

## Add the xcframeworks

The Dynamsoft Code Parser (DCP) iOS SDK comes with four libraries:

| File | Description |
|---------|-------------|
| `DynamsoftCodeParser.xcframework` | The Dynamsoft Code Parser library, which includes code parsing logic and related APIs. |
| `DynamsoftCore.xcframework` | The core library, which includes common basic structures and intermediate result related APIs. |
| `DynamsoftLicense.xcframework` | The license library, which includes license related APIs. |
| `DynamsoftCodeParserDedicator.xcframework` | The code parser helper library, which includes some validation functions used by the SDK. |

There are two ways to add the libraries into your project - **Manually** and **Via the CocaPods**.

### Add the xcframeworks Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/survey/dlr/?utm_source=docs" target="_blank">Dynamsoft website</a>. After unzipping, four **xcframework** files can be found in the **Dynamsoft\Frameworks** directory:

   - **DynamsoftCodeParser.xcframework**
   - **DynamsoftCore.xcframework**
   - **DynamsoftLicense.xcframework**
   - **DynamsoftCodeParserDedicator.xcframework**

2. Drag and drop the above **xcframeworks** into your Xcode project. Make sure to check Copy items if needed and create groups to copy the **xcframeworks** into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all the **xcframeworks**.

### Add the xcframeworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```pod
   target '{Your project name}' do
     use_frameworks!

     pod 'DynamsoftCodeParser','2.0.20'
     pod 'DynamsoftCodeParserDedicator','1.0.0'
     pod 'DynamsoftCore','3.0.20'
     pod 'DynamsoftLicense','3.0.20'

   end
   ```

2. Execute the pod command to install the frameworks and generate workspace(**{TargetName}.xcworkspace**):

   ```bash
   pod install
   ```

## Build Your First Application

The following sample will demonstrate how to create a simple `HelloWorld` app for parsing text or bytes.

>Note:
>
>- The following steps are completed in XCode 14.2
>- View the entire Swift source code from [HelloWorld(Swift) sample](https://github.com/Dynamsoft/code-parser-mobile-samples/blob/main/ios/HelloWorld/)

### Create a New Project

1. Open XCode and select New Project… in the File > New > New Project… menu to create a new project.

2. Select **iOS -> App** for your application.

3. Input your product name (HelloWorld), interface (StoryBoard) and language (Objective-C/Swift)

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Include the Library

Add the SDK to your new project. Please read [Add the xcframeworks](#add-the-xcframeworks) section for more details.

### Initialize the License

1. Use the `LicenseManager` class and initialize the license in the file **AppDelegate**.

    ```swift
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate:self)
        return true
    }
    func onLicenseVerified(_ isSuccess: Bool, error: Error?) {
        if(error != nil)
        {
            if let msg = error?.localizedDescription {
                print("Server license verify failed, error:\(msg)")
            }
        }
    }
    ```

    >Note:  
    >  
    >- Network connection is required for the license to work.
    >- The license string here will grant you a time-limited trial license.
    >- If the license has expired, you can go to the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs&product=dcp&package=mobile" target="_blank">customer portal</a> to request for an extension.

### Initialize Code Parser And Parse the Code Bytes

1. Import and initialize the `CodeParser`.

    ```swift
    import UIKit
    import CodeParser
    class ViewController: UIViewController {
        private let codeParser = CodeParser()

    }
    ```

2. Add a "Parse" button on the UI.

    ```swift
    class ViewController: UIViewController {
        ...
        lazy var parseButton: UIButton = {
            let left = 120.0
            let width = UIScreen.main.bounds.size.width - 2 * left
            let height = 50.0
            let top = UIScreen.main.bounds.size.height - 50.0 - height
            let button = UIButton(frame: CGRectMake(left, top, width, height))
            button.backgroundColor = .darkGray
            button.setTitle("Parse", for: .normal)
            button.setTitleColor(.white, for: .normal)
            button.layer.cornerRadius = 6.0
            button.titleLabel?.font = UIFont.systemFont(ofSize: 20.0)
            button.addTarget(self, action: #selector(parseCode(_:)), for: .touchUpInside)
            return button
        }()
        
        override func viewDidLoad() {
            super.viewDidLoad()
            self.view.addSubview(parseButton)
        }
    }
    ```

3. Parse the code bytes when the user clicks the "Parse" button. Here we use the passport MRZ string as an example.

    ```swift
    class ViewController: UIViewController {
        ...
        @objc private func parseCode(_ button: UIButton) -> Void {
            let passportMRZStr = "P<D<<ADENAUER<<KONRAD<HERMANN<JOSEPH<<<<<<<<1234567897D<<7601059M6704115<<<<<<<<<<<<<<<2"
    
            let data = passportMRZStr.data(using: String.Encoding(rawValue: NSUTF8StringEncoding))
    
            guard data != nil else {return}
            
            let dcpResultItem = try? self.codeParser.parse(data!, taskSettingName: "")
            
            showResults(dcpResultItem)
        }
    }
    ```
  
   >Note:
   >- Check out the complete <a href="https://www.dynamsoft.com/code-parser/docs/core/code-types/" target="_blank">supported code types and fields </a>for details.

### Display Parsed Results

1. Display the parsed result(s) in an alert dialog box.

    ```swift
    class ViewController: UIViewController {
        ...
        private func showResults(_ item: ParsedResultItem?) -> Void {
            if item != nil {
                guard let parsedFields = item?.parsedFields else { return }
                
                var result = ""
                for (key,value) in parsedFields {
                    result += "\(key):\(value)\n"
                }
                
                let alterController = UIAlertController(title:"Result", message: result, preferredStyle: .alert)
                let okAction = UIAlertAction(title:"OK", style: .default, handler: nil)
                alterController.addAction(okAction)
                
                present(alterController, animated: true, completion: nil)
            }
        }
    }
    ```

### Build and Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

>Note:
>
>- You can get the source code of the HelloWord app from the following link
>- View the entire Swift source code from [HelloWorld sample](https://github.com/Dynamsoft/code-parser-mobile-samples/blob/main/ios/HelloWorld/)
