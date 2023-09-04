# 10.2 How to handle it on Android
\(By Camilo Escobar-Velásquez, Claudia Bedoya, Michael Osorio\)

---
<p align="center">
<img width="100%" src="/assets/christian-erfurt-1131100-unsplash.jpg"/>
</p>

_(Photo by Christian Erfurt on [Unsplash](https://unsplash.com/photos/sxQz2VfoFBE))_

## Connection Status

Most of the issues found are related to not verifying the state of connection before performing an action. This leads to various errors and exceptions that, when left unhandled, cause the application to crash or interrupt its execution. The current connection status can be obtained using the ["Connectivity Manager"](https://developer.android.com/reference/android/net/ConnectivityManager). The correct verification of connection status can prevent errors from several categories. For example, in BA issues, if the connection is previously verified, the request would not be executed until there is a properly established connection. Another example is the Map Component that belongs to Google Maps. It uses an API in order to display a map as a Fragment, however, it does not provide a mechanism to handle the lack of connection to retrieve map information. Therefore, when using this component without connection a blank map will be shown.

Other examples are applications that retrieve images directly from the Internet. In this specific case, applications must check for connectivity before retrieving images/text, and if there is no connection they must react to display a message or not allowing the activity transition until a connection is established.

## Library Handling

#### Correct use of callbacks

Most of the libraries that provide HTTP services use callbacks functions, so it is important to use wisely the error callback to provide a great user experience. Additionally, if the backend service is not managed by the developer, it is important to fully understand the default values used by the library as a response when no result was found. Therefore, if there is an error or the response is the library's default value, the app could react correctly, and no execution break will happen. This way, BA issues can be avoided.

#### Thread Handling

When using libraries to connect to a backend service, it is important to understand how responsibilities are delegated. Some of the libraries delegate the management of threads to developers. Additionally, is worth noting that heavy processes must be performed in a secondary thread in order to improve the user experience, by allowing it to trigger other actions while the first action is performed. Therefore, if actions are correctly delegated, the user must experience a clean behavior (i.e. without delays, messages that tell the user about action delegation, etc.)

#### Map Libraries

Using the GoogleMaps component is not the only way to display maps in Android applications. Some libraries allow developers to improve the map experience: custom themes or layers. However, those libraries retrieve the information from an API that would have to be consumed. Therefore, it is important to be aware of the multiple problems these libraries could have. Even more important, it is crucial for the app to communicate to the user all context values to allow him to know what is being shown. For example, if the app downloads a shell map that is used as a default map when there is no connection, the user must not be expecting the map to respond to specific actions like zooming.


## Android Components

For this research, all actions are related to connectivity. For this reason, if there is an error, it is important to hide all visible progress notifications and replace them with a mechanism that informs the user about what happened. So be careful when using Android Core Components that inherently provide connection-related services. For example, the SwipeRefreshLayout component allows the user to use, as its name says, a "Swipe-down" gesture to refresh the GUI. This behavior is managed by overwriting "onRefresh()" method that is called each time the user "refreshes" the GUI. However, while the application process the refresh action, the SwipeRefreshLayout displays a progress notification that disappears only after "setRefreshing(false)" method is called. Therefore, if the process made in "onRefresh()" fails and the "setRefreshing(false)" method is not called, a progress notification will be displayed to the user until another refresh is performed with success.

Another example is the WebView component that provides a method called "WebViewClient.onReceivedError". This method is triggered when the embedded web page finds an error. Normally the errors are related to not being able to load content. However, that error could also be related to a lack of connectivity.

## Informative Messages

One of the most common issues found in this research (103 of 316 issues) is related to messages that do not provide the correct information when displayed. Those issues can be avoided having in mind the following pieces of advice:

- Exception Messages unless they are created by developers, must not be included in the error message shown to the user. Most of the time users do not know the meaning of exceptions messages like: "IndexOutOfBoundsException, NullPointerException, etc".
- The words used in the messages must take into account the user's context. It is important to avoid using technical words (\eg server, exception, connection error, \etc). This will provide a natural behavior to the users that will improve the user experience.
- Messages displayed to the user must be as meaningful as possible. Therefore, reusing messages in various parts of the application is discouraged because that could lead to misunderstandings (in order to reuse them, they must be generic and may not provide enough information for the user to understand the problem/situation.)

## User content actions

In order to improve user experience, all actions that manage user-generated content must be queued to avoid losing valuable information. In this way, all actions that could not be executed remain in the queue and when a connection is established they can be triggered again. However, it is important to show to the user that its content has not been send/processed yet but it is stored for future action. This way user knows there is a connection problem but its content is "save" from being lost.

## Notifications

Android Developers Guide (ADvG) recommends using notifications for foreground services. Nevertheless, it is important to notify all possible events that are meaningful for the user. For example, when the service is going to start, the current progress of the service (if it is possible), when an error occurs, if the user must trigger the action again, if the service has ended successfully, etc. Notifications, as presented by ADvG, are shown at the top of the screen and have several sections that can be modified as the notification title. However, events as the start of the service can be shown using a "Toast" component. The standard implementation of Android Notifications uses "NotificationCompact" APIs from the [Android Support Library](https://developer.android.com/guide/topics/ui/notifiers/notifications?hl=es-419).

## External Services

Mobile applications use external applications' capabilities to perform well-known actions as send an email. Therefore, delegate such actions to already installed apps improves the development process. However, it is important to take into account that those delegated actions may use connection and users might not recognize that the action is being performed by another application.

#### Web Content

Specifically, web content can be shown using the "WebView" Android component or using an installed browser. In both cases, connectivity must be verified before calling the "startActivity()" method. Furthermore, ADvG recommends as an alternative to create a progressive web app in case web content must be required more frequently or to use Chrome Custom Tabs to improve page loading, privacy protections and security.

Nevertheless, the WebView component can be used in several ways and each one could lead to its own errors. In this research, we found 3 of those ways, and all of them generated errors due to a lack of connection validation. The first one, associated to employ local web files that use external resources to correctly work, leading the app to show style-less web content or blank spaces in case of multimedia resources. Second, related to display a URL content without connection, leading the app to display a default "Webpage not available" message that contains technical information. Last, a case related to loading a local web file representing a map that ends up with a blank map due to connection status.

#### General content

When action to be performed corresponds to no web-related content such as sending an email, share content, or explore a map, already installed apps fulfill the need and can handle it. However, when the action is delegated, the main application loses control of behavior and an error in the secondary app could lead users to think the main app has failed too. Therefore, knowing those actions are still connection-related, a validation must be done to prevent part of the errors that a secondary app could have.