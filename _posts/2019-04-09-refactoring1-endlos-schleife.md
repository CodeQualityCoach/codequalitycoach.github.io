---
layout: post
title: Refactoring (I) Die Endlosschleife
categories: [DE, Architecture]
tags: [Refactoring]
---


Das Refactoring von Code ist laut Wikipedia eine Umstrukturierung von Codes ohne eine funktionale Veränderungen der Software aus Anwendersicht. Es werden nicht-funktionale Anforderungen wie Wartbarkeit, Lesbarkeit, Erweiterbarkeit und weitere *-keiten verbessert.

Refactoring kann beispielsweise durch Implementierung eines Plugin Mechanismus stattfinden. Das System wird aber im Rahmen des Refactorings nicht erweitert, sondern allenfalls bestehende Komponenten auf den neuen Pluginmechanismus umgestellt. In der Praxis wird es, zumindest wenn das Refactoring groß genug ist, mit der Umsetzung neue Features oder sichtbare Umstellungen in der Applikation geben. Aber der Großteil der Arbeit, der Kern des Refactorings, findet hinter den Kulissen statt.

#### "Manchmal muss man auch eine grüne Wiese umgraben, um neu anzufangen"

Das Refactoring von Software ist wie die Sanierung eines Hauses. Es folgt den gleichen Gesetzmäßigkeiten und es verlangt einem die gleichen Überlegungen ab, die man sich vor, während und nach den Umbaumaßnahmen machen muss. Und beim Hausbau kennt jeder den Spruch: "Mit einem Haus ist man nie fertig, es gibt immer etwas, das man reparieren muss.". Und ebenso ist das Refactoring eine "never ending story", eine Endlosschleife der Weiterentwicklung und Verbesserung.


Diese kleine Blogserie wird große und kleine Aspekte des Refactorings aufgreifen, aber eben auch die Analogie zur Haussanierung zeigen. Eine Sanierung, also ein Handwerk, ist oft greifbarer, als die Softwareentwicklung, weil ein Software Refactoring rein virtuell stattfindet. Aussagen wie "es funktioniert doch" oder "das geht schneller wenn man ... macht" bekommen plötzlich eine ganz andere Bedeutung, wenn man die Analogie des Hauses heranzieht.

Die Konsequenzen sind greifbarer und offensichtlicher. Eine Software gibt man in der Regel an einen oder mehrere Kunden ab, aber Häuser bewohnt man selber, und man muss mit den (Design-) Entscheidungen selber leben.

Es wird immer "Gründe" geben, warum die Analogien nicht passen. Manchmal zurecht, manchmal auch einfach nur, um die Augen vor dem Offensichtlichen zu verschließen. Man betrachtet die Probleme und Lösungen aus einer anderen Perspektive und kann sich mit neuen Argumenten einer besseren Lösung annähern.