# Chapter 10: Error Retrieving
\(By Camilo Escobar-Velásquez\)

<p align="center">
<img width="100%" src="assets/fancycrave-228336-unsplash.jpg"/>
</p>
_(Free image by Fancycrave on [Unsplash](https://unsplash.com/photos/mIPu1hzjkZQ))_

---

Have you ever found yourself fighting with a mobile app because it is not able to publish your last status or picture? or maybe you are not able to send that waited message to your crush? Have you ever found out that some important work you have done was lost due to a connection error? I think we have all found errors like "An error ocurred:java.net.UnknownHostException ..." while using our cellphones. Or maybe, one of your parents has called you because "that thing doesn't work" referring to a mobile app they are trying to use. Well, let me tell you about connectivity errors on mobile apps.

Since smartphones are having a fundamental role in common life, we are relying on these devices (truly on mobile apps) to ease our daily tasks. However, these mobile devices are not always connected to the internet, and that is why you, as a developer, need to solve all the problems that might occur due to a lack of connectivity.

Let just imagine the next case. You work as a technician for an air conditioning company. Your boss has told you that the air conditioner on professor Mario Linares-Vásquez's office is not working, and you need to go to the Mario Laserna building's basement to check the pipelines that supply the cold air to the professor's office. When you arrive at the basement you realize that there are several broken tubes and decide to redact an email on your tablet to start a service order. You add a lot of pictures to the email and add a detailed description of the type of tubes and the correct procedure the next technician must follow to solve the problem. After 3 hours of work, you send the report via email to your boss, but when the app tries to send the email it shows a message that says: "There is an error sending the email" and then it closes. You try to open the app again and it starts showing a message that says: "Download process failed. This app will close". After the 20th try, the app opens but there isn't any saved draft of your email or the pictures you took. You run to your boss's office to tell him what happened and try to send an email in his office to show him that it was a problem from the email app. Unfortunately, when you send the email from your boss's office it all works fine. Overwhelmed by this behavior, you realize that the source of the problem is that there wasn't an active internet connection in the basement while there was one in your boss's office.

I don't know about you, but I would definitely uninstall that email app and start using another as soon as possible. But there is one main question that is important for you to get from this example ...

> How can I avoid providing this awful experience to my users ?


