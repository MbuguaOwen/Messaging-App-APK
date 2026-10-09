# Achat with Brenda Demo

A phone-sized Android demo that creates a fictional activity preview. The preview always carries the label **DEMO — NOT A PAYMENT CONFIRMATION**. It has no payment provider integration, real recipient lookup, generated transaction reference, account balance, SMS permission, or network permission.

## Build and install the APK

The debug APK is at `app/build/outputs/apk/debug/app-debug.apk`. To rebuild after changing the interface, open this folder in Android Studio and choose **Build > Build App Bundle(s) / APK(s) > Build APK(s)**. The project compiles against API 37 and targets API 36.

To install it on an Android phone, copy the APK to the device and open it from the Files app. Android may ask you to allow installs from that source; approve it for the file manager you used, then tap **Install**. The app is a local UI simulation: it does not connect to a mobile-money provider, send SMS, or move funds.
