# 12.7 More resources about performance-related practices
\(By Mario Linares-Vásquez, Laura Bello, Sergio Velásquez, Santiago Cortés, Juan Santiago Acevedo and Juan David Cruz\)
___

As a nice closing for this chapter, we have prepared a list of recommended videos, and recommended libraries that could help you to improve your performance bugs exterminator skills. 

**Android**

The following are videos from the Google Developers YouTube channel:
- [Memory Performance 101](https://goo.gl/NY3wCh)
- [Garbage Collection in Android](https://goo.gl/6f9ABF)
- [App Launch time 101](https://goo.gl/aQ97Nf)
- [Understanding Android Threading](https://goo.gl/3Ezqzo)
- [Memory & Threading](https://goo.gl/sUg83z)
- [Removing unused resources](https://goo.gl/R3We1q)
- [Perf Theory: Batching](https://goo.gl/aK2BmB)
- [Caching UI data](https://goo.gl/PBkaac)
- [To Index or Iterate?](https://goo.gl/hm8VEA)
- [Re-using Bitmaps](https://goo.gl/yQEd8K)
- [Battery Drain and Networking](https://goo.gl/uRbjKu)
- [The Performance Lyfecycle](https://goo.gl/d2ihHE)
- [Overdraw](https://goo.gl/RWVai3)
- [Battery Drain and Wakelocks](https://goo.gl/hehSph)
- [Memory Leaks](https://goo.gl/vgWZMR)



Also, there are many third-party libraries for Android but several of them are "must have" libraries that are extremely popular and often used in almost any Android project. Some of those major libraries are:

| Name | Description |
| :--- | :--- |
| [Retrofit](https://github.com/codepath/android_guides/wiki/Consuming-APIs-with-Retrofit) | A type-safe REST client for Android which intelligently map an API into a client interface using annotations. |
| [Glide](https://github.com/codepath/android_guides/wiki/Displaying-Images-with-the-Glide-Library) | A powerful image downloading and caching library for Android. |
| [ButterKnife](https://github.com/codepath/android_guides/wiki/Reducing-View-Boilerplate-with-Butterknife) | Using Java annotations, makes Android development better by simplifying common tasks. _Might Be replaced by Kotlin Synthetic Variables of _[_Kotlin Extensions_](https://kotlinlang.org/docs/tutorials/android-plugin.html) |
| [Parceler](https://github.com/codepath/android_guides/wiki/Using-Parceler) | Android Parcelable made easy through code generation |
| [IcePick](https://github.com/frankiesardo/icepick) | Android Instance State made easy |
| [LeakCanary](https://github.com/square/leakcanary) | Catch memory leaks in your apps |
| [Espresso](https://github.com/codepath/android_guides/wiki/UI-Testing-with-Espresso) | Powerful DSL for Android integration testing |
| [Robolectric](https://github.com/codepath/android_guides/wiki/Unit-Testing-with-Robolectric) | Efficient unit testing for Android |

When using libraries, you must keep in count that Android has some restrictions on its method count \(65535 method limit\). So, unless you are really going to squeeze the functionalities out of a library, you should not use it and instead build the functionality by yourself.

Let's say we want to load an image in our "Hello World" app using Glide. As with most dependencies, pulling Glide into a Gradle project is a single liner into your **build.gradle** file:

```
dependencies {
    ...
    implementation 'com.github.bumptech.glide:glide:4.6.1'
    annotationProcessor 'com.github.bumptech.glide:compiler:4.6.1'
}
```

Make sure you use the key "implementation" instead of "compile", which was the rule before Android Studio 3.0.

**iOS**


- [iOS Memory Deep Dive - WWDC 2018](https://developer.apple.com/videos/play/wwdc2018/416)

- [Optimizing App Assets - WWDC 2018](https://developer.apple.com/videos/play/wwdc2018/227) 

- [Images and Graphics Best Practices - WWDC2018](https://developer.apple.com/videos/play/wwdc2018/219)

- [Practical Approaches to Great App Performance - WWDC 2018](https://developer.apple.com/videos/play/wwdc2018/407)

- [Optimizing Your App for Today’s Internet - WWDC 2018](https://developer.apple.com/videos/play/wwdc2018/714/)

Also, there are many libraries that could help you in your project. Here is a list of some important ones:

| Name | Description |
| :--- | :--- |
| [RestEssentials](https://github.com/sean7512/RestEssentials) | Is a lightweight REST and JSON library for Swift  |
| [MBProgressHUD](https://github.com/jdg/MBProgressHUD)   | Is a really useful library to make loading dialogs.  |
| [Reachability.swift](https://github.com/ashleymills/Reachability.swift)   | Lets you know the connectivity state of your phone, you can the internet network status, the wifi status, etc...  |
| [Cosmos](https://github.com/evgenyneu/Cosmos)   | A star rating control for iOS  |
