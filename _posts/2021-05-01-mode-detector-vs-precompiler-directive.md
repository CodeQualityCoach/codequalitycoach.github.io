---
layout: post
title: ModeDetector vs. Precompiler Directives
categories: [EN, Testing, Snippet]
tags: [Precompiler Directive, Code, Testing]
---

## The problem

Sometimes the build server runs into a very common problem, the **"It runs on my machine"** problem. This can be caused by a compiler error, which dit not occur on a developers machine. This can be caused by precompiler directives which changes the code before the compiler tries to compile it, especially if the code should behave differently in `debug` than in `release`. The following code illustrates a typical example.

AWESOME CODE WITH #DEBUG


