## 1. Allgemeines

### Projekttitel \*

WYSIWYG JSON Editor Framework

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
Während WYSIWYG-Editoren wie Lexical oder ProseMirror eine hervorragende
Nutzererfahrung und Kollaboration bieten, unterstützen sie keine strukturierten
Inhalte. Formbasierte Editoren wie H5P ermöglichen strukturierte Inhalte,
bleiben aber in der Nutzererfahrung hinter heutigen Standards zurück und
unterstützen keine gleichzeitige Bearbeitung. Unser Framework kombiniert beide
Ansätze und erleichtert so die Erstellung strukturierter Dokumente – bspw. in
der Bildung, im Jorunalismus oder im Gesundheitswesen.

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
nicht abbilden. Hier setzen wir an.

Wir sind überzeugt, dass ein solches Framework nicht nur im Bildungsbereich,
sondern auch in weiteren Feldern mit komplexen Dokumentenprozessen erheblichen
Mehrwert bietet – etwa bei technischen Dokumentationen und Konfigurationen, der
Erstellung von Formularen oder journalistischen bzw. juristischen Inhalten.

### Wie willst du dein Projekt technisch umsetzen? \*

(max. 175 Wörter)

Die technische Grundlage bildet ein schema-basierter Ansatz: Die
Dokumentenstruktur wird ähnlich wie bei JSON Schema oder Validierungstools wie
zod / io-ts über ein Schema beschrieben. Dieses Schema beschreibt, welche Arten
von Knoten ein Dokument enthält und welche Eigenschaften sie besitzen (z.B. ob
und wie Knoten gesplittet und gemergt werden können). Dieses Schema definiert
insbesondere auch das Rendering der einzelnen Knoten.

Die Schema-Definition ermöglicht außerdem eine Beschreibung der
Dokumentenstruktur für LLMs, so dass im Editor Inhalte per generativer AI neu
erstellt oder bearbeitet werden kann.

Intern wird der Dokumentenbaum in einer flachen Struktur gespeichert. Dadurch
können auch tief verschachtelte Änderungen effizient beschrieben und
durchgeführt werden. Für die Echtzeit-Kollaboration wird von Beginn an ein
CRDT-Framework wie Yjs oder Loro eingesetzt, so dass konfliktfreie
Synchronisation zwischen mehreren Nutzer\*innen gewährleistet ist.

In der Prototypenentwicklung wird überprüft, ob es sinnvoll ist, als
Blatt-Knoten Richtext-Elemente auf Basis von ProseMirror zu ermöglichen oder ob
die RichText-Erstellung komplett im Framework abgebildet werden soll.

Das Projekt wird in TypeScript entwickelt und unter einer freien Apache-Lizenz
auf GitHub bereitgestellt.

### Hast du schon an der Idee gearbeitet? Wenn ja, beschreibe kurz den aktuellen Stand und erkläre die geplanten Neuerungen. \*

(max. 100 Wörter)

- Beschreibung der beiden Alternativen Ansätze mit Lexical + ProseMirror
- Prototyp ohne ProseMirror
- Prototyp mit ProseMirror

### Link zum bestehenden Projekt (falls vorhanden)

(optional)

### Welche ähnlichen Ansätze gibt es schon und was wird dein Projekt anders bzw. besser machen? \*

(max. 100 Wörter)

- Frameworks für Rich-Text-Editoren wie ProseMirror, Slate.js oder Lexical =>
  deren Datenmodell unterstützt keine strukturieten Daten
- Formbasierte Editoren wie H5P => schlechtere UX + keine kollaborative
  Bearbeitung
- Statemanagement-Lösungen wie Redux oder Zustand => keine Unterstützung für
  kollaborative Bearbeitung + keine Unterstützung schema-basierter
  Dokumentbeschreibung (Merging, Splitting, AI-Generierung)

### Wer ist die Zielgruppe und wie soll dein Projekt sie erreichen? \*

(max. 100 Wörter)

- Zielgruppe: Organisationen und Einzelpersonen, die webbasierte Lösungen zur
  kollaborativen Erstellung strukturierter Inhalte benötigen + inklusiv AI
  basierte Funktionen erstellen
- Beispiele: Bildungsinst

### Skizziere kurz die wichtigsten Meilensteine, die im Förderzeitraum umgesetzt werden sollen. \*

(max. 100 Wörter)

Limit this field to 100 words.

## 3. Team & Erfahrung

### Bewerbt ihr euch als Team um die Förderung? \*

ja nein

### Für Teams: Namen der Teammitglieder (verbindliche Nennung)

Hinweis: Die Teams können aus bis zu 4 Personen bestehen. (optional – bitte nur
leer lassen, wenn du dich allein bewerben möchtest | max. 30 Wörter)

Limit this field to 30 words.

### An welchen Software-Projekten hast du / habt ihr bisher gearbeitet? Bei Open-Source-Projekten bitte einen Link zum Repository angeben.

Hinweis: Max. 3 Projektbeispiele angeben (mit Namen und/oder Link zum
Repository) (optional | max. 100 Wörter)

Limit this field to 100 words.

### Wie viele Stunden willst du (bzw. will das Team) in den 6 Monaten Förderzeitraum insgesamt an der Umsetzung arbeiten? \*

Hinweis: Bitte nur eine Zahl eintragen - max. 950 h für eine Person oder max.
1.900 h für Teams. Die Maximalförderung für die reguläre Förderphase beträgt
47.500€ für eine Person oder 95.000€ für Teams. Wie die Fördersummen berechnet
werden, kann auf https://www.prototypefund.de/faq nachgelesen werden.

### Erfahrung, Hintergrund, Motivation, Perspektive: Was sollen wir über dich (bzw. euch) wissen und bei der Auswahl berücksichtigen?

(optional | 100 Wörter)

Limit this field to 100 words.

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
