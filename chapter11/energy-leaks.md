# 11.3 Energy leaks
\(By Mario Linares-Vásquez\)

<p align="center"><img width="100%" src="../assets/zoltan-tasi-681246-unsplash.jpg"/>
</p>

_(Photo by Zoltan Tasi on [Unsplash](https://unsplash.com/photos/6vEqcR8Icbs))_
___


Draining the juice of a mobile device battery is a very easy task. You only need to implement a mobile app without considering the best practices. Hardware components in a mobile device can be energy greedy if you do not use them properly, also, bad design decisions and bad coding practices can make your app a hungry and greedy energy blob. 

Some of the hardware components that have been recognized as energy greedy are the CPU, GPS, display, and Bluetooth. For example, running computationally heavy tasks on the mobile device requires energy for the CPU; therefore, always think on delegating computationally heavy tasks to a back end server/service. In OLED diplays, the choice of color palette matters because the energy consumed by the display depends on the colors painted by the display subpixels[^1], so, it is a good idea to have two versions of GUI themes that could be selected by the user (or automatically by the app) depending on the battery level: the original design and one aimed at saving energy. In the case of GPS, when requesting for location updates with high precision, forgetting to unregister the listener when an app is in background can easily drain the battery (a clear example here is the Waze app).


Programming errors and API misuses can cause high levels of energy consumption (also known as energy bugs) in mobile apps.[^2] The energy bugs have been widely studied and cataloged by the research community. Thus, you MUST be knowledgeable of the energy bugs to avoid introducing them into your apps. The mobile energy bugs at the app level can be categorized in: **no sleep bug**, **immortality bug**, **loop bug**, and **energy greedy API usages**[^2] [^3] 

**No sleep bug.** The app is keeping a hardware component awake (erroneously), which leads to an unnecessary battery drain.Typical examples here are buggy usages of the [wakelocks](https://developer.android.com/training/scheduling/wakelock) in Android and missing to unregister listeners-related to hardware components.  Examples of non-sleep bugs are: [battery drain in Twidere 3.6.24](https://github.com/TwidereProject/Twidere-Android/issues/935); [Persistent CPU wakelocks in AntennaPod](https://github.com/TwidereProject/Twidere-Android/issues/935); [Facebook 1.3 not releasing a partial wake lock](https://forums.androidcentral.com/samsung-galaxy-s4/313523-facebook-wakelock-problem.html); [Email 2.3 app keeps awake when no data connection is available](https://productforums.google.com/forum/#!category-topic/gmail/android/zAXTphqwEFo). So, do not forget to realease any lock you have on a hardware component, and release listeners as soon as you do not need them. Put special attention on the lifecycle methods in Android components and iOS AppDelegates/Controlleres, to release resources based on the app status.


> Check the "[Stuck partial wake locks](https://developer.android.com/topic/performance/vitals/wakelock)"  guide for reading about the wakelock best practices recommended by Google.

**Energy loop bug.** In this case the app or any thread in the app enters into a looping state that periodicaly executes a task that is unnecessary and leads to significant drain of the battery. Energy loop bugs can be induced by contextual/unexpected conditions such as eventual connectivity, for example, if your app has a messages queue and very frequently checks for the connectivity status before sending the message. Another example is a bad implementation of recursive calls, infinite loops inside apps aimed at checking specific conditions, synchronization issues, erroneous handling of exceptions in catch/finally blocks. A real example is a [syncing issue in Google calendar](https://productforums.google.com/forum/#!topic/calendar/_kRcIuj4c_4).

**Immortality bug.** This is probably the most weird and hard to find energy bug. Suppose that your app has an energy bug draining a device battery, the app is killed by the user, but the app is relaunched again  by the OS and the draining continues (or the app is continuously running despite being forced to close). Weird, right? Well, there are reports related to  [an immortality energy bug in Google maps](https://productforums.google.com/forum/#!topic/nexus/cMyY014d3-Q).

**Energy greedy API usages.** Some APIs are energy greedy, therefore, you must be careful when using those APIs. Some of those examples have been discovered previously with empirical studies [^2], but also recognized publicly by API developers. With some friends from William and Mary, Sannio and Molise, some years ago we conducted an empirical study aimed at identifying energy-greedy API usage patterns in the Android API. We found very interesting results and insights. 

>Check the online appendix of the study to see real examples of energy greedy API usages: http://www.cs.wm.edu/semeru/data/MSR14-android-energy/#patterns.


For instance, the `findViewById` method used in Android apps for getting an object of a view (i.e., GUI component) defined in a layout file, was one of the most energy greedy APIs we found.  This has been already reported in Google groups and Q&A systems as StackOverflow, but from the point of view of computation cost, in the post entitled [Efficiency of findViewById](https://stackoverflow.com/questions/26037744/efficiency-of-findviewbyid). The main reason for the `findViewById` issue is that finding a view declaration in a layout file requires traversing the layout file, while looking for the component with the expected id. The [ViewHolder pattern](https://developer.android.com/training/improving-layouts/smooth-scrolling) and [data binding](https://medium.com/androiddevelopers/no-more-findviewbyid-457457644885) are ways to mitigate the impact of using 'findBiewById'. In iOS referencing a view from a ViewController is done via outlets (i.e., object references) that are declared explicitly in ViewControllers code.



> Check the StackOverflow post titled [Efficiency of findViewById](https://stackoverflow.com/questions/26037744/efficiency-of-findviewbyid). There is a cool discussion about the issues in the 'findViewById' method. 
  

<br>
<br>

 
[^1]: Mario Linares-Vásquez, Gabriele Bavota, Carlos Bernal-Cárdenas, Massimiliano Di Penta, Rocco Oliveto, and Denys Poshyvanyk. 2018. Multi-Objective Optimization of Energy Consumption of GUIs in Android Apps. ACM Trans. Softw. Eng. Methodol. 27, 3, Article 14 (September 2018), 47 pages. DOI: https://doi.org/10.1145/3241742

[^2]: Mario Linares-Vásquez, Gabriele Bavota, Carlos Bernal-Cárdenas, Rocco Oliveto, Massimiliano Di Penta, and Denys Poshyvanyk. 2014. Mining energy-greedy API usage patterns in Android apps: an empirical study. In Proceedings of the 11th Working Conference on Mining Software Repositories (MSR 2014). ACM, New York, NY, USA, 2-11. DOI: http://dx.doi.org/10.1145/2597073.2597085

[^3]: Abhinav Pathak, Y. Charlie Hu, and Ming Zhang. 2011. Bootstrapping energy debugging on smartphones: a first look at energy bugs in mobile devices. In Proceedings of the 10th ACM Workshop on Hot Topics in Networks (HotNets-X). ACM, New York, NY, USA, Article 5, 6 pages. DOI: https://doi.org/10.1145/2070562.2070567 
