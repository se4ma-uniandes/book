# 2.4 Accessibility in mobile apps

---
Mobile devices are the most personal devices nowadays. Thus, devices and apps should be designed for everyone. One step toward this ideal is to introduce accessibility features in your apps. The mobile development platforms provide accessibility features for users with different disabilities such as vision loss and hearing loss. ¿So, why do not you take a look to the accessibility features of your preffered mobile platform?. Here we give you a brief of the accessibility capabilities in iOS and Android, but once you start to build your apps it is better you have a deep knowledge of the guidelines and frameworks.

> For more information on accessibility features in iOS you can check https://www.apple.com/accessibility/; for Android go to https://developer.android.com/guide/topics/ui/accessibility/

<br>
**iOS.** Accessibility is one of the principles Apple cares about, therefore, the Apple platform for mobile apps provides developers with different accessibility features that are inherent to the operating system. These features can be included into iOS apps with little effort, because the features are provided by the UIKit and MediaKit libraries.

> In iOS, the *Kits are the frameworks available for programming iOS apps. For example, the UIKit is the one with the APIs for the user interface.

 

Some of the accessibility features that can be used in iOS apps are:

- _VoiceOver_: it is a gesture-based "screen reader". VoiceOver allows users to listen an audible version of the alternative text defined for UI components (yes the alternative text matter) when the component is touched or swapped. VoiceOver is a very nice feature for helping people with vision disabilities to understand what is on the GUI and how to navigate it. Whatever you put in the alternative text is voiced when the VoiceOver feature is enabled in the device. So, remember to always add alternative text to the GUI components.

- _Adaptable GUI_: apps with GUI components from UIKit are automatically adapted to accessibility preferences. It means, that no extra effort is required for adapting the GUI when the user choose to zoom-in, adjusts the fonts, invert colors, among others preferences.


- _Siri and Dictation_: the former can be integrated into your apps to use voice input to control features; the latter converts user words into text. There is also a "Type to Siri" feature available since iOS 11. 


**Android.** The mobile platform of the green robot also has accessibility APIs and services for universaly designed apps: TalkBack, VoiceAccess, Text-to-Speech, and SwitchAccess. TalkBack is similar to the VoiceOver feature in iOS; VoiceAccess allows users to control the device with spoken commands; Text-to-Speech synthesizes voice from text; and SwithAccess allows users to interact with Android devices using external hardware (e.g., switches, or keyboards). Something very cool in Android are the Lint and Accessibility Scanner tools that statically analyze your app and look for potential violations to accessibility guidelines.

