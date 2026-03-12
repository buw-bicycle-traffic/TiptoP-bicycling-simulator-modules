---
tags:
  - OpenBikeSim
  - CARLA
  - person/Gabriel_Kostka
  - person/Aboozar_Roosta
  - GitHub
date created: 2026-03-04
---

# Hintergrund

Für das Erstellen von virtuellen Umgebungen für den BT Radfahrsimulator in [CARLA](https://carla.org/) haben unsere früheren Kollegen Jack Stockman und Nando Redicker eine Anleitung erstellt und über [Docusaurus](https://docusaurus.io/) veröffentlicht. Die Sammlung der Infos ist gut und hilfreich, um zu lernen wie man Umgebungen in CARLA erstellt. Das Problem ist jedoch, dass die Anleitung bisher nicht fertig gestellt wurde und die Texte noch nicht überprüft wurden.
Die Texte zur Anleitung liegen auf [GitHub](https://github.com/buw-bicycle-traffic/BicycleSimulator) und sind über eine [Docusaurus Seite](https://bicyclesimulator.onrender.com/) lesbar. Um die Texte zu bearbeiten kann man in Docusaurus auf "Edit this page" am unteren Ende der Seite klicken und wird direkt zum jeweiligen Dokument in GitHub weitergeleitet. Hinweise zur Anleitung gibt es auch auf Basecamp im Projekt "[Bicycle Simulator](https://3.basecamp.com/5232459/projects/35892720)" unter "[Docs & Files / Open Source Guide for Bicycle Simulator Draft](https://3.basecamp.com/5232459/buckets/35892720/cloud_files/7001631352)"

Diese Anleitung kann eine große Hilfe für Menschen sein, die neu anfangen in CARLA zu arbeiten. CARLA hat jedoch seine Probleme und ist in der Human-in-the-Loop Simulator Szene kaum verbreitet. Daher ist der potentielle Nutzen dieser Anleitung zwar groß, die Zielgruppe jedoch sehr klein.
Der **Fokus** liegt daher darauf die Anleitung mit geringstem Aufwand zu verbessern und für die Veröffentlichung auf OpenBikeSim vorzubereiten.

## Ziel

- Die bestehende Anleitung zum Erstellen von virtuellen Umgebungen in CARLA in eine klare strukturierte Form mit präziser Wortwahl umwandeln und für die Publikation über OpenBikeSim vorbereiten.

## Arbeitshypothesen

Meine (Mathis) Hypothesen die es zu überprüfen gilt:

- Der grundsätzliche Inhalt zum Erstellen von virtuellen Umgebungen ist gut und hilfreich für Menschen mit wenig Vorwissen.
- Es gibt viele Texte "drum herum", die potentiell ablenken und gekürzt werden könnten.
- Das Verständnis der Anleitung kann durch eine klare Struktur und genaue Wortwahl verbessert werden.
- Viele Abschnitte der gesamten Dokumentation sind nicht relevant, nur manche: 
  - [Open Bicycle Simulator Introduction](https://bicyclesimulator.onrender.com/docs/IntroductionBISIM) --> not relevant
  - [Open Bicycle Simulator Overview](https://bicyclesimulator.onrender.com/docs/category/open-bicycle-simulator-overview) --> not relevant 
    - [Introduction](https://bicyclesimulator.onrender.com/docs/BISIM%20Overview/introduction) --> not relevant
    - [Equipment Requirements](https://bicyclesimulator.onrender.com/docs/BISIM%20Overview/Equipment-requirements) --> not relevant
    - [Small Electronics](https://bicyclesimulator.onrender.com/docs/BISIM%20Overview/small_electronics) --> not relevant
    - [**Software**](https://bicyclesimulator.onrender.com/docs/BISIM%20Overview/Software)\*\* --> relevant\*\*
  - [Setup and Building of Simulator](https://bicyclesimulator.onrender.com/docs/category/setup-and-building-of-simulator) --> not relevant 
    - [**Computer Setup**](https://bicyclesimulator.onrender.com/docs/Setup_and_Building_of_Simulator/Computer_Setup)\*\* --> relevant\*\*
    - [Simulator Setup](https://bicyclesimulator.onrender.com/docs/Setup_and_Building_of_Simulator/Simulator_Setup) --> not relevant
    - [**Setup of Scenarios**](https://bicyclesimulator.onrender.com/docs/Setup_and_Building_of_Simulator/Setup_of_Scenarios) \*\* --> relevant\*\*
  - [Calibration and Validation](https://bicyclesimulator.onrender.com/docs/category/calibration-and-validation) --> not relevant 
    - [Calibration](https://bicyclesimulator.onrender.com/docs/Calabration_and_Validation/Calibration) --> not relevant
    - [Validation of Bicycle Simulator](https://bicyclesimulator.onrender.com/docs/Calabration_and_Validation/Validation) --> not relevant
  - [Research Methodology](https://bicyclesimulator.onrender.com/docs/category/research-methodology) --> not relevant 
    - [Ethics](https://bicyclesimulator.onrender.com/docs/Reseach_Methodology/ethics)--> not relevant
    - [Measured Inputs](https://bicyclesimulator.onrender.com/docs/Reseach_Methodology/measured_inputs)--> not relevant
    - [Simulator Training](https://bicyclesimulator.onrender.com/docs/Reseach_Methodology/Simulator_Training)--> not relevant
    - [Questionnaires](https://bicyclesimulator.onrender.com/docs/Reseach_Methodology/Questionnaires)--> not relevant
  - [References](https://bicyclesimulator.onrender.com/docs/references)--> not relevant

> [!tip] Tip: Zusammenfassung per KI
> In Firefox kann man im Side Menu ein KI Tool hinzufügen. Z.B. mit Mistral kann man sich die Seite dann einfach zusammenfassen lassen. Das spart vielleicht etwas Lesearbeit.

# Aufgaben

- Die bestehende Anleitung lesen und kommentieren
- Eine Übersicht zu den vorhandenen Texten erstellen: 
  - Welche Inhalte sind wirklich wichtig für das erstellen von virtuellen Umgebungen in CARLA?
  - Welche Inhalte sind noch sehr grob und im Status einer Skizze?
  - Welche Schlüsselbegriffe gibt es, die in einem Glossar aufgefasst werden sollten?
  - Ist aus den bisherigen Dokumenten ein Workflow erkennbar?
  - Was kann weg und was sollte verbessert werden?
- Die vorhandene Anleitung überarbeiten 
  - Eine Struktur für die Anleitung erstellen und die vorhandenen Texte zuordnen und überarbeiten. 
    - Welche Lücken gibt es in den Texten?
    - Wo sollten ggf. noch Beschreibungen ergänzt werden?
    - Wo sollten ggf. noch Bilder, Skizzen Code Snipits o.ä. ergänzt werden?
  - Die überarbeitete Anleitung für die Publikation vorbereiten 
    - Alle Texte als Markdown und alle Bilder in einer Orderstruktur ablegen, welche die Struktur der Anleitung widerspiegelt.
    - Gemeinsam entscheiden, ob wir bei Docusaurus bleiben oder die Anleitung über OpenBikeSim veröffentlichen

# Anforderungen / Vorgaben

- Alle Textdokumente sollten im Markdown Format sein. 
  - Die Formatierung muss der [GitHub Formatierungsrichtlinie](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) entsprechen
- Alle Dateien müssen eindeutige klare Bezeichnungen haben
- Alle Bilder, etc. müssen in den Ordern der zugehörigen Texte abgelegt sein
- Für alle Bilder und externe Dokumente müssen Quellen angegeben werden.
- Für die Verwaltung von Quellen muss [Zotero](https://www.zotero.org/) verwendet werden
- Schlüsselbegriffe sollten einheitlich verwendet werden und da wo sinnvoll auch einmal definiert werden
- Begriffe sollten immer ausgeschrieben werden, Abkürzungen im besten Fall vermeiden. 
  - Ausnahme: Wenn lange, sich oft wiederholende Begriffe vorkommen und eine Abkürzung sinnvoll machen sollten die Abkürzung bei der ersten Nennung eingeführt und dann konsequent verwendet werden.
- Es sollte ein Glossar für Schlüsselbegriffe erstellt werden, der pro Begriff eine Definition, Synonyme, ggf. die Abkürzung und ggf. einen Quellenverweis enthält.
- Alle Dokumente müssen auf Englisch veröffentlicht werden. (Auf Deutsch schreiben und später übersetzen ist ok.)
- KI-Tools sollten für die Arbeit genutzt werden wo immer sinnvoll.
- Wenn KI-Tools genutzt werden muss das kurz dokumentiert werden in folgender Form: 
  - Welches Tool, wofür genutzt, in welchem Zeitraum
  - Beispiel: DeepL (kostenlose Version), Übersetzen von Textabschnitten, 01. - 05.03.2026