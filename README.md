# OpenMoji Mashup Bot

## Dokumentation
 
### Ablauf
Von 12 bis ca 13:30-14:00 Uhr Emojis [HfG OpenMoji](#emoji-source) aussortiert und nur die „richtigen“ Emojis rausgesucht.  
Diese haben wir dann in Einzelteile (Münder, Augen, Objekte & Hintergründe) mit Adobe Illustrator zerlegt und gruppiert abgespeichert.

Um die Emoji Teile dann automatisch zusammen zu setzen haben wir begonnen in JavaScript mit Node.js ein Programm zu schreiben,
welches uns zufällig verschiedene Teile auswählt und diese zu einem Emoji zusammensetzt.
Hierfür verwenden wir ein [Node Modul](https://www.npmjs.com/package/xpath), mit dem xml-Dateien be-/verarbeitet werden können.

### Emoji-Aufbereitung
Zuerst haben wir die Emojis aus der GitHub Repository aussortiert, so dass wir nur noch die "normalen" Emojis haben.   
Danach hat jeder von uns eine Kopie des Ordners erhalten und wir haben uns die Bearbeitung / Aufbereitung aufgeteilt.  
Wir haben jeder alle Emojis in Illustrator geöffnet und alle bis auf die uns zugewiesenen Elemente gelöscht.  
Noah hat die Augen aussortiert, Luca die Münder, Steve die Hintergründe und Marc alle anderen Objekte.
Bei manchen Emojis gab es noch Elemente die an den Mündern oder Augen angesetzt waren, bei denen haben wir jeweils gemeinsam entschieden wer es behält.  
Zum Schluss haben wir alle Emojis gesammelt und in die Repo eingebunden.

### Software
Zuerst haben wir ein neues Node.js Projekt erstellt um dort unser Script zu erstellen.  
Dies liest mit dem npm-Modul [fs](https://www.npmjs.com/package/fs) die Ordner aus und speichert alle Dateien in einem Array.

Aus diesem wird dann zufällig je Kategorie eine Datei ausgewählt und ebenfalls abgespeichert.  
Um aus dem jeweiligen SVG die relevanten Daten zu extrahieren und verarbeiten verwenden wir das npm-Modul [xpath](https://www.npmjs.com/package/xpath),
welches es uns erlaubt Dateien im XML-Format (d.h. auch SVGs) mit einer gewissen Terminologie zu durchsuchen (vgl. RegEx).
Hierbei suchen wir alle Gruppen- und Style-Tags und speichern diese, nachdem die Namen der beiden Tags mit der Kategorie versehen wurden, in einem weiteren Array.  

Nachdem alle Dateien durchsucht und extrahiert worden sind wird der Array mit dem npm-Modul [mustache](https://www.npmjs.com/package/mustache) in eine Template-Datei
eines leeren SVGs eingefügt und diese abgespeichert.



### Emoji-Source
This is an emoji mashup bot using the OpenMoji data set.

Open-source emojis for designers, developers and everyone else! OpenMoji is an open-source project of the HfG Schwäbisch Gmünd by Benedikt Groß, Daniel Utz, 50+ students and external contributors.

👉 OpenMoji.org/
🐙 github.com/hfg-gmuend/openmoji
