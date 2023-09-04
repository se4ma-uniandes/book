# 12.2 Micro-optimizations again
\(By Mario Linares-Vásquez\)
___

We already talked briefly about micro-optimizations in Chapter 8. Let´s see another set of micro-optimizations you should care about when programming your mobile app.

**Use memory efficient collections if possible (Android)** 
Android has a wide set of collections that can be used within your app. If your structures are linear and the idea is to store basic types, always prefer arrays of primitive types instead of wrappers to reduce memory footprint. For instance, while an int type requires 4 bytes, an Integer wrapper requires 16 bytes. 

When using Lists, understand the differences between `Vector` and `ArrayList`. For instance, `Vector` is synchronized (`ArrayList` no) which adds overhead when compared to `ArrayList`. `Vector` and `ArrayList` in Java are dynamic collections that grow or shrink as needed. However, the space re-allocation in `Vector` wastes more memory because the slots increase based on the `capacityIncrement` attribute; if it is not set by the user, the `Vector` size will be doubled if an increase is needed, while in the case of `ArrayList`, the size is increased by adding 12 positions (in the worst case).

> Look for the source code of `Vector` and `ArrayList` and check the implementation of the `add` method in both collections.

When implementing dictionaries using `HashMap` check whether [`ArrayMap`](https://developer.android.com/reference/android/util/ArrayMap)  or any collection from the [`SparseArray`](https://developer.android.com/reference/android/util/SparseArray) family fits your needs. Both are dictionary implementations in the Android API aimed at being more memory efficient than `HashMap`. `ArrayMap` is a generic dictionary that requires less objects than `HashMap` internals and have a more aggressive control on how the internal array grows; there is no need to rebuild the internal array in `ArrayMap`, conversely to the index and buckets rehashing in  `HashMap`, because `ArrayMap` uses a separate chaining implementation with growing buckets and a load factor. However, insertions and deletions cost a bit more in an `ArrayMap` than in a `HashMap`. So, if the number of elements is less than 1K and there are a lot of accesses, deletions, and insertions, then it is a good idea to use `ArrayMap`.

There is another issue with generic HashMaps in Java. Keys and values in a HashMap can only be Objects, therefore, if the keys/values are primitive types you have to use the wrapper versions of the types (e.g., Integer, Float, etc). As we mentioned before, the wrappers require more memory than the primitive types, and there is an overhead because of the boxing/unboxing operations. To deal with this, the Android API has the `SparseArray` family, which allows developers to create dictionaries with primitive types as keys and values. An SparseArray is an ArrayMap, and the same use cases of ArrayMap apply to SparseArrays. 

The SparseArray family in Android contains the following implementations:

 |Class| Key |Value|
 | --- | --- | --- |
 |[SparseArray](https://developer.android.com/reference/android/util/SparseArray)|int|Object| 
 |[SparseBooleanArray](https://developer.android.com/reference/android/util/SparseBooleanArray)|int|boolean|
 |[SparseLongArray](https://developer.android.com/reference/android/util/SparseLongArray)|int|long|
 |[LongSparseArray](https://developer.android.com/reference/android/util/LongSparseArray)|long|Object|
 |[SparseIntArray](https://developer.android.com/reference/android/util/SparseIntArray)|int|int|
 



>For more details about `ArrayMap` and `SparseArray`, watch the [Fun with ArrayMaps](https://www.youtube.com/watch?v=ORgucLTtTDI) and [SparseArray Family Ties](https://www.youtube.com/watch?v=I16lz26WyzQ) videos. 

**Baseline alignment in LinearLayout (Android)** 
The `android:baselineAligned` attribute is used to align texts to the same invisible line in which the text sits on. When this attribute is true in linear layouts, it forces the texts to align themselvers with each other, therefore, there is extra work required to align the texts. This micro-optimization is suggested by the Android linter, therefore, try to use android:baselineAligned="false" in LinearLayouts.


**Use "reuse" identifiers (iOS)**
In Table views, when a new cell scrolls in the viewable area of the screen, a new object is created for each row. If you do not properly implement TableView in iOS, then, you can consume a lot of memory and introduce GUI lagging when a new row shows up after scrolling. There is a simple solution: to reuse cells by setting the ['cellReuseIdentifier'](https://developer.apple.com/documentation/uikit/uitableviewcell/1623246-reuseidentifier), by using the table view cell editor in XCode or programatically in the controller code. When the cellReuseIdentifier is not set, then a new object is created for each row in the Table/Collection.  Read the [Why we use dequeueReusableCellWithIdentifier](https://medium.com/ios-seminar/why-we-use-dequeuereusablecellwithidentifier-ce7fd97cde8e) article to understand how to use it in TableViews.

**Avoid Overdrawing (Android and iOS)**
Overdrawing is one of the sources of GUI lagging in mobile apps. Overdrawing means that the same pixel is painted/drawn several times, which makes no sense because the user only see the latest color painted in the pixel.  Overdrawing happens because the views are painted/drawn from back to forth according to the layout hierarchy, following a priority fill heuristic (a.k.a., [the painter´s algorithm](https://developer.android.com/topic/performance/rendering/overdraw)). For example, it is common for painters to paint first the most distant part from the viewer eyes, and so on until painting the closest one:



<p align="center">
<img width="100%" src="../assets/1000px-Painter's_algorithm.svg.png"/>
</p>
_(Image from [wikipedia](https://en.wikipedia.org/wiki/Painter%27s_algorithm) - CC BY-SA 3.0)_

So, the more layers are needed to paint in an app, the more overdraw it will have. The general fix here is to simplify view hierarchies by avoiding nested layouts. But there is a simple micro-optimization, which consists on removing unneeded backgrounds in GUI components and reducing transparencies. In Android, backgrounds are set to null in layout files by adding the `android:background="@null"` expression. In iOS, having opaque views optimizes the drawing operations; this attribute can be set to views programmatically or via the Attributes Inspector in Interface Builder Editor.

>Note that micro-optimizations are considered by some practitioners as premature optimization, and they recommend not to use it. We disagree with them, and encourage you to micro-optimize. Every minimum effort or saving, in a constrained and wild enviroment as the one where your apps run, counts and matters. Keep calm and micro-optimize your code !!