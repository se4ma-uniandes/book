# 1.2 There is more than one type of mobile app

---

<p align="center">
<img width="600" src="https://blog.phonehouse.es/wp-content/uploads/2016/08/android-vs-ios-love.jpg"/>
</p>

Nowadays, there are two dominant platforms in the mobile market: Android and iOS. Each of those platforms include their own operating system (OS), APIs, programming languages, SDK (Software Development Kit), IDE, backend services, online market, and devices. Let us briefly describe each platform:

**Android:** _Google's Open source platform for mobile app development. The OS is know as Android, which is a fork of Linux. Android follows a tier-based stack that includes a virtual machine (DVM or ART) for compiling Java code to DEX code. The official IDE is the "Android Studio" and the apps are published through the Google Play market (http://play.google.com). There are unofficial IDEs (e.g., IntelliJ) and markets. The Android apps are packaged as .APK files. Nowadays, Kotlin is the official language for native development (https://kotlinlang.org), and Dart is the suggested official one for cross-platform development (https://www.dartlang.org/). Note that Java is still supported as a native language for Android. The Android OS in some cases is customized by OEMs, for instance, the Android OS version used by Huawei devices which is called EMUI.

**iOS:** _Apple's closed platform for mobile app development. The OS is called iOS and is a son of UNIX (yes !!, pure power); in particular, the iOS kernel is the Darwin OS. iOS apps are only developed with the official IDE (XCode) and are restricted to be published only via the App Store market (https://www.apple.com/ios/app-store/). The iOS apps are packaged as .IPA files. To program iOS apps you need to learn the Swift or Objective-C languages._  

> In following chapters you will learn more about the mobile OSs.

Thanks to all the gods because we have only two-dominant platforms for mobile development!! Can you imagine the magnitude of the fragmentation problem with more than two platforms? Each platform has their own way for creating a mobile app. In addition to specific languages, APIs, SDKs, and IDEs, each platform has their own programming model, and the devices has their own features. Even there are different programming models for each platform, for example the swift UI model introduced in iOS 12 vs classic MVC programming supported until iOS 11.  

Let's clarify the meaning of native app.  Mobile applications are **native** when the development process is based on the languages, APIS, SDKs, IDEs, and programming models of each platform. Being a **native app** means that the app has access (through the APIs) to the hardware components in the device and specific features of each platform. Native apps provide the users with the best user experience but also are the most expensive ones to implement because you have to do double work: design/program/test the Android app, and design/program/test the iOS app. There is an additional drawback: **behavioral consistency**; it is possible that some features offered in one platform are not in the other, and it is possible that the releases in both markets are not aligned (in terms of time and features).

> Everything would be awesome if you could create a single mobile app, like a boss, that works in both platforms !! ¿what do you think? Check the next section.
