# Chapter 7: Yes, software architecture matters... a lot.

(By Mario Linares-Vásquez)
> **NOTE: In this chapter, I will use some online videos created by Prof. Alex Orso \(Georgia Tech\) as a reference.**

---
<p align="center">
  <img src="assets/pexels-photo-415574.jpeg">
</p>
_(Free photo from [https://www.pexels.com](https://www.pexels.com/photo/arch-architecture-art-building-415574/). Creative Commons Zero (CC0) license)._


At this point in your engineering (or computer science) program, you are very close to seeing the ''light at the end of the tunnel"[^1]. You are at your senior year and you have already passed \(or failed\) a large set of classes that have prepared you for this moment \(attending this awesome class\). Our "Mobile apps development" class is a software engineering-oriented one that focuses on the process of designing and building mobile apps based on a set of _**design constraints**_**. **In the case of mobile apps, we must give special attention to design constraints because mobile apps run on environments that have limited resources and are exposed to eventualities from this context \(e.g., the phone is running out of memory, or there is no good internet connection when using your favorite app\).  Therefore, _**design constraints**_ should be part of the development process, including the evolution and maintenance phases.

> Do you not remember what a design constraint is? Well, this is one of the foundations of the engineering disciplines, because we, as engineers, design and build awesome things that \(i\) provide solutions to problems experienced by people \(cool and challenging problems\), and \(ii\) improve the life quality of people in our society. But if you do not remember what a design constraint is, no worries!! In this chapter, we will recap \(briefly\) the most important concepts you need to know for our class.

Examples of design constraints are the _**quality attributes**_** **that software applications must support and deal with, such as eventual connectivity, performance, or accesibility. Design constraints can be achieved in software applications by implementing _**design decisions**_ that combine hardware, software, and humanware. The way how we ---engineers--- organize the design decisions is by means of an architecture. Design an architecture requires us (first) to follow well-proved _**architectural styles and patterns **_\(or to create new ones\), and then to implement _**tactics**_** **that will help us assure our app supports the design constraints.

> The term architecture makes reference to the design of the "structures" that compose a system and the rationale for that design.

Design constraints, architecture, quality attributes, non-functional requirements, architectural styles and patterns, tactics, etc., are concepts that you should know (if you already attended a software architecture class). Applying these concepts should be your _**mantra**_, since you are not only a programmer--you are an engineer and an architect. The lack of architectural design in mobile apps is one of the top reasons for having buggy apps that will be easily dropped/uninstalled by users. The mobile ecosystem has millions of apps that can be easily browsed by users that look for "replacement products" \(i.e., an app that does a better job than your app\). Thus, high quality is a mandatory feature for mobile apps.

In the following sections, you will find a brief description of those main concepts. This is not a "replacement" of your software architecture or software design classes. This is a complement, and we build "upon the shoulders of giants", i.e., you are supposed to be ready to design software applications \(like a boss!!\). We just want to make sure we are on the same page, and we talk the same language in the class. In the case you want to go deep into the concepts, we provide additional links and further readings.

Architecture is an amazing discipline that allows us to build great pieces of art like the one you saw in the photo at the beginning of this section. Software systems are also masterpieces composed of thousands, millions of components called code, libraries, resources, etc.


[^1]: I am assuming that you take the "Mobile Development" class at your senior year, as happens at Universidad de los Andes (Colombia).
