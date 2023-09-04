# 8.3 Hello Jetpack, my new friend...
\(By Santiago Cortés-Fernández\)

___

As defined on the Android Developers website, 

> _Jetpack_ is a collection of Android software components to make it easier for you to develop great Android apps. These components help you follow best practices, free you from writing boilerplate code, and simplify complex tasks, so you can focus on the code you care about [(Android Developers)](https://developer.android.com/jetpack/?gclid=Cj0KCQiAp7DiBRDdARIsABIMfoClEuGfoKG2ch_Qt-q2mb5SnLYTZZaMBp4A9bzG7Qq6TCNsOGvQ_zMaAnTGEALw_wcB).

In other words, _Android Jetpack_ is a collection of software components that were realesed in 2018 as a way to facilitate the development of Android applications. For example, as it was said in the previous section, Android apps can now be easily implemented using the _MVVM_ architectural pattern thanks to the _Jetpack components_. In addition to this, _Jetpack_ also counts with some other package libraries that aim to help developers to reduce boilerplate code, accelerate the development of apps, take advantage of _Kotlin language_, amonst some other very interesting functionalities.

{%youtube%}LmkKFCfmnhQ{%endyoutube%}

Furthermore, as the image below depicts it, there are four current components that constitute _Android Jetpack_ for developing high quality applications, with their own specific purpose and features.

<p align="center">
<img width="80%" src="https://cdn-images-1.medium.com/max/1600/1*FB931aBGoALv3OLY5LSRGg.png" alt="Android Jetpack Components: Achitecture, UI, Foundation and Behaviour"/>
</p>

## UI

The _UI_ components provide widgets and helpers that aim to improve the interactions that users have with Android applications. Among these components, some of the most interesting ones, which can be very useful to facilitate the development of the project and contribute significantly to the users experience, are:

* [Animation and Transition](https://developer.android.com/training/animation/): Used (as you imagined) for moving widgets and to create transitions between screens.

* [Fragments](https://developer.android.com/guide/components/fragments): Represents a behaviour or portion of the user interface, used for dynamic and flexible UI designs (and to reduce boilerplate layouts and code).

* [Layouts](https://developer.android.com/guide/topics/ui/declaring-layout): Are used for creating and designing the structure of the user interface.

* [Palette](https://developer.android.com/training/material/palette-colors): Used for designing layout themes and to apply custom colors to the elements of the app.
  
* [Wear OS by Google](https://developer.android.com/wear): Components created to help develop apps for Wear.
  
## Behaviour

The _Behaviour_ components are oriented to help developers with the integrations of standard Android services. Some of this components are:

* [Notifications](https://developer.android.com/guide/topics/ui/notifiers/notifications.html): Providing a notification API that also works with Wear.

* [**Permissions**](https://developer.android.com/guide/topics/permissions/index.html): Needed to request permission to access sensitive data from users (contacts, camera, multimedia, etc.).

* [**Preferences**](https://developer.android.com/guide/topics/ui/settings): Used to create interactive settings for the user to choose (some of) the overall functionality and behaviour of an application.

* [Media & Playback](https://developer.android.com/guide/topics/media-apps/media-apps-overview.html): Backwards compatible APIs for media playback and routing.

## Foundation

The _Foundation_ components provide _cross-cutting_ functionalities such as:

*[AppCompat](https://developer.android.com/topic/libraries/support-library/packages.html#v7-appcompat): Are support libraries which help applications developed in newer versions to work with older versions.

* [Testing](https://developer.android.com/topic/libraries/testing-support-library/index.html): As the name says it, this components give developers a set of testing tools to verify an aplication's correctedness, funcionality, etc.
  
* [Kotlin Support](https://developer.android.com/kotlin/ktx.html): A set of _Kotlin_ extensions to help with a consice and pleasant app development using the _Kotlin language_

## Architecture

The _Architecture_ components are used by developer to design robust, testeable and maintainable applications. Amongst all the elements that compose this _Android Jetpack_ component, it contains all the necessary elements to implement a fully lifecycle-aware application with the _MVVM_ architectual pattern. 

> Check our [guide](https://uniandes-se4ma.gitlab.io/guias/KOTLIN/guia3_kotlin.html) describing the main architecture components to start developing an Android application with the help of _Android Jetpack_.


___

> Check the following [link](https://developer.android.com/jetpack) to learn more about _Android Jetpack_!

> To have a better understanding of how Jetpack libraries are developed, tested, packageed, versioned and released (It could be quite helpful) check this [link](https://developer.android.com/jetpack/androidx) to learn about _AndroidX_

> Check the Android Architecture Components [guide](https://developer.android.com/jetpack/docs/guide) to learn more about how to implement MVVM in Android.


