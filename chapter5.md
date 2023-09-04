# Chapter 5: A GUI is better than two thousand words
\(By Mario Linares-Vásquez, Mariana Villamizar, Juan Santiago Acevedo, Gustavo Alegría, and Sergio Velásquez\)

---

Mobile apps are user-interaction driven, because the user interacts with the app through the GUI, gestures and sensors. The context canvas, the VD-map, and the scenarios description are not focused on the app GUI. Therefore, there is still a missing element in our mobile app development toolbox, because there is no way to have an app without a GUI.
> Actually it is possible to have mobile apps without GUIs. This type of applications have background services or broadcast receivers that are running in background (on the device) and do not react to GUI actions, because there is no GUI, but react to other actions as system calls, intents, or other events.

OK, lets rephrase it, there is no way to have a GUI-dependent app without a GUI. Consequently, during all the design thinking steps it is really important to take into account the GUI of your mobile apps, because mobile apps are a particular type of software that are highly-dependent on the GUI.

Now, the question is how to design the GUI of a mobile app. The answer is that there are a lot of artifacts and tools. However, the most important elements to have in mind are the design metaphors promoted by each platform. **A metaphor is a shared language, a set of principles of style, branding, and defined interactions, that aims to give guidelines on how you should make your design.**    

For instance, in the particular case of Android apps, the design metaphor is called  **"Material Design"**. You can see all the metaphor documentation in [Material io](https://material.io/guidelines/#).

Material Design is inspired in tactile and physical qualities of materials (paper and
ink), including physical laws of movement. It emphasizes on user actions to ensure that
main functionality is clear, because user actions are reflected naturally in the GUI. Check the following video to get an idea of material design.

{%youtube%}cQzien5H2Do{%endyoutube%}

_(Video by Google Design available at [YouTube](https://www.youtube.com/watch?time_continue=45&v=cQzien5H2Do). The video is published under the Standard YouTube license )_

The composition foundations are geometric forms based on circles, squares, diagonal and orthogonal strokes, in a three-dimensional space in which the light and the shadows reflect the elevation of the elements that make up a view.

But, what is elevation? Material design was thought in a three-dimensional space, in which the components are located at some place in the three axis. There is a key value for the components called elevation, that reflects the component position in the Z-axis. When a user interacts with a component it is reflected by changing the position of the component in the Z-axis. How is it possible to do that? Using shadows and light.

Material Design is not just a set of rules that someone came up with. It is the result of a set of experiments on how we as people relate to objects, and how we can take advantage of the phone screen to not only show elements to the users, but also to let them feel how they can interact with the elements. Watch the following video about how material design was developed.

{%youtube%}rrT6v5sOwJg{%endyoutube%}

_(Video by Google Design available at [YouTube](https://www.youtube.com/watch?v=rrT6v5sOwJg). The video is published under the Standard YouTube license )_

In the case of **iOS**, the design is based on specific **[Human interface guidelines](https://developer.apple.com/ios/human-interface-guidelines/overview/themes/)** that are close to a **"Flat Design"** metaphor.

There are three essential characteristics of the iOS design metaphor:

- **Clarity:** Legible text at every size, lucid an precise icons, and design motivated on functionality.

- **Deference:** Fluid motion and a crisp interface help people understand and interact with content while never competing with it.

- **Depth:** Distinct visual layers and realistic motion hierarchy facilitate understanding. Transitions provide a sense of depth as you navigate through content.

The iOS metaphor tries to follow an "intentional design"; when designing for iOS you should always keep a focus on the people that you are designing for. You will want to create apps that feel simple, that make the users believe that the app is an extension of what they already know. You need to create comfort and confidence; to do that you should take into account the following five elements of intentional design:

- **Radical Simplification:** The UI could be as simple as one screen with one functionality, it does not matter if it is enough to fulfill the app's goal.

- **Deep Understanding:** Understand the real problem, do not just assume that you know everything. Try to get to the why, and create solutions that will answer the real problems.

- **Extreme Focus:** What might seem as extreme case could be the point or focus to redesign your solution.

- **Personal Connection:** Try to find ways of recreating feelings. Think of how the way a user relates with your app is a reminiscence of some feelings or moments.

- **Direct Communication:** Draw on what people already know, be as clear and specific as possible, try not to make the user doubt about what your app does.

> Check the Intentional Design video from the WWDC18:
https://developer.apple.com/videos/play/wwdc2018/802/

Metaphors exist so that you can rely on them to extend the utility or value of your app. It is not about following some rules so that every app is perfectly design; it is about understanding the capabilities of the platform you are building your app upon.

Note that the metaphor/guidelines also come with a specific set of GUI components; thus, having a generic design that is expected to work in both platforms is a hard task to achieve, because there is a difference on how an app will look in the two platforms. One way to achieve GUI consistency across platforms is by implementing mobile web or hybrid apps instead of native apps. Another option is to design the app by considering only the GUI components that are mirrored in both platforms (e.g., button); however, this option limits the user experience on each platform.
