# 3.3 Please help me to model the context
___


You might be familiar with the system context diagram, which is used to define/understand the boundaries between a system under design/analysis and its environment.

<p align="center">
<img width="500" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/NDE_Context_Diagram_%28vector%29.svg/620px-NDE_Context_Diagram_%28vector%29.svg.png"/>
</p>


_(Example of a system context diagram from Wikipedia)_

As you see in the figure, the circle in the middle is the system under analysis (SUA) and the boxes are the the entities or external systems that interact with the SUA. The connectors between all the components show the data/information flow.  

>If you are not knowledgeable of the context diagram, quickly read the wikipedia entry about [system context diagram](https://en.wikipedia.org/wiki/System_context_diagram).

Think about the potential usage of the context diagram in design thinking and in mobile app development. Write your thoughts in a piece of paper and discuss during 5 minutes with yourself (yes, like in a monologue) about the usefulness of the context diagram.

The context diagram is a useful tool for identifying interactions between components in a system, including external third-parties. However, this is just a part of the context, and in this course, we really care about the context because it has powerful insights about the problem we are analyzing. Thus, the system context diagram is limited for our needs.

_What are the main components in the context of a mobile app?_ You need a device, an app (obviously), personas, and backend services. _Anything else?_ Yes, a mobile app can interact with other apps installed in your device (e.g., contacts, messaging, browser, etc.) and interacts with the environment via sensors and data collection components. _Anything else important in the context?_ Of course, a persona uses an app under specific conditions/situations (e.g., in an elevator or in a place with bad network signal), thus, those conditions are part of the context.

We have designed a specific context diagram, which is tailored for mobile app development. We called it the **"context canvas"*. The context canvas is a graphic template that will help you to identify your app context, in particular, the information needs, information flows, constraints, and actors that interact with the app. Go to the next section and learn more about it.
