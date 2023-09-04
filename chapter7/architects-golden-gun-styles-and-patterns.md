# 7.3 Architects' mojo: styles and patterns

---
Think for a few seconds on the following question: _What architecture should I use? _

It depends on the type of application you are building and the design constraints you need to meet. The first step on selecting a suitable architecture is to understand how the system components should interact together and how the information flows across them. The good news is that there is a catalog of already defined and proved architectures styles and patterns. You might be familiar with the _Model-View-Controller pattern_ and the _REST architectural style_. But why is the former a pattern and the latter a style? Watch the following video by Prof. Alex Orso (Georgia Tech), which briefly explains what an architectural style is.

<iframe width="560" height="315" src="https://www.youtube.com/embed/jKPyb6GatJU?si=kbP4ZLeh-GJ8g4x7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

_(Video by Prof. Alex Orso from Georgia Tech available at [Youtube](https://www.youtube.com/watch?v=jKPyb6GatJU). The video is published under the Standard YouTube license )_

If you do not remember your software architecture course, you might be a bit confused. Style? Pattern? As described by Prof. Orso in his video, an architectural style is a specific way of combining components and connections, and a well-defined data flow/communication between the components.
> And what about the patterns? ..... No worries, we will talk about patterns later.

For instance, the micro-services and SOA buzzwords refer to two architectural styles that belong to a family called **call-return** style. In this family, a consumer component invokes functionality available in or offered by provider components. Check one more video by Prof. Alex Orso that presents six different architectural styles:


<iframe width="560" height="315" src="https://www.youtube.com/embed/JLbo9Lvvy5M?si=l2IbDt07xzfBCFtH" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

_(Video by Prof. Alex Orso from Georgia Tech available at [YouTube](https://www.youtube.com/watch?v=JLbo9Lvvy5M). The video is published under the Standard YouTube license )_

After watching Prof. Orso's video, let me clarify some concepts. In general, there are four (high-level) categories of architectural styles (a.k.a., families) that follow the components-and-connectors metaphor:

 1. **Data-flow styles:** The system is a combination of components that transform data in a consecutive way. If data/information is a stream, then each component in the system is like a pipe section in the whole pipeline that moves the "data stream". In a data-flow system, the output of a component is then the input for other components, and so on. The assumption is that each component is on charge of transforming its input. The pipes-and-filter style mentioned in Prof. Orso's video is one example of style in the **data-flow** family.
 > Are you familiar with the UNIX/Linux systems? If you enjoy typing commands on a UNIX/Linux console you will be surprised by the amazing results you can have by "piping" commands using the pipe "|" character. UNIX/Linux systems use the pipes-and-filter style.

 2. **Call-return styles:** As mentioned before, this family groups the styles in which a consumer invokes the functionality in a provider. Note that the invocation can be synchronous or asynchronous. Probably, you are thinking now on client-server, multi-tier, SOA, and REST. Yes, you are right!!! These are examples of **call-return** styles. What about the torrents and communication apps (e.g., Skype, WhatsApp) that share data with different nodes like in a point-to-point way? These apps follow the peer-to-peer style that also belongs to the **call-return** family.

 3. **Event-based styles:** Pretty clear right? This family groups the styles in which components interact by means of events, and the system operation is an emerging property of the events-based interaction of its components. Events can be signals, user inputs, sensor inputs, messages, callback methods, etc. Events act as functionality triggers or indicators of change in a part of the system. Thus, communication in **event-based** styles is **implicit**, which means that components do not directly call each other, because the communication is mediated by an **event bus**. In systems using the **event-based** style, the components communicate through asynchronous messages (that are handled by the bus) and the components are loosely coupled. One famous and widely used style from this family is the publish-subscribe style.
>Wait a second, this sounds also like SOA and REST!! You are right---SOA and REST combine both **call-return** and **event-based** styles.

 4. **Repository-based styles:** Representative examples in this family are the shared-data and blackboard styles. In **repository-based** systems there are central components that keep large collections of data (i.e., the repositories). Those components might be also in charge of notifying data-accessor components when the data has changed.
>This sounds like data-centric applications (aka applications with a database), right? In other words, this sounds like systems where there is a database-management system (SQL or NoSQL) that provides persistence capabilities.


All right, that is enough with architectural styles for today. We are still missing a highly relevant concept: patterns. In the case of software engineering, a **design pattern** is a *well-proved solution to a problem*. The solution is expressed in terms of classes and objects and how they should interact. This sounds pretty close to the definition of architectural style, if we consider classes and objects as components. However, one key difference is the scope: while architectural styles apply to components in general, the scope of design patterns is the internals of a software system. In other words, the scope of design patterns are code units such as packages, classes, or methods. Thus, a design pattern involves classes and objects, whereas an architectural style applies to systems, subsystems, or modules. Another key difference is that a design pattern has four essential elements that should be reported when describing it: the pattern name, the problem, the solution, and the consequences. Instead, architectural styles do not have definition templates.  

In the literature, you will find different catalogs of design patterns. The most famous one is the GoF (Gang-of-Four) catalog for object-oriented software proposed by Eric Gamma, Richard Helm, Ralph Johnson, and John Vlissides. You should be familiar with some of the design patterns in the GoF list, e.g., Factory, FactoryMethod, Strategy, Observer, Facade, Decorator, among others.

Another well-known catalog is the JEE catalog for enterprise applications, which describes patterns depending on the application tier in which they should be located. Common examples of the JEE catalog are Value Object (VO)/Data Transfer Object (DTO)/Transfer Object (TO), Business Delegate, Data Access Object (DAO), Service/Session Facade, Service, Service Broker, among other. Note that the J2EE patterns are not only for JEE applications; they are widely adopted in software systems (of any type).

> Check [this diagram](http://www.corej2eepatterns.com/images/CJP2Catalog.gif) that summarizes the JEE patterns and their relationships.

In summary, design patterns provide you with smart, effective and elegant strategies for organizing your classes and methods, by following object-oriented design principles and promoting quality attributes such as maintainability.

But, what about **architectural patterns**? They are also design patterns but with a broader scope. A way of defining an architectural pattern is as a specialization of an architectural style that solves a recurrent problem in software design but at the architectural level. Maybe you are familiar with some of them, but what you do not know is that they are patterns. MVC (Model-View-Controller), MVP (Model-View-Presenter), and MVW (Model-View-Whatever) are examples of architectural patterns that correspond to the multi-tier style.  

Lets close this section now. Remember, designing a software system requires you to combine architectural styles, architectural patterns, and design patterns.


>Now, browse internet and look for real examples of each one of the styles presented in Prof. Orso's video.  We might ask you later in the weekly quiz about the examples :\). The following videos, explain some examples of real systems and their underlying architectural style, but you should look for other examples: <br>
[Napster Example - Georgia Tech - Software Development Process](https://www.youtube.com/watch?v=odPVTQG7IaY)
_(Video by Prof. Alex Orso from Georgia Tech available at YouTube and  published under the Standard YouTube license )_ <br>
[Skype Example - Georgia Tech - Software Development Process](https://www.youtube.com/watch?v=tjgqOXbQBJo)
_(Video by Prof. Alex Orso from Georgia Tech available at YouTube and  published under the Standard YouTube license )_
