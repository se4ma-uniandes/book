# 12.4 Using multi-threading like a boss !!
\(By Mario Linares-Vásquez\)
<p align="center">
<img width="100%" src="/assets/martin-sanchez-513155-unsplash.jpg"/>
</p>


_(Free photo by  Martin Sanchez on [Unsplash](https://unsplash.com/photos/NfLZeAN7I6s))_
___

Multi-treading is a way of distributing work in batches, by assigning batches to different threads that can be executed on a set of processors.  But how con this be used to avoid losing my friend in the single-thread game? Well, use multi-threading with different workers (i.e., background threads)  to off-load long running tasks from the main-thread, with the purpose of giving the main thread the chance to continue interacting with the user nicely..... smoothly (i.e., without any lag, glitch, or ANR).

A worker is a thread that runsin background with the purpose of executing long tasks. Using the single-thread game as an example, you could hire minions that are in charge of executing the tasks (for you) while you continue giving your user a nice experience without any lag or blocking. Those "minions" could inform you about the progress of the tasks, so you can tell the user "you task is in progress..", or inform you when the task is done. The same happens with a mobile apps, because mobile apps by default execute everything in the main thread, you can start worker threads for executing long lasting tasks (e.g., processing data retrieved from a REST API) out of the main thread. 

This sounds pretty easy to do, but there is a general restriction in both mobile platforms: GUI-related tasks (e.g., painting a view) can only be done on the main thread. So, your multi-threading strategy must consider that if your worker threads needs to paint something on the GUI, the execution flow needs to go back to the UI. To do this, you need to understand how multi-threading is done on each mobile platform. In the case of iOS it is straightforward by using the Grand Central Dispatch, however, in the case of Android you need to be careful because the API has more than one option for implementing working threads.

**Multi-threading in iOS.** The [Grand Central Dispatch](https://developer.apple.com/documentation/dispatch) (GCD) is a unique API for handling multi-threading in iOS apps, which encapsulates low level tasks in a high level and easy to use API.  GCD allows iOS developers to define synchronous and asynchronous execution of tasks on predefined queues that are executed (i) serially or concurrently (i.e., time sliced), and (ii) on or off the main thread. In addition to the pre-defined queues, a developer can also set their on queues.

There is a main queue for executing tasks serially on the main thread, and there are for global queues (high, default, low, background) for executing tasks (concurrently) with different priorities:

<p align="center">
<img width="70%" src="/assets/gcd-queues.png"/>
</p>

The `qos` argument is for defining the execution priority of the queues that do not execute the tasks serially:

- `userInteractive`: runs on the main thread; it is expected for small tasks that must finished immediately;

-  `userInitiated`: use it for work that is expected to runs on the high priority global queue and it is expected for async tasks from the UI;

- `utility`: it runs on the low priority global queue, and is expected for long running tasks with a visible feedback via progress indicators;
 
- `background`: this is the one for long lasting tasks that need to be executed in background

- `unspecified`: GCD assigns the job to the default global queue.

On-loading and off-loading to the main thread is simply achieved by encapsulating code statements inside the corresponding queue block. A queue block is defined by the corresponding queue objected followed by the `async` or `sync`keywords as illustrated above:

<p align="center">
<img width="70%" src="/assets/on-off-main-thread.png"/>
</p>


**Multi-threading in Android.** This is a completely different animal because there is no unique API in Android; even there are differences depending on the language (e.g., kotlin). However, the main idea is to pick the right class depending on the task. Some of the options you have are:

- [`AsyncTask`](https://developer.android.com/reference/android/os/AsyncTask): this provides the easiest way to do work in background and update the UI. The `AsyncTask` class executes code on the main thread via the methods `onPreExecute`, `onProgressUpdate`, and `onPostExecute`. The `doInBackground` is the one for executing the task in background. Note that all the AsyncTasks in an app run serially, so if you have an AsynTask that is long lasting, it could delay the execution of other AsyncTasks in your app

- `Service`  and [`IntentService`](https://developer.android.com/reference/android/app/IntentService): while a service runs on the main thread, and `IntentService` is used to offload work from the main thread. An `IntentService` handle asynchronous requests via intents with a work queue that serves the requests to the IntentService. Because there is only a work queue for each IntentSerice, therefore a long lasting execution may delay other intents waiting for being served in the queue. This class is intended for lon  Starting on API 26, IntentServices are subjects to [background execution limits](https://developer.android.com/about/versions/oreo/background). This type of worker is a good option for long running tasks that do not require updating the UI. If you need to update the UI you could use a Local Broadcast Receiver to inform the UI when it needs to be updated or by sending messages to a Handler created in the corresponding UI class.

- [`HandlerThread`](https://developer.android.com/reference/android/os/HandlerThread): this is also a good option for long tasks in background. Note that an IntentService has a HandlerThread, so the behavior is very similar. A `HandlerThread` also has a queue, and it is is a long living thread, because it has a Looper that keeps it alive. 
 
- `Thread`: this is the classic Java thread intended to run long tasks on the background. Use it as the last line of defense when the other options does not fit your needs. Remember that threads run on background.





