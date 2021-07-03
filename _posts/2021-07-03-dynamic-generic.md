---
layout: post
title: Dynamically create generic using reflection
categories: [EN, Testing, Snippet]
tags: [.NET, Code, Testing, Generics, Reflection]
---

A long time ago I created a class which helps creating a sut for unit testing. This class is generic and has the type of the sut as generic parameter. 
Details see [ContextFor<> zum Testen des SUT](/posts/ContextFor-for-testing/).

Now, I was trying to use the `ContextFor<T>` in a [data-driven test](/posts/lazy-load-of-assembly/) which passes the type as parameter. This is a little tricky,
because the generic class is not known during compile-time. The casting is limited due to covariance of the generic patameter `T`. Besides, the default
`Activator.CreateInstance` is not designed to dynamic generics.

The following snippet shows the creation of a generic with a dynamic generic parameter `T`. The `dynamic` can be replaced by `object` but obviously not 
to the data-driven parameter.

{% gist b8246fc93e0b747476f7b18ce303ae0f Activator_Generic.cs %}
