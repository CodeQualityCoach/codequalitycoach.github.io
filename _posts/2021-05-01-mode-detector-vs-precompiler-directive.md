---
layout: post
title: ModeDetector vs. Precompiler Directives
categories: [EN, Testing, Snippet]
tags: [Precompiler Directive, Code, Testing]
---

> Disclaimer: This solution does not apply to multi-framework targeting.

## The problem

Regularly, I do a lot of refactoring, which means renaming classes and methods. Tools help a lot to rename dependencies and all dependent code. But sometimes, tools are not able to determine the correct refactoring for commented-out code. But why care about commented-out code? Because code, which has pre-compiler directives and is not included in the current configuration is "commented-out code" from a compiler perspective. The following snippet shows an example.

{% gist b8246fc93e0b747476f7b18ce303ae0f Modedetector_Problem.cs %}

My prefered solution is a class that encapsulates the code with the pre-compiler directive. The code is as simple and compiler-safe as possible and works for all configurations. This is a code, which returns the pre-compiler settings in a compiler-safe way. 

{% gist b8246fc93e0b747476f7b18ce303ae0f Modedetector_Simple.cs %}

Now, the directive can be used in a refactoring-safe way.

{% gist b8246fc93e0b747476f7b18ce303ae0f Modedetector_SimpleUsage.cs %}

