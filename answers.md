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

- Framework entwickeln, um

### Welche gesellschaftliche Herausforderung willst du mit dem Projekt angehen? \*

(max. 175 Wörter)

Ich will erreichen, dass Lehrende kollaborativ und mit möglichst wenig Aufwand
exzellente Lernmaterialien erstellen können. Als Softwareentwickler bin ich
dabei auf eine Lücke gestoßen: Auf der einen Seite gibt es exzellente Frameworks
für kollaborative WYSIWYG-Editoren wie ProseMirror oder Lexical, deren
Datenmodell aber keine strukturierten Objekte unterstützt. Auf der anderen Seite
gibt es formbasierte Editoren wie H5P, die aber eine schlechtere User-Experience
und keine gleichzeitige Kollaboration unterstützt. Ich will in einem Framework
beide Ansätze kombinieren. So kann dann nicht nur ein Google-Docs-ähnlicher
Editor für Lernmaterialien enstehen, auch andere Bereiche profitieren davon, in
denen strukturierte Dokumente mit komplexeren Workflows erstellt werden müssen.

### Wie willst du dein Projekt technisch umsetzen? \*

(max. 175 Wörter)

- Schema-basierter Ansatz: Dokument ist ein Baum von Knoten => Jeder Knoten hat einen Typ + Eigenschaften (u.a. das Rendering)
- Dokumentknoten werden ähnlich wie bei zod / io-ts beschrieben
- Speicherung erfolgt in einer flachen Struktur => So sind Änderungen direkt im Node möglich
- Basis ist ein CRDT-Framework wie Yjs => Kollaborative Bearbeitung
- Zwei Möglichkeiten: Leaf könnte Richtext sein oder nicht
- Sprache ist TypeScript

### Hast du schon an der Idee gearbeitet? Wenn ja, beschreibe kurz den aktuellen Stand und erkläre die geplanten Neuerungen. \*

(max. 100 Wörter)

- Beschreibung der beiden Alternativen Ansätze mit Lexical + ProseMirror
- Prototyp ohne ProseMirror
- Prototyp mit ProseMirror

### Link zum bestehenden Projekt (falls vorhanden)

(optional)

### Welche ähnlichen Ansätze gibt es schon und was wird dein Projekt anders bzw. besser machen? \*

(max. 100 Wörter)

- Frameworks für Rich-Text-Editoren wie ProseMirror, Slate.js oder Lexical => deren Datenmodell unterstützt keine strukturieten Daten
- Formbasierte Editoren wie H5P => schlechtere UX + keine kollaborative Bearbeitung
- Statemanagement-Lösungen wie Redux oder Zustand => keine Unterstützung für kollaborative Bearbeitung + keine Unterstützung schema-basierter Dokumentbeschreibung (Merging, Splitting, AI-Generierung)

### Wer ist die Zielgruppe und wie soll dein Projekt sie erreichen? \*

(max. 100 Wörter)

- Zielgruppe: Organisationen und Einzelpersonen, die webbasierte Lösungen zur kollaborativen Erstellung strukturierter Inhalte benötigen + inklusiv AI basierte Funktionen erstellen
- Beispiele: Bildungsinst

### Skizziere kurz die wichtigsten Meilensteine, die im Förderzeitraum umgesetzt werden sollen. \*

(max. 100 Wörter)

Limit this field to 100 words.

## 3. Team & Erfahrung

### Bewerbt ihr euch als Team um die Förderung? \*

ja
nein

### Für Teams: Namen der Teammitglieder (verbindliche Nennung)

Hinweis: Die Teams können aus bis zu 4 Personen bestehen.
(optional – bitte nur leer lassen, wenn du dich allein bewerben möchtest | max. 30 Wörter)

Limit this field to 30 words.

### An welchen Software-Projekten hast du / habt ihr bisher gearbeitet? Bei Open-Source-Projekten bitte einen Link zum Repository angeben.

Hinweis: Max. 3 Projektbeispiele angeben (mit Namen und/oder Link zum Repository)
(optional | max. 100 Wörter)

Limit this field to 100 words.

### Wie viele Stunden willst du (bzw. will das Team) in den 6 Monaten Förderzeitraum insgesamt an der Umsetzung arbeiten? \*

Hinweis: Bitte nur eine Zahl eintragen - max. 950 h für eine Person oder max. 1.900 h für Teams.
Die Maximalförderung für die reguläre Förderphase beträgt 47.500€ für eine Person oder 95.000€ für Teams. Wie die Fördersummen berechnet werden, kann auf https://www.prototypefund.de/faq nachgelesen werden.

### Erfahrung, Hintergrund, Motivation, Perspektive: Was sollen wir über dich (bzw. euch) wissen und bei der Auswahl berücksichtigen?

(optional | 100 Wörter)

Limit this field to 100 words.

## 4. Second Stage

### Beantragst du die viermonatige Second-Stage-Förderung nach Ablauf der sechsmonatigen regulären Förderung? \*

- [ ] ja
- [x] nein

### Wenn du eine Verlängerung beantragen möchtest: Erzähle uns kurz, was dein Projekt braucht, um aus dem Prototypen-Stadium herauszukommen und wie du dein Projekt in den vier Monaten nachhaltig aufbauen willst.

(optional - verpflichtend wenn du/ihr euch für die Second-Stage-Förderung bewirbst bzw. bewerbt | 175 Wörter)

Limit this field to 175 words.

### Skizziere kurz die wichtigsten Meilensteine, die in der viermonatigen Verlängerung deines Förderzeitraum umgesetzt werden sollen.

(optional - verpflichtend wenn du/ihr euch für die Second-Stage-Förderung bewirbst bzw. bewerbt | 100 Wörter)

Limit this field to 100 words.

## 5. Bestätigungen

### Ich habe die Checkliste für Bewerber*innen gelesen. *

Checkliste auf Deutsch: https://www.prototypefund.de/uploads/Publikationen_und_Onepager/Checkliste_Bewerbung.pdf
Checklist in English: https://www.prototypefund.de/uploads/Publikationen_und_Onepager/Checklist_Application.pdf

on

### Ich bin über 18 Jahre alt und habe meinen Hauptwohnsitz bzw. den GbR-Sitz meines Teams in Deutschland. \*

on

### Ich bin damit einverstanden, die Projektergebnisse unter einer Open-Source-Lizenz (z. B. MIT-Lizenz), öffentlich zugänglich (z. B. über Github/Gitlab/Codeberg) zur Verfügung zu stellen. \*

on
