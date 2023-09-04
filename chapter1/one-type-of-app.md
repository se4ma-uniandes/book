# 1.4 ... one type of app

---

Have you heard about frameworks such as React native, Cordova, Xamarin, PhoneGap, Ionic, or Telerik? These frameworks allow developers to write a mobile app "once" and have it ready for multiple platforms.  So, there is another type of mobile apps called **cross-platform** apps. This is very cool because you do not have to learn the specific APIs of each platform. But you have to learn the "high-level" language used by the cross-platform framework, and obviously  you have to use the corresponding infrastructure (SDK, IDE, etc.).

There are two flavors of cross-platform apps: hybrid and cross-platform native. The former type of app (i.e., hybrid) combines the native and mobile web worlds by creating a native "wrapper" that renders HTML5 and CS, and interprets JS; the latter (cross-platform native) compiles the apps directly to native code. In both cases at the end you have an app that can be installed on a device, but, the key difference with native apps is the limitations that hybrid apps have.

In hybrid apps, the wrapper is a native thin container that provides the apps with access to "some" of the native features. This is like the cyborg character from DC comics, in which there is a human part and a machine part. In hybrid apps there is a native part and a web app part. This hybrid nature is possible thanks to the [Apache Cordova](https://cordova.apache.org) project that serves as a middleware between the native platform (i.e., Android and iOS) and HTML/JS-based world.

 The web part of a hybrid app can be embedded in the app (i.e., downloaded to the device as part of the app), or can be accessed remotely because the native container is also a browser. Note that in hybrid apps the look-and-feel is provided by the web part and the performance is highly dependent on the internet connection (if the web resources are not embedded in the container). Examples of frameworks for building hybrid apps are [Trigger.io](https://trigger.io "Trigger.io"), [Ionic](https://ionicframework.com "Ionic"), and [Adobe PhoneGap](https://phonegap.com).

The second choice in the "cross-platform" world are the frameworks that compile directly to native code (e.g., [Flutter](https://flutter.dev),  [React native](https://facebook.github.io/react-native/ "React native"), [Kotlin/native](https://kotlinlang.org/docs/reference/native-overview.html), and [Native Script](https://www.progress.com/nativescript "Native script")). These frameworks are a pretty good choice for reducing the development time. However, not all the mobile-platform specific features can be directly expressed in the cross-platform languages.

> Being knowledgeable of cross-platform frameworks is one of the skills highly demanded by mobile app development companies. Remember this is not a programming course, but, we recommend you to learn one the frameworks by yourself. These two articles describe how [Flutter](https://medium.com/@ralfgehrer/how-flutter-works-under-the-hood-and-why-it-is-game-changing-2335954a5bfc) works, and how [React Native](https://medium.com/we-talk-it/react-native-what-it-is-and-how-it-works-e2182d008f5e) works.

In summary, there are three types of mobile apps you can develop: native, mobile web, and cross-platform/hybrid. In the internet you will find different articles discussing the pros and cons of each type.

>Hint: you should be prepared for midterm questions regarding the pros/cons of each type of mobile app.
