Mobile Sentinel
===============

Mobile Sentinel is an Android App that allows you to detect vulnerabilities in deployed LTE and (future) 5G networks. With the current release, Mobile Sentinel focuses on the detection of the ReVoLTE vulnerability  (www.revolte-attack.net). Mobile Sentinel requires a Qualcomm based  Android phone with root access as it builds upon the Qualcomm's mdlog tool.  

The application includes:
 - An automized test run to detect the ReVoLTE vulnerability
 - A logging view to capture cellular traffic (currently RRC only) and view protocol messages in-app
 - Writing the captured traffic into PCAP files
 - Upload function of logs to an http server (under development)
 
 
## Installation
Download the latest APK build from [here](https://github.com/RUB-SysSec/mobile_sentinel/releases/download/1.0/MobileSentinel.apk) and install it directly on the device. 

```
adb install MobileSentinel.apk
```

Alternatively, the app can be installed directly from the device's file system.

## Settings

-  Configure Log Upload Setting: This setting allows you to change the behavior for uploading the log files to the server. Options: 
   - Ask for Upload: Will ask after each test run if you would upload the data (Default).
   - Never Upload: Will never upload the logs.
   - Always Upload: Will always upload the logs.
-  Change Call Number: This setting allows you to change the phone number that is called for testing. *Important note: there may be a risk of expense.* Default number is a german phone number.  

## Build instructions

You can build the application from source as well however, you will need a [Chaquopy SDK](https://chaquo.com/chaquopy/license/) license to be able to deploy the app outside of Android Studio.


## Requirements
 
- Rooted Android Phone with a Qualcomm Baseband
- The phone AND the used SIM Card must support VoLTE
- Currently requires minimum Android Pie (9.0)

*Make sure to grant Superuser rights to the application and accept the requested permissions, as the application will not work without.*

## Tested Devices
 - Xiaomi Mi A3 (Android 9.0)
 - One Plus 6T (Android 9.0)
 - Xiaomi Mix 3 5G (Android 9.0)

## Used Libraries 
Mobile Sentinel uses the following libraries: 
 - [Chaquopy SDK](https://chaquo.com/chaquopy/license/)
 - [SCAT](https://github.com/fgsect/scat)
 - [Pycrate](https://github.com/P1sec/pycrate)

## Known Bugs

- Some phones with a Qualcomm baseband do not allow extracting cellular network traffic from the DIAG interface
