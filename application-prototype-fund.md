## 1. Allgemeines

### Projekttitel \*

Kollaborativer WYSIWYG-Editor für strukturierte Dokumente

### Name für den Account \*

–

### Vorname \*

–

### Name \*

–

### E-Mail-Adresse \*

–

### Hast du einen Account bei GitHub, BitBucket oder einer ähnlichen Plattform? Wenn ja, gib bitte den entsprechenden Link an.

https://github.com/kulla

## 2. Dein Projekt

### Beschreibe dein Projekt kurz. \*

(max. 100 Wörter)

Wir wollen ein Framework entwickeln, das es ermöglicht, strukturierte Dokumente
(z.B. Arbeitsblätter, Formulare, Konfigurationen, technische Dokumentationen) in
Echtzeit gemeinsam und mit einer WYSIWYG-User-Experience zu erstellen. Bisherige
Editor-Frameworks lösen bisher nur jeweils einen Teil der Herausforderung:
Während WYSIWYG-Editoren wie [Lexical](https://lexical.dev/) oder
[ProseMirror](https://prosemirror.net/) eine hervorragende Nutzererfahrung und
Kollaboration bieten, unterstützen sie keine strukturierten Inhalte.
Formbasierte Editoren wie [H5P](https://h5p.org/) ermöglichen strukturierte
Inhalte, bleiben aber in der Nutzererfahrung hinter heutigen Standards zurück
und unterstützen keine gleichzeitige Bearbeitung. Unser Framework kombiniert
beide Ansätze und erleichtert so die Erstellung strukturierter Dokumente, was
wir im Bildungsbereich für einen Editor für digitale Arbeitsblätter
demonstrieren wollen.

### Welche gesellschaftliche Herausforderung willst du mit dem Projekt angehen? \*

(max. 175 Wörter)

Wir wollen will erreichen, dass Lehrende kollaborativ und mit minimalen Aufwand
exzellente Lernmaterialien erstellen können. Lehrkäften und Dozierenden haben
unserer Meinung nach eine zentrale Rolle, damit aktuelle Herausforderungen im
Bildungsbereich (z.B. Heterogenität der Schülerschaft, soziale
Bildungsungleichheiten & Chancengerechtigkeit) gemeistert werden können. Dafür
brauchen sie u.a. die richtigen Werkzeuge, durch die eine zeitsparende
Unterrichtsvorbereitung und effiziente Materialerstellung möglich ist.

Im Zuge der Arbeit an dieser Vision sind wir auf eine technische Lücke gestoßen:
Es gibt bisher kein Framework, dass sowohl die Erstellung strukturierter
Dokumente (in unserem Fall digitale Arbeitsblätter) als auch
Echzeit-Kollaboration und eine WYSIWYG-User-Experience ermöglicht. Der typische
Prozess eines Arbeitsblattes – Erstellung durch Lehrkräfte, Bearbeitung durch
Lernende, anschließende Korrektur – lässt sich mit den heutigen
Editorframeworks, die meist nur zwischen Bearbeiten und Lesen unterscheiden,
schwer abbilden. Hier setzen wir an.

Wir sind überzeugt, dass ein solches Framework nicht nur im Bildungsbereich,
sondern auch in weiteren Feldern mit komplexen Dokumentenprozessen erheblichen
Mehrwert bietet – etwa bei technischen Dokumentationen und Konfigurationen, der
Erstellung von Formularen oder journalistischen bzw. juristischen Inhalten.

### Wie willst du dein Projekt technisch umsetzen? \*

(max. 175 Wörter)

Die technische Umsetzung basiert auf einem schema-orientierten Ansatz: Die
Dokumentstruktur wird – angelehnt an JSON Schema oder Typing-Frameworks wie
[zod](https://zod.dev/) und [io-ts](https://gcanti.github.io/io-ts/) – über klar
definierte Knotentypen beschrieben. Diese Typen legen nicht nur Eigenschaften
und erlaubte Operationen (z. B. Split/Merge) fest, sondern auch das Rendering
der jeweiligen Knoten.

Intern wird der Dokumentenbaum in einer flachen Struktur gespeichert, was
effiziente Updates in tief verschachtelten Bereichen ermöglicht. Das Schema
dient zudem als strukturierte Schnittstelle für LLMs, sodass Inhalte über AI
generiert, umgeschrieben oder ergänzt werden können.

Für die Echtzeit-Kollaboration wird ein CRDT-Framework wie
[Yjs](https://yjs.dev/) oder [Loro](https://loro.dev/) eingesetzt, wodurch
gleichzeitige Bearbeitung ohne Konflikte gewährleistet ist. In der
Prototypenphase wird evaluiert, ob die Rich-Text-Bearbeitung über spezielle
Blattknoten mit ProseMirror als Editor-Engine oder komplett im entwickelten
Framework umgesetzt wird.

Die Entwicklung erfolgt vollständig in TypeScript. Das Projekt wird unter einer
freien Apache-Lizenz auf GitHub veröffentlicht.

### Hast du schon an der Idee gearbeitet? Wenn ja, beschreibe kurz den aktuellen Stand und erkläre die geplanten Neuerungen. \*

(max. 100 Wörter)

Mit dem [Serlo‑Editor](https://de.serlo.org/editor) existiert bereits ein
Open‑Source‑Produkt, an dem wir federführend mitgearbeitet haben und das beide
Welten – WYSIWYG und strukturierte Inhalte – zusammenführt. Allerdings ist
dessen Kern so komplex und eng verzahnt, dass er nicht sinnvoll auf andere
Bereiche übertragbar ist. In einem
[Hackathon](https://github.com/kulla/hackathoern-collab-oer-editor) konnte
gezeigt werden, dass kollaborative Bearbeitung möglich ist. Ein
[weiterer Prototyp](https://github.com/kulla/2025-10-28-editor) demonstriert die
Möglichkeit eines WYSIWYG-Editors für strukturierte Inhalte mit nur rund 2.000
Zeilen Code. Gleichzeitig zeigte sich in anderen Prototypen, dass bestehende
Editor‑Frameworks kaum geeignet sind, strukturierte Dokumente wie einfache
Übungsaufgaben abzubilden
([Prototyp für ProseMirror](https://github.com/kulla/2025-11-15-prosekit-with-multiple-choice-exercise).
[Prototyp für Lexical](https://github.com/kulla/2025-11-08-lexical-with-multiple-choice-exercise)).

### Link zum bestehenden Projekt (falls vorhanden)

(optional)

https://github.com/kulla/collaborative-wysiwyg-editor-for-structured-data

### Welche ähnlichen Ansätze gibt es schon und was wird dein Projekt anders bzw. besser machen? \*

(max. 100 Wörter)

Auf der einen Seite gibt es erfolgreiche WYSIWYG-Editor-Frameworks wie
[Lexical](https://lexical.dev/), [ProseMirror](https://prosemirror.net/) und
[Slate.js](https://docs.slatejs.org/). Deren Datenmodell unterstützt jedoch
keine Strukturen, die sich in JSON als Objekte darstellen lassen – etwa eine
Übungsaufgabe, die als Objekt mit Aufgabenstellung und Lösung beschrieben wird.
Dadurch können komplexere Dokumentstrukturen nicht vorgegeben werden.

Auf der anderen Seite stehen formularbasierte Editoren wie
[H5P](https://h5p.org/), deren Nutzererfahrung im Vergleich zu modernen
WYSIWYG-Editoren eingeschränkter ist und die zudem keine gleichzeitige
Kollaboration ermöglichen.

Unser Ansatz kombiniert beide Welten, indem von Anfang an neben Listen auch
Objekte im Dokumentenbaum erlaubt werden. So können beliebige
Dokumentenstrukturen vorgegeben werden.

### Wer ist die Zielgruppe und wie soll dein Projekt sie erreichen? \*

(max. 100 Wörter)

Die Zielgruppe umfasst Organisationen und Einzelpersonen, die webbasierte
Lösungen zur kollaborativen Erstellung strukturierter Inhalte benötigen. Neben
EdTech-Initiativen und Bildungseinrichtungen, zählen hierzu auch Teams aus
anderen Bereichen wie Journalismus, dem Gesundheitswesen oder der
Softwareentwicklung.

Das Framework wird frei zugänglich über GitHub und NPM bereitgestellt. Um die
Zielgruppe zu erreichen, suchen wir den Austausch mit bestehenden Communities
rund um ProseMirror, Slate.js und Lexical. Erfolgreiche Konzepte aus dem Projekt
können perspektivisch in bestehende Open-Source-Editor-Ökosysteme einfließen.

Wir werden das Framework verwenden, um kollaborative und intuitive Erstellung
von digitalen Arbeitsblättern zu ermöglichen. Dies wiederum nutzt Institutionen
und Ed-Tech-Anbieter, die Lernmanagementsysteme für das Bildungssystem
bereitstellen.

### Skizziere kurz die wichtigsten Meilensteine, die im Förderzeitraum umgesetzt werden sollen. \*

(max. 100 Wörter)

Limit this field to 100 words.

## 3. Team & Erfahrung

### Bewerbt ihr euch als Team um die Förderung? \*

- [x] ja
- [ ] nein

### Für Teams: Namen der Teammitglieder (verbindliche Nennung)

Hinweis: Die Teams können aus bis zu 4 Personen bestehen. (optional – bitte nur
leer lassen, wenn du dich allein bewerben möchtest | max. 30 Wörter)

Limit this field to 30 words.

### An welchen Software-Projekten hast du / habt ihr bisher gearbeitet? Bei Open-Source-Projekten bitte einen Link zum Repository angeben.

Hinweis: Max. 3 Projektbeispiele angeben (mit Namen und/oder Link zum
Repository) (optional | max. 100 Wörter)

Limit this field to 100 words.

- Serlo Editor
- Serlo Plattform
- ...

### Wie viele Stunden willst du (bzw. will das Team) in den 6 Monaten Förderzeitraum insgesamt an der Umsetzung arbeiten? \*

Hinweis: Bitte nur eine Zahl eintragen - max. 950 h für eine Person oder max.
1.900 h für Teams. Die Maximalförderung für die reguläre Förderphase beträgt
47.500€ für eine Person oder 95.000€ für Teams. Wie die Fördersummen berechnet
werden, kann auf https://www.prototypefund.de/faq nachgelesen werden.

1680h

### Erfahrung, Hintergrund, Motivation, Perspektive: Was sollen wir über dich (bzw. euch) wissen und bei der Auswahl berücksichtigen?

(optional | 100 Wörter)

Limit this field to 100 words.

- Kulla: Ausgebildete Lehrkraft für Mathematik und Physik und
  Bildungsbegesiterte Person. Hat über 10 Jahre lang ehren- und hauptamtlich
  beim Serlo mitgewirkt, welche monatlich 600.000 bis 1.000.000 Schüler\*innen
  erreicht. Kulla hat außerdem das freie Lernbuch "Mathe für Nicht-Freaks"
  gegründet und geschrieben, welches geschätzt 50% aller MINT-Studienanfänger
  erreicht und ihnen einen einfachen Übergang von der Schul- in die
  Universitätsmathematik ermöglichst

## 4. Second Stage

### Beantragst du die viermonatige Second-Stage-Förderung nach Ablauf der sechsmonatigen regulären Förderung? \*

- [ ] ja
- [x] nein

### Wenn du eine Verlängerung beantragen möchtest: Erzähle uns kurz, was dein Projekt braucht, um aus dem Prototypen-Stadium herauszukommen und wie du dein Projekt in den vier Monaten nachhaltig aufbauen willst.

(optional - verpflichtend wenn du/ihr euch für die Second-Stage-Förderung
bewirbst bzw. bewerbt | 175 Wörter)

Limit this field to 175 words.

### Skizziere kurz die wichtigsten Meilensteine, die in der viermonatigen Verlängerung deines Förderzeitraum umgesetzt werden sollen.

(optional - verpflichtend wenn du/ihr euch für die Second-Stage-Förderung
bewirbst bzw. bewerbt | 100 Wörter)

Limit this field to 100 words.

## 5. Bestätigungen

### Ich habe die Checkliste für Bewerber*innen gelesen. *

Checkliste auf Deutsch:
https://www.prototypefund.de/uploads/Publikationen_und_Onepager/Checkliste_Bewerbung.pdf
Checklist in English:
https://www.prototypefund.de/uploads/Publikationen_und_Onepager/Checklist_Application.pdf

on

### Ich bin über 18 Jahre alt und habe meinen Hauptwohnsitz bzw. den GbR-Sitz meines Teams in Deutschland. \*

on

### Ich bin damit einverstanden, die Projektergebnisse unter einer Open-Source-Lizenz (z. B. MIT-Lizenz), öffentlich zugänglich (z. B. über Github/Gitlab/Codeberg) zur Verfügung zu stellen. \*

on
