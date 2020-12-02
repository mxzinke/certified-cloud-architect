# Model Driven Architecture (MDA)

Ist das Modellieren einer Spezifikationen, welche völlig Plattform unabhängig ist und in sich strikt Business- und Applikationslogik trennt. Die plattformunabhängigen Modelle widerspiegeln Funktionalitäten und Verhalten ab.  Diese Architektur legt dabei großen Wert auf die Unabhängigkeit zwischen Business und Technologie, um damit die Grenzen in der Entwicklung zu brechen, Neuentwicklungen voranzutreiben und die Wiederverwendbarkeit zu erhöhen.

Nach meinem Verständnis wird die Code-Ebene nach oben, auf die Modellebene, gehoben. Man baut sich also kleinere Bausteine, die man zusammenstecken kann um wiederrum ein Gesamtbild zu schaffen. Man entwickelt somit nicht mehr mit Code, sondern nur noch mit fertigen Modellen die jeweils auf beliebiger Plattform umgesetzt werden können und miteinander Kommunizieren können.
Einziges Problem was zu meistern ist, ist dass man die Kommunikation vereinheitlichen und klare Schnittstellen definieren muss.

Für eine Umsetzung dieser Art verwendet man Generatoren, die Source-Code produzieren. In diesem sind nur noch die Anpassungen für die eigentliche Implementierung nötig.
Die Architektur hat drei Hauptmodelle als Leitfaden, folgend erklärt.

## CIM - Computation Independent Model
In der MDA gibt es ein Model, welches vollständig losgelöst ist, von der Applikationslogik und soll nur die Business Logik widerspiegeln. Dieses erlangt man in anderen Herangehensweisen bisher nur durch die Use-Case suche über die System Requirements. Sie wird für die umgangssprachliche Handhabung genutzt.

## PIM - Plattform Independent Model
Modellierung auf einer Ebene die noch nicht Plattform gebunden ist. Die Use-Cases werden miteinander verknüpft und geben ein Gesamtbild. Funktionalitäten spielen eine Rolle. Sie wird für die Modellierung von Geschäftsprozessen genutzt.

## PSM - Plattform Specific Model
Ist ein Plattformabhängige Definition der Architektur in Form von Services. Sie reicht jedoch nicht auf die Code-Ebene, also die eigentliche Implementation auf der Zielplattform.

## Abstrakte Beispiele
So kann man ein System mit mehreren Machine Learning Models bauen, welche alle die gleichen oder ähnliche Daten bekommen und ähnliche Daten als Ausgabe haben. Lässt man diese Modelle dann in der einer bestimmten Abfolge laufen oder macht es möglich die Models auszutauschen.

### Quellen:
- [Object Management Group - MDA](https://www.omg.org/mda/)
- [Gellschaft für Informatik eV](https://gi.de/informatiklexikon/model-driven-architecture)
- [RWTH Aachen - CIM](http://ftp.informatik.rwth-aachen.de/Publications/CEUR-WS/Vol-252/paper06.pdf)