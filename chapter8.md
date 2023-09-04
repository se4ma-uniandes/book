# Chapter 8: Finally... coding
\(By Mario Linares-Vásquez, Laura Bello-Jiménez, Santiago Cortés-Fernández, and Rogelio García\)



<p align="center">
<img width="100%" src="assets/caspar-rubin-669071-unsplash.jpg"/>
</p>

_(Free image by Caspar Rubin on [Unsplash](https://unsplash.com/photos/89xuP-XmyrA))_

---
All right!! It's time for getting your hands "dirty" and learning mode about coding practices in mobile development. Programming mobile apps is a very interesting (and complex) topic. It is not only about learning the languages' syntax and code; you need to follow the best practices and understand what you are doing because mobile devices and Operating Systems impose several constraints on your apps. Not following the design/coding practices is a clear recipe for failure.

In addition, you should understand that each mobile platform follows a different programming model and architectural patterns. For instance, while iOS follows strictly an MVC pattern, Android apps can be implemented using other patterns like MVVM and MVI.

> You can even create Android apps without following any patterns. During several years, Android developers worked like that. The good news is that Google has introduced the "[Android Architecture Components](https://developer.android.com/jetpack/arch/)", so, finally, Android developers have a guide to follow.

Independently of the platform, there are some basic rules you MUST follow before coding and designing your app:

- **Be concerned... about separating concerns in your app:** do not put all your code in the GUI related components. Get knowledgeable of the programming components and the purpose of each one. Follow the developer guides that explain you how and when each component should be used.

- **Single GUI-thread policy:** mobile apps run on a single thread by default. That "main" thread is on charge of painting the GUI, listening to events (GUI and system), and whatever other operation is codified. Therefore, do not miss multi-threading opportunities by using the right APIs, and let be conservative when assigning tasks to the main thread.

- **Simplicity:** keep your code as simple as possible and remove the code and resources you do not really need.

- **Know the platform:**  again, know the mobile development platform and follow de best practices and developer guides. Components and applications have life-cycle/callback methods designed for dealing with the events-based nature of mobile apps. Mobile platforms are change-prone [^1] (in particular Android), so, be up-to-date on the changes done for each new-release of the mobile APIs and OSs.

- **Performance matters:** be careful with your design decisions. Mobile devices have several constraints and there is trade-off between quality attributes (e.g., security impacts performance). Thus, think carefully about the rationale and implementation of your design decisions.

> You will learn more about performance practices in Chapter 9. Chapter 8 has a brief introduction to one technique for improving performance: micro-optimizations.

<br>
<br>
[^1] G. Bavota, M. Linares-Vásquez, C. E. Bernal-Cárdenas, M. D. Penta, R. Oliveto and D. Poshyvanyk, "The Impact of API Change- and Fault-Proneness on the User Ratings of Android Apps," in IEEE Transactions on Software Engineering, vol. 41, no. 4, pp. 384-407, 1 April 2015. doi: 10.1109/TSE.2014.2367027
