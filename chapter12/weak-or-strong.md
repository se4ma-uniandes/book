# 12.1 Weak or strong?
\(By Mario Linares-Vásquez\)
___

The mobile development languages (i.e., Java, Kotlin, Swift) are high-level languages in which memory management has not to be done by the developer, conversely to other languages like C in which memory has to be allocated and released by the developer. Java, Kotlin, and Swift have mechanisms for automatically reclaiming unused memory. In the case of the Android languages, there is the [Garbage Collector (GC)](https://developer.android.com/topic/performance/memory-overview#gc) of the virtual machine (ART/DVM), and in Swift there is the [Automatic Reference Counting (ARC)](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html) mechanism. In both cases, GC and ARC, the memory claiming events are not controlled by the developer; each OS/environment has its own rules for deciding when to execute memory claiming events. However, there is a common rule for deciding what to claim: _free up memory of objects no longer needed in the program_. Note that the memory claiming events apply only to instances of classes (i.e., reference types), it does not apply to value types (e.g., structures and enumerations in Swift).

> Check the [Automatic Referencing Counting](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html) article from the swift book to understand how ARC works.

How is an object/reference understood by GC or ARC as no longer needed? An object is no longer needed when there is no active reference pointing to that object, there is no further usage of the object in the code, or it is an unreachable object, i.e., the object is not used anymore as an argument of a function, in a control structure, or by other value/reference type. For instance, if inside a loop you declare an object, once the iteration execution ends, the object is no longer needed because its scope is only the loop-iteration block.

> In the object declaration inside a loop example, each time the object is created, a new reference is created, so, the objects created in previous iterations are unreachable, which means that the objects are no longer needed... which means potential invocations of memory claiming events. So, if the loop has many iterations.... does it mean there would be several memory claiming events? Potentially, and the events could take more time depending on the objects structure and size in memory.

Freeing up memory also depends on whether the references are strong or weak, and whether there are strong reference cycles. Memory is re-claimed when there are zero strong references to an object. But, **what is a strong reference?** A strong reference is the by-default created reference  when you instantiate an object. Let's say we have a car object declaration; in swift `let car = Car()`, in Java `Car car = new Car()`, and in kotlin `val car: Car`. If there is a method or class having any of those statements, therefore, there is a strong reference to the car object because the car object is reachable from the scope that covers the object instantiation; as soon as the program flow leaves the scope, then, the references are not strong anymore.

OK, so, **what is a weak reference?** It is a reference that points to an object that is not protected from being deallocated. Because references are by default strong, therefore, a weak reference should be programmatically unprotected by developers. It means, a developer is the one who has to decide which references are weak on her code. A weak reference for a type `T` is declared as follows 

- Java: `WeakRefence<T> reference = new WeakReference<>(theReference)`
- Swift: `weak var reference: T?`
- Kotlin: `var reference: WeakReference<T>?`

In Kotlin and Swift, weak references are set to null/nil when deallocated, therefore, weak references should be optional variables. Extra logic should be added, in particular in Java, to avoid null pointer exceptions.

But **what are weak references useful for?** They are useful for avoiding memory leaks, view leaks, and activity leaks when there are strong reference cycles. Supose that you have two classes: `Professor` and `Department`; `Professor` has a department attribute, and the department has a reference back to the professor. It is a pretty common scenario in which there are strong references that create a strong reference cycle `Professor` -> `Department` -> `Professor`. So, the reference cycle keeps the references reachable, which means that memory claiming events can not free up memory. This is a very common memory leak.  The leak is avoided when at some point one of the references is set to null/nil. So, how can we fix it in a more decent way? By using a weak reference in one of the classes. For example, changing the classes so that `Professor` has a strong reference to `Deparment` and `Department` has a weak reference to `Professor`.

In the case of Android, in addition to the by-default strong references, there are [phantom](https://developer.android.com/reference/java/lang/ref/PhantomReference), [soft](https://developer.android.com/reference/java/lang/ref/SoftReference), and [weak](https://developer.android.com/reference/java/lang/ref/WeakReference) references. In swift, there are [weak and unowned](https://medium.com/@chris_dus/strong-weak-unowned-reference-counting-in-swift-5813fa454f30) references.

**Further reading.** If you are interested on more readings about references in mobile apps, take a look to the following links:


- [WEAK, STRONG, UNOWNED, OH MY!" - A GUIDE TO REFERENCES IN SWIFT](https://krakendev.io/blog/weak-and-unowned-references-in-swift)

- [Finally understanding how references work in Android and Java](https://medium.com/google-developer-experts/finally-understanding-how-references-work-in-android-and-java-26a0d9c92f83)
