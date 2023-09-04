# Chapter 12: Become a performance bug exterminator
\(By Mario Linares-Vásquez\)

<p align="center">
<img width="100%" src="assets/nowshad-arefin-484188-unsplash.jpg"/>
</p>


_(Free photo by Nowshad Arefin on [Unsplash](https://unsplash.com/photos/tTHUqB0FNWA))_
___

All right... All right... Get ready, because in this chapter you will read about different techniques to avoid, reduce, and get rid of those annoying performance bugs in your mobile apps. Starting from the basics, micro-optimizations (a.k.a., premature optimizations) are prevention-oriented techniques that at runtime could help your app to have better performance (depending on the work-load). Therefore, micro-optimize your app as much as you can. Also, be careful about GUI lags and ANRs, and take advantage of multi-threading; in this chapter we will tell you about the different API classes available for multi-threading. Also, to reduce processing times due to data retrieval you could use caching; thus, in this section we will present you the mechanisms available in both mobile platforms to enable caching. Finally, we will talk about some techniques for reducing the probability of having memory bloats, such as image recycling and using memory efficient structures. Putting all together, you can start your career as a performance bug exterminator.

But before starting, let´s take a quick look to some basic concepts of memory management in both platforms.



