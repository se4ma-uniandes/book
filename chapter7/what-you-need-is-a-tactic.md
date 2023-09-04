# 7.4 What you need is a tactic  !!

---

<p align="center">
  <img src="../assets/luca-onniboni-bridge.jpg" >
</p>
_(Free photo by Luca Unniboni on [Unsplash](https://unsplash.com/photos/bUpwY7EdrlQ))._


One of the big challenges we have to face is the lack of *visibility* of software structures when compared to other *products* made by humans. Think of a building, a bridge, or a car.  Clearly, these structures are composed of other structures and elements, which are put together by using different gluing/connection mechanisms and a plethora of engineering methods. Are software systems structures composed of other structures and components that are put together by using engineering methods? Yes, they are. The big difference is that most of the structures and components in software systems are also software (:sweat_smile:), which means that they are not visible to the user because at the end, they are strings of zeros and ones running on a Zilicio-based world \(the chips in the computers\). Of course you can see the hardware, which is also part of the software system. However, the soul of a software system is not tangible at all. What the users can see is the UI and documents of the systems.

OK, OK, but how does this concept of *(in)visibility* fit in our book? Some of the engineering techniques we use are not as fancy as the math-based methods of other disciplines[^1], but we have several methods that belong to the book-of-knowledge that several guys have built since the last century \(circa 1950\). In addition to architectural styles and design patterns, there are specific "recipes" that have been designed, in particular, to deal with and achieve **quality attributes.** These recipes are known as **architectural tactics** \(or tactics\).

> Recap: A quality attribute \(aka quality properties\) is a stakeholder concern in the non-functional sense. This means that a quality attribute is a non-functional property that can impact the quality as perceived by the stakeholder. Examples of quality attributes are: security, scalability, performance, etc.

According to Nick Rozanski and Eoin Woods in his seminal book "Software Systems Architecture":

_"An architectural tactic is an established and proven approach you can use to help achieve a particular quality property \(e.g., defining different processing priorities for different parts of the system’s workload and managing this by using a priority-based process scheduler to achieve satisfactory overall system performance\)."_[^2]

Another definition of tactic from Len Bass et al. book is:

_"A tactic is a design decision that influences the control of a quality attribute response."_[^3]

In other words, a tactic is a recipe for achieving a quality attribute. Note that a *tactic* is different from a *design pattern* in that the pattern operates at the class level, while a tactic is a design decision that might involve hardware, architectural style, or execution of specific actions. An example of well-known tactics for achieving scalability are vertical and horizontal scalability---while the former establishes that increasing the resources in a machine \(it is like asking help to Captain America when you are in a fight\), the latter suggest to include more machines that distribute the computing tasks across the machines \(it is like asking help to a thousand minions when you are in a fight\). If you are interested in reading more about the architectural tactics, please check \(at your own pace\) the Rozanski's and Bass's books referenced in this section.


[^1]: Note that there are formal methods for developing software, but they are out of the scope of this book.

[^2]: Nick Rozanski, Eoin Woods. Software Systems Architecture, Addison Wesley, 2005.

[^3]: Len Bass, Paul Clements, Rick Kazman. Software Architecture in Practice, 3rd edition, Addison Wesley, 2012.
