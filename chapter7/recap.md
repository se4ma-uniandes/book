# 7.2 About design and design constraints

Remember that one of the most important things in the engineering disciplines is _**design**_, and computer science, software engineering and systems/computing engineering are not the exception. Although we do not follow "heavy" a priori methods to design and test the design of software before the construction phase \(like other engineers do\), we have a plethora of methods, models, and tools in our toolbox that allow us to design software applications. For us, _**design**_ is highly important because we are engineers and architects, and as a consequence, \(i\) we build software systems that solve human kind issues/problems, and \(ii\) we must deal with a set of design constraints \(e.g., budget, a specific software stack, or a set of service level agreements\). In order to build software systems, we _must_ design (or define) an architecture. Please take a look to the following video of Prof. Alex Orso \(Georgia Tech\) that briefly explains two different definitions of *software architecture*:


{%youtube%}6bX2EPI-BqE{%endyoutube%}

_(Video by Prof. Alex Orso from Georgia Tech available at [YouTube](https://www.youtube.com/watch?v=6bX2EPI-BqE). The video is published under the Standard YouTube license )_

In the context of software development, architecture is the *design of the structures that compose a system*. One easy way to understand the architecture is by using a "metaphor" of components and connections. In this sense, a software system is a set of components that interact with each other. Thus, as Prof. Orso said in the video, a software architecture is a design of how the components interact in a software system and the rationale for that design.

>Note that an architecture also includes the hardware and human components of a system.

OK, but what is the meaning of _rationale_? It is the set of underlying reasons for your design decisions and your architecture, e.g.,  "we decided to follow a publish-suscribe style because we were interested on asynchronous notifications".

Remember that when designing a system there are three aspects that should be gathered/elicited to define _what is the system to implement_ and _how is the system going to be implemented_:

1. the features and services offered by the system to the users, i.e.,** the functional requirements**;
2. the quality attributes and service levels expected by the stakeholders, i.e., **the non-functional requirements**
3. **technology constraints** regarding the production/deployment environment (e.g., the system should be deployed on AWS but with Windows servers).

Both **non-functional requirements** and **technology constraints** are design constraints that drive systems' implementation. Design constraints are like "nature forces" that you must fight/deal with when designing a system. If there are design constraints, then your architecture must assure the constraints will be covered. But, How? Well, by using architectural styles, patterns, and tactics.
