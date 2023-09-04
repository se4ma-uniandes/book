# Chapter 9: Data pipelines

At this moment of the course, we have some analytical questions; but how are we going to answer them?. In this chapter, we are going to give you some clues and tools to make this possible. For now, let’s start with an analogy.


---

Imagine that you are in a candy factory, you receive many raw products such as: corn sugar, condensed-milk, maple sugar, colorants, dehydrated fruits, nuts and flavorings. For making candies and sell them or just eat them, we need first to make them!. We have to go through our production line:

- **Our first step** is to filter and audit the quality of or different components. For example, we can find some nuts that do not meet the quality needed, so we have to take them out.

- **Second step:** now we have our ingredients ready, so it is time to mix them up, for example we can mix liquid ingredients like water with sugar to make syrup.

- **Third step:** if we need some cooking and baking then we have to do it.

- **Fourth step:** since the candy factory cannot sell all the candies immediately, it has to store it in some special storage for finished candies.

As you can see, we need to take some raw products and go through some process to have the goal (candies). The same happens with data. We can have one or multiple data sources (raw data), which we wrangle, process, and transport to another data storage to final analyze it and answer our business questions. Those steps and different components that interact form a data pipeline. A data pipeline is a set of actions/components that ingest raw data from one or multiple sources and may transform and move to another system, in our case, for analysis and gather insights. In this set of actions, many components are involved.