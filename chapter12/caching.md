# 12.5 Caching
\(By Mario Linares-Vásquez\)
___
 All right.  Let´s talk again about the single-thread game from Section 11.3. Remember that in the game there was an action requesting for a math operation: *"Calculate
sqrt(35323554545345345345345345345)"*. If you are doing the operation manually and you get the request action, it would be cool if you have the result in a notebook or a post-it, so you do not have to expend again "computational power" recalculating the value. The notebook or the post-it is just a form of "cache", a very simple one.

Caching is a technique used in computing to store data in a temporal storage (i.e., cache) with the purpose of serving that data faster for incoming future requests (asking for the same data). Caching can be done directly by hardware components, or programmatically as part of the architecture of a software system. 
Among the benefits of using caching you can find improvements on  application performance in terms of latency, response time, and IOPS (input/output operations per second), reduction of energy consumption, and reduction of the load on the backend. The key of caching is on having temporary storage that is significantly faster than re-calculating the data. 

> Note that cache is not only for data generated with a computation, but also for resources that are accessed locally or via a backend request such as images, documents, or result sets.


This sounds like a pretty good strategy to be widely used in apps, right? Yes; however, caching can not be used with every piece of data you have in your app. Look, because temporary storage is faster than persistent storage (i.e., disk),  cache is more expensive and consequently smaller. Therefore, cache is often kept in RAM, which means,  you have a reduce set of memory slots for caching. So, how to decide what you keep in cache? 