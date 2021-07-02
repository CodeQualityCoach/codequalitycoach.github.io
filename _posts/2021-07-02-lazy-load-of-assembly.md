---
layout: post
title: Lazy load of assemblies can be tricky
categories: [EN, Testing, Snippet]
tags: [.NET, Code, Testing]
---

Recently I was doing some testing and trying to check if all classes have a corresponding test class. Therefore I used data-driven nunit tests, which uses 
a list of all classes in non-test assemblies.

{% gist b8246fc93e0b747476f7b18ce303ae0f datadrivenunittest.cs %}

I created another test to verify the list of the classes used as test data-source. The idea was making sure that the data source is returning all testable classes
and excludes classes which are not in the scope for "test class required" constraint.

{% gist b8246fc93e0b747476f7b18ce303ae0f datadrivenunittest_test.cs %}

The classes are added correctly to the data-driven data-source but the tests were not executed. The test-runner marked the test as "ignored" and "inconclusive". So I was
trying to figure out, why were the tests (for approx. 100 classes) not executed, although I validated, that the data-source is correct.

After using multiple test runners and searching the internet for bugs, the solution came to my mind. **The .NET framework only loads an assembly to the app domain if it is required.**
The data-source validation test was using at least one class from each related assembly. To the frameworks loads the assembly to the app domain before the test method was executed.

For the data-driven test it was different. Non of these classes were referenced, so the .NET framework does not load the assemblies into the app domain. The solutions is to
make the data-source reference the types from the related assemblies. After that, is was working fine and all classes were tested.

{% gist b8246fc93e0b747476f7b18ce303ae0f datadrivenunittest_working.cs %}
