---
layout: post
title: ContextFor<> zum Testen des SUT
categories: [DE, Testing, Snippet]
tags: [Testing Helper, Code]
---

In meinen Projekte der letzten Jahren ist mit der Zeit eine Hilfsklasse fürs Testen entstanden. Das Problem war das Erstellen des SUT mittels Konstruktor, welcher bei Dependency Injection entsprechend viele Paramter hat oder haben kann.  

Hier ein Beispiel mit "nur" 5 Konstruktor Parameter.

{% gist b8246fc93e0b747476f7b18ce303ae0f contextfor_problem.cs %}

Dadurch ist Builder entstanden, welcher für jeden Konstruktor Parameter des SUT ein Mock mittels NSubstitute erzeugt. Auf diese generierten Instanzen kann über die `For<>()`-Methode mit dem entsprechenden Typ zugegriffen werden. Mittels `Use<>()` kann die generierte Instanz ersetzt werden, beispielsweise durch einen komplexen Mock.

Im folgenden sind kleine Beispiele für die Verwendung. Mehr Beispiele finden sich auf der Projektseite von [NEdifis](https://github.com/awesome-inc/NEdifis), in dem diverse Hilfsklassen fürs Testen hinterlegt sind.

{% gist b8246fc93e0b747476f7b18ce303ae0f contextfor_usage.cs %}

Der Code für den Contest findet man hier, oder auch auf der Projektseite in der aktuellen Version. Benutzt werden in der Bibliothek NUnit, NSubstitute und FluentAssertions.

{% gist b8246fc93e0b747476f7b18ce303ae0f contextfor.cs %}

  