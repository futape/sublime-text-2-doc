Bedienung & Funkionen
===================

1.  [Panels](#panels)
2.  [Undo & Redo](#undo--redo)
3.  [Multiple Cursors](#multiple-cursors)
4.  [Auswahl](#auswahl)
    1.  [Column Selection](#column-selection)
    2.  [Auswählen von Entitäten](#ausw%C3%A4hlen-von-entit%C3%A4ten)
5.  [Tastenkombinationen](#tastenkombinationen)
    1.  [Gewohnte Tastenkombinationen (Gemischt)](#----gewohnte-tastenkombinationen-gemischt-----und-erweiterungen)
        1.  [Anwendung & Dateien](#anwendung--dateien)
        2.  [Navigation](#navigation)
        3.  [Editor](#editor)
        4.  [Panels](#panels-1)
        5.  [Darstellung](#darstellung)
    2.  [Anwendung & Navigation](#anwendung--navigation)
        1.  [Tabs & Dateien](#tabs--dateien)
        2.  [Layout & Views](#layout--views)
    3.  [Editor](#editor-1)
        1.  [Einfügen & Entfernen](#einf%C3%BCgen--entfernen)
        2.  [Auswahl & Cursor](#auswahl--cursor)
        3.  [Verschieben](#verschieben)
        4.  [Manipulieren](#manipulieren)
        5.  [Navigation](#navigation-1)
    4.  [Panels](#panels-2)
    5.  [Tools](#tools)
        1.  [Hilfsprogramme & Dienste](#hilfsprogramme--dienste)
        2.  [Den Text beeinflussend](#den-text-beeinflussend)
    6.  [Darstellung](#darstellung-1)





Panels
------

Die **Search & Replace** Panels können mittels `Ctrl + F` bzw. `Ctrl + H` aufgerufen werden.
Beide bieten Unterstützung für Perl-kompatible reguläre Ausdrücke. Ein Zeilenumbruch kann im Suchterm durch Drücken von `Ctrl + Enter` eingefügt werden.

Im **Search Panel** kann durch Drücken von `Enter` der nächsten Treffer und durch `Shift + Enter` der vorherigen Treffer ausgewählt werden. Beim Drücken von `Alt + Enter` werden *alle* Treffer ausgewählt (mehrere Cursors).  
Ist das Search Panel nicht aktiv, können dieselben Aktionen mithilfe der `F3` Taste vollzogen werden. Sie übernimmt dabei die Rolle der `Enter` Taste. Dabei wird das zuletzt verwendete Suchmuster bzw. Suchterm verwendet.

Im **Replace Panel** werden beim Betätigen von `Ctrl + Alt + Enter` alle Treffer ersetzt.

Wie auch im Search Panel, kann im **File Search** Panel, geöffnet durch `Ctrl + Shift + F`, mit `Enter` zum nächsten Treffer gesprungen werden. Auch mittels `F4` kann in der Liste der Treffer vorangeschritten werden. Durch `Shift + F4` kann zurückgegangen werden.  
Das ***Where*** Feld in diesem Panel dient zur Angabe von Orten, die in die Suche mit einbezogen werden sollen. Orte können auf die folgenden Arten angegeben werden und durch Kommas (",") voneinander getrennt werden.

+   Eindeutige Verzeichnisse (Unix-Pfade, auch unter Windows)
+   Glob Muster (durch vorangestelltes "-" aus Liste ausschließen)
+   Platzhalter: `<open folders>` und `<open files>`

Ein weiteres Panel ist das **GoTo Anything** Panel, welches mittels `Ctrl + P` aufgerufen werden kann. Es bietet diverse Möglichkeiten um zwischen Dateien hin und her oder an bestimmte Stellen in Dateien zu springen. Auch kann mit GoTo Anything *in* oder in den aktuell geöffneten Dateien und Verzeichnissen *nach* Dateien gesucht werden.  
Der eingegebene Suchterm gibt den Dateinamen, nach dem gesucht werden soll, an. Zusätzlich können durch bestimmte Zeichen weitere Direktiven für die Suche angegeben werden. Diese Direktiven sind unten aufgelistet.

+   <code>@<em>&lt;symbol&gt;</em></code>: Sucht nach einem Vorkommen des als *`<symbol>`* angegebenen Symbols. Ein Symbol ist eine Entität, die von einer Syntax Definition definiert wurde.  
    Diese Direktive kann auch direkt mittels `Ctrl + R` verwendet werden.
+   <code>#<em>&lt;search&gt;</em></code>: Sucht nach dem Text *`<search>`*. Dabei werden keine Wortbegrenzungen o.Ä. berücksichtigt, sondern der Term wird *irgendwo* im Text gesucht.  
    Diese Direktive kann auch direkt mittels `Ctrl + ;` verwendet werden.
+   <code>:<em>&lt;line_number&gt;</em></code>: Setzt den Cursor in die mittels *`<line_number>`* angegebene Zeile.  
    Diese Direktive kann auch direkt mittels `Ctrl + G` verwendet werden.

Ähnlich wie das GoTo Anything Panel, sieht auch das **Commands** Panel aus. Dies dient zur Eingabe von definierten Commands (`.sublime-commands` Dateien) und kann mittels `Ctrl + Shift + P` aufgerufen werden.





Undo & Redo
----------

In der Historie der Änderungen an einer Datei/einem Buffer kann mittels `Ctrl + Z` zurück gegangen werden, und mittels `Ctrl + Shift + Z` voran gegangen werden. Die zuletzt durchgeführte Aktion kann durch `Ctrl + Y` wiederholt werden.  
Mit ***Undo/Redo Selection*** bzw. ***Soft Undo/Redo*** steht sogar die Möglichkeit zu Verfügung, die Bewegung des Cursors oder den Verlauf der Auswahl nachzuvollziehen. Mittels `Ctrl + U` wird zurück gegangen, mittels `Ctrl + Shift + U` wird vorwärts gegangen.





Multiple Cursors
---------------

`Alt + Shift + Up/Down` fügt einen Cursor in der nächsten Zeile an derselben horizontalen Position hinzu.  
`Up` fügt ihn in der nächsthöheren Zeile hinzu, `Down` fügt ihn in der nächsttieferen Zeile hinzu.

`Ctrl + Shift + L` teilt *eine* Auswahl über mehrere Zeilen in *mehrere separate* Auswahlen, eine je Zeile, mit je einem eigenen Cursor am Ende der Auswahl, auf.

Um mehrere Auswahlen oder Cursors wieder zu verwerfen und zu einer einfachen Auswahl zurückzukehren, kann `Esc` verwendet werden. Dabei werden alle bis auf die erste Auswahl aufgehoben.





Auswahl
-------

### Column Selection

Bei gedrückter `Shift` Taste mit der **rechten Maustaste** Auswahl ziehen.  
Zusätzliches Drücken von `Ctrl` ergänzt die Auswahl, `Alt` reduziert sie.

Bei Auswahlen über mehrere Zeilen oder von mehreren nicht zusammenhängenden Teilen, werden mehrere Cursors verwendet.



### Auswählen von Entitäten

Wie gewohnt kann mit `Shift + Up/Down/Left/Right` Text ausgewählt werden.  
Bei zusätzlichem Drücken von `Alt`, wird anstatt eines einzelnen Zeichens, ein gesamtes Wort ausgewählt (gilt für `Left` und `Right`).

Mittels `Ctrl + Shift + M` kann der Text innerhalb des **Klammernpaares**, in dessen Mitte sich der Cursor aktuell befindet, ausgewählt werden.

Dasselbe funktioniert auch mit **HTML-Tag-Paaren** indem `Ctrl + Shift + A` gedrückt wird.

`Ctrl + Shift + J` wählt den Textblock um den Cursor mit demselben oder einem höheren **Indentation Level** aus.

Der Text, der zum **Scope** (Syntax Definition), in dem sich der Cursor aktuell befindet, gehört, kann durch Drücken von `Ctrl + Shift + Space` ausgewählt werden.

`Ctrl + L` fügt die **Zeile**, in der sich der Cursor aktuell befindet, der Auswahl hinzu. Dabei werden keine zusätzlichen Cursors hinzugefügt, sondern bestehende Auswahlen erweitert.

`Ctrl + D` wählt das am Cursor grenzende **Wort** aus. Bei wiederholtem Drücken oder falls bereits etwas selektiert ist, wird die nächste Instanz des ausgewählten Textes der Auswahl hinzugefügt.  
Mittels `Ctrl + K` kann die zuletzt ausgewählte Instanz wieder zum Entfernen von der Auswahl vorgemerkt werden. Sie wird beim Auswählen der nächsten Instanz durch `Ctrl + D` von der Auswahl entfernt.  
Anstatt diese Tastenkombination mehrmals zu wiederholen, kann auch einfach `Alt + F3` verwendet werden um alle Instanzen des aktuell ausgewählten Textes der Auswahl hinzuzufügen. Siehe dazu auch *Search Panel* unter [*Panels*](#panels).  
Beim Auswählen der nächsten Instanzen wird für jede neue Auswahl ein eigener Cursor hinzugefügt.





Tastenkombinationen
-----------------

<h3>
    Gewohnte Tastenkombinationen (Gemischt)<br />
    <em>... und Erweiterungen</em>
</h3>

#### Anwendung & Dateien

+   `Ctrl + Q`: Sublime Text beenden.
+   `F11`: Aktiviere Vollbild Modus
    +   `Shift`: Aktiviere *Distraction Free* Modus

<!---->

+   `Ctrl + O`: Datei öffnen.
+   `Ctrl + S`: Datei/Buffer speichern.
    +   `Shift`: Mit angegebenem Dateinamen im angegebenen Verzeichnis speichern.

<!---->

+   `Ctrl + N`: Neuen Tab öffnen.
    +   `Shift`: Neues Fenster öffnen.
+   `Ctrl + W`: Tab schließen.
    +   `Shift`: Fenster und alle darin enthaltenen Tabs schließen.
+   `Ctrl + Shift + T`: Zuletzt geschlossenen Tab wieder öffnen.

#### Navigation

+   `Ctrl + Tab`: Zwischen Tabs wechseln, den Tab(-Wechsel)-Verlauf in entgegengesetzter Richtung folgend. Beim Erreichen des ersten protokollierten Tab-Wechsels wird erneut vom Ende des Verlaufs begonnen.
    +   `Shift`: Den Tab-Verlauf in Richtung Ende folgend, wechseln.

#### Editor

+   `Ctrl + Z`: Undo.
    +   `Shift`: Redo.
+   `Ctrl + Y`: Zuletzt durchgeführte Aktion wiederholen.

<!---->

+   `Ctrl + C`: Ausgewählten Text bzw. gesamte aktuelle Zeile, falls nichts ausgewählt ist, in Zwischenablage kopieren.
+   `Ctrl + X`: Ausgewählten Text bzw. gesamte aktuelle Zeile, falls nichts ausgewählt ist, in Zwischenablage kopieren und aus Buffer entfernen.
+   `Ctrl + V`: Text aus Zwischenablage an der Position des Cursors einfügen. Aktuell ausgewählter Text wird überschrieben.
    +   `Shift`: Eingefügten Text automatisch passend einrücken.

<!---->

+   `Ctrl + A`: Gesamten Buffer auswählen.
    +   `Shift`: Wählt den Text zwischen dem Tag-Paar, in dem sich der Cursor aktuell befindet, aus.
+   `Shift + Up/Down/Left/Right`: Fügt Text zu der aktuellen Auswahl hinzu. Up und Down erweitern die Auswahl um Text in der nächsthöheren (Up) bzw. -tieferen (Down) Zeile, Left und Right fügen das Zeichen links (Left) bzw. rechts (Right) von der Auswahl hinzu.
    +   `Alt`: Fügt für Left und Right nicht nur ein einzelnes Zeichen, sondern das gesamte angrenzende Wort hinzu.
+   `Ctrl + Left/Right`: Bewegt den Cursor anstatt nur um ein Zeichen nach links (Left) oder rechts (Right), um ein gesamtes Wort.

<!---->

+   `Tab`: Rückt aktuelle Zeile ein.
    +   `Shift`: Rückt Zeile aus.

#### Panels

+   `Ctrl + F`: Suche in Buffer nach Text.
    +   `Shift`: Suche (und ersetze) in Dateien.
+   `Ctrl + H`: Suche und ersetze Text in Buffer.
    +   `Shift`: Ersetze aktuell ausgewählten Treffer und suche nach nächstem.

<!---->

+   `Ctrl + Space`: Wählt die nächste Auto-Vervollständigungs-Option aus oder blendet diese ein falls noch nicht geschehen.

#### Darstellung

+   `Ctrl + -/+`: Die Editor Schriftgröße verändern. `+` erhöht die Schriftgröße, `-` reduziert sie.



### Anwendung & Navigation

#### Tabs & Dateien

+   <code>Alt + <em>&lt;num&gt;</em></code>: Wechselt zu dem durch *`<num>`* referenzierten Tab. *`<num>`* ist dabei die Nummer des Tabs. Gezählt wird dabei von links nach rechts, begonnen bei 1. 0 entspricht dem zehnten Tab. Bei einer Zahl außerhalb der verfügbaren Tabs, wird keine Aktion durchgeführt. Die Taste für *`<num>`* muss eine der Tasten `1...9/0` sein (nicht auf dem Nummernblock).
+   `Ctrl + PageUp/PageDown`: Wechselt zum Tab, links (`PageUp`) bzw. rechts (`PageDown`) des aktuellen Tabs. Beim Erreichen des erste Tabs, wird der letzte Tab ausgewählt (`PageUp`) und beim Erreichen des letzten Tabs, wird der erste Tab ausgewählt (`PageDown`).

<!---->

+   `Alt + O`: Wechselt zwischen *Header* und *Implementation* Datei.

#### Layout & Views

+   `Ctrl + 1...4/0`: Legt den Input Fokus auf den entsprechenden View. Dieser ist in der Rasterdarstellung der obere, linke für `1`, der obere, rechte für `2`, der untere, linke für `3` und der untere, rechte für `4`.  
    Bei einer horizontalen Anordnung entspricht `1` dem linken, `2` dem zweiten von links, `3` dem dritten von links und `4` dem vierten von links.  
    Ähnlich verhält es sich bei einer vertikalen Anordnung: `1` fokussiert den obersten View, `2` den zweiten von oben und `3` den dritten von oben.  
    Bei `0` wird der Fokus auf die Sidebar gelegt. Existiert der angegebene View nicht, wird keine Aktion durchgeführt.
    +   `Shift`: Verschiebt den aktuellen Tab in den angegebenen View. `0` (für die Sidebar) kann dabei nicht verwendet werden und hat keinen Effekt.



### Editor

#### Einfügen & Entfernen

+   `Ctrl + Backspace/Delete`: Löscht das Wort vor (`Backspace`) bzw. nach (`Delete`) dem Cursor.
    +   `Shift`: Löscht alles vom Cursor bis zum Anfang (`Backspace`) bzw. Ende (`Delete`) der Zeile.
+   `Ctrl + K - K/Backspace`: Alias für `Ctrl + Shift + Backspace` (`K`) bzw. `Ctrl + Shift + Delete` (`Backspace`).
+   `Ctrl + Shift + K/D`: Löscht die aktuelle Zeile (`K`) oder dupliziert sie bzw. den ausgewählten Text (`D`).

<!---->

+   `Ctrl + Enter`: Fügt einen Zeilenumbruch am Ende der Zeile, in der sich der Cursor aktuell befindet, ein.
    +   `Shift`: Fügt ihn anstatt am Ende, *vor* der Zeile ein.
+   `Ctrl + J`: Entfernt den Zeilenumbruch am Ende der aktuellen Zeile und verkettet sie mit der nächsten Zeile, getrennt durch ein Leerzeichen.

<!---->

+   `Ctrl + ]/[`: Alias für `Tab` (`]`) bzw. `Shift + Tab` (`[`).
+   `Ctrl + /`: Kommentiert die aktuelle Auswahl bzw. die betroffenen Zeilen, oder die aktuelle Zeile, falls nichts ausgewählt ist, aus (wenn möglich als einzeiliger Kommentar) oder entfernt den Kommentar.
    +   `Shift`: Kommentiert den ausgewählten Text als mehrzeiliger Kommentar aus oder entfernt den Kommentar.
+   `Alt + .`: Fügt für einen öffnenden Tag ohne schließendes Gegenstück, in dessen *Inhalt* sich der Cursor aktuell befindet, einen schließenden Tag ein.
+   `Alt + Shift + W`: Auswahl mit Tag umschließen.

#### Auswahl & Cursor

+   `Alt + Left/Right`: Alias für `Ctrl + Left/Right`.
+   `Ctrl + L`: Fügt die Zeile, in der sich der Cursor aktuell befindet, der Auswahl hinzu. Dabei werden keine zusätzlichen Cursors hinzugefügt, sondern bestehende Auswahlen erweitert.

<!---->

+   `Ctrl + Shift + M/A/J/Space`: Wählt den Text zwischen einem Klammernpaar (`M`) bzw. einem Tag-Paar (`A`), in dessen Mitte sich der Cursor aktuell befindet, oder die Zeilen eines Blocks, in dem sich der Cursor aktuell befindet, mit demselben oder einem höheren Indentation Level (`J`) bzw. desselben Scopes (Syntax Definition), aus.
+   `Ctrl + M`: Springt mit dem Cursor zwischen der schließenden und der öffnenden Klammer des Klammernpaares, in dessen Mitte sich der Cursor aktuell befindet, hin und her.

<!---->

+   `Ctrl + D`: Falls nichts ausgewählt ist, wird das Wort, in dem sich der Cursor aktuell befindet, ausgewählt. Anderenfalls, wird die nächste Instanz des ausgewählten Textes zur Auswahl hinzugefügt. Dabei werden mehrere Cursors verwendet.
+   `Ctrl + K`: Merkt eine mittels `Ctrl + D` hinzugefügte Auswahl für dessen Aufhebung vor. Diese wird vollzogen sobald die nächste Instanz mittels `Ctrl + D` ausgewählt wird.
+   `F3`: Sucht nach dem nächsten Treffer des zuletzt verwendeten Suchterms (*Search Panel*) und selektiert den entsprechenden Text.
    +   `Shift`: Wählt anstatt des nächsten Treffers, den vorherigen Treffer aus.
    +   `Ctrl`: *Quick Find*. Sucht nicht auf Basis des zuletzt verwendeten Suchterms, sondern nutzt den aktuell ausgewählten Text oder das Wort, in dem sich der Cursor aktuell befindet, falls nichts ausgewählt ist, als Suchterm. Der verwendete Suchterm wird automatisch in das *Search Panel* sowie in das *Replace Panel* eingefügt. Kann kein Text für den Suchterm ausgemacht werden, passiert nichts. Alternativ kann auch `Ctrl + E`, gefolgt von `F3` verwendet werden.
    +   `Alt`: *Quick Find All*. Wie `Ctrl + F3`, wählt aber direkt *alle* Treffer aus.

<!---->

+   `Shift + Up/Down`: Die nächsthöhere (`Up`) bzw. -tiefere (`Down`) Zeile wird ...
    +   `Alt`: ... um einen Cursor an derselben horizontalen Position wie der aktuelle Cursor oder, im Falle einer Auswahl, dem Ende des Auswahl, erweitert.
    +   `Ctrl`: ... mit den ausgewählten Zeilen oder, falls nichts ausgewählt ist, der aktuelle Zeile ausgetauscht.
+   `Shift + MouseRight`: *Column Selection*. Bei gedrückter `Shift` Taste, mit gedrückter **rechter Maustaste** eine viereckige Auswahl ziehen. Siehe dazu [*Column Selection*](#column-selection).
    +   `Ctrl`: Fügt Auswahl zur aktuellen Auswahl hinzu.
    +   `Alt`: Subtrahiert Auswahl von aktueller Auswahl.
+   `Ctrl + Shift + L`: Teilt *eine* Auswahl über mehrere Zeilen in *mehrere* Auswahlen, mit je einem Cursor am Ende der Auswahl, auf.
+   `Esc`: Reduziert mehrere Auswahlen oder Cursors auf eine einfachen Auswahl indem alle bis auf die erste Auswahl aufgehoben werden.

#### Verschieben

+   `Ctrl + Shift + Up/Down`: Siehe *Shift + Up/Down* > *Ctrl* unter [*Auswahl & Cursor*](#auswahl--cursor).
+   `Ctrl + T`: Texte mehrerer Auswahlen austauschen.

#### Manipulieren

+   `Ctrl + K - U/L`: Transformiert den ausgewählten Text oder das Wort, in dem sich der Cursor aktuell befindet, falls nichts ausgewählt ist, zu Groß- (`U`) bzw. Kleinbuchstaben (`L`).

#### Navigation

+   `Ctrl + U`: *Soft Undo*. Ähnlich wie `Ctrl + Z`, erlaubt aber eine granularere Navigation in der Historie mit der Möglichkeit sogar Cursor Bewegungen, Hinzufügen von zusätzlichen Cursors oder Auswählen von Text nachzuvollziehen.
    +   `Shift`: *Soft Redo*. Das *softe* Gegenstück zu `Ctrl + Shift + Z`.

<!---->

+   `Ctrl + Up/Down`: Um eine Zeile nach oben (`Up`) oder unten (`Down`) scrollen.



### Panels

+   `Ctrl + I`: *Incremental Find*. Ähnlich wie das *Search Panel* hinter `Ctrl + F`, mit der Ausnahme, dass nach Ausführen der Suche, das Panel automatisch direkt wieder geschlossen wird.
+   `Ctrl + E`: Fügt den aktuell ausgewählten Text oder das Wort, in dem sich der Cursor aktuell befindet, falls nichts ausgewählt ist, als Suchterm in das *Search Panel* und in das *Replace Panel* ein.
    +   `Shift`: Fügt den Text als Ersetzungstext anstatt als Suchterm in das *Replace Panel* ein. Die Suchterme im *Search Panel* und im *Replace Panel* bleiben unberührt.
+   `F4`: Zeigt bzw. springt zum nächsten Ergebnis (*Result*) einer *File Search* Operation oder eines *Build* Prozesses.
    +   `Shift`: Zeigt nicht das nächste, sondern das vorherige Ergebnis.

<!---->

+   `Ctrl + P`: Öffnet einen Dialog/ein Panel in Form eines *Overlays*, genannt *Palette*, für ...
    +   ... die Eingabe von *GoTo Anywhere* Direktiven.
    +   `Shift`: ... die Eingabe von *Commands*.
    +   `Alt`: ... das Wechseln des geöffneten Projekts (*Switch Project in Window*).
+   `Ctrl + ;/R/G`: Alias für `Ctrl + P`, beginnt aber direkt mit einem Eingabefeld für <code>@<em>&lt;symbol&gt;</em></code> (`R`), <code>:<em>&lt;line_number>&gt;</em></code> (`G`), <code>#<em>&lt;search&gt;</em></code> (`;`).

<!---->

+   `Alt + /`: Alias für `Ctrl + Space`.



### Tools

#### Hilfsprogramme & Dienste

+   `Ctrl + Shift + [/]`: *Code Fold* (`[`) bzw. *Code Unfold* (`]`).
+   `F2`: Springt zum nächsten Bookmark im aktuellen Buffer.
    +   `Shift`: Springt zum vorherigen Bookmark.
    +   `Ctrl`: Fügt Bookmark hinzu oder entfernt es.
        +   `Shift`: Entfernt alle Bookmarks.
+   `F6`: Das *Spell Checking* aktivieren.
    +   `Ctrl`: Zum nächsten Rechtschreibfehler springen.
        +   `Shift`: Springt zum vorherigen Fehler.

<!---->

+   `Ctrl + Alt + Q`: Startet Aufnahme für Macros.
    +   `Shift`: Spielt ein Macro ab bzw. wendet es an.
+   `Ctrl + B`: Startet den *Build* Prozess für das ausgewählte *Build System*.

<!---->

+   `Ctrl + Shift + Alt + P`: Zeigt kurzzeitig den Scope (Syntax Definition) des Textes, in dem sich der Cursor aktuell befindet, in der Statusleiste an.

#### Den Text beeinflussend

+   `Alt + Q`: Fügt in den Zeilen des Absatzes, in dem sich der Cursor aktuell befindet, bzw. der Absätze, über die sich die aktuelle Auswahl erstreckt, an der horizontalen Position des *Rulers* einen Zeilenumbruch ein.  
    Als *Absätze* werden hier Textblöcke, welche mittels Leerzeilen voneinander getrennt sind, bezeichnet.
+   `F9`: Sortiert die ausgewählten Zeilen bzw. alle Zeilen im Buffer, falls nichts ausgewählt ist, in alphabetische Reihenfolge, ohne Rücksicht auf Groß- und Kleinschreibung.
    +   `Shift`: Sortiert *mit* Rücksicht auf Groß- und Kleinschreibung.



### Darstellung

+   `Alt + Shift + 1...5/8/9`: Teilt das Fenster in mehrere Views auf.  
    Bei `1` wird das Fenster auf 1 View reduziert, `2`, `3` und `4` zeigen 2, 3 bzw. 4 Views nebeneinander an, `8` und `9` teilen das Fenster auf 2 (`8`) bzw. 3 (`9`) Views untereinander auf, und `5` zeigt 4 Views als Raster (2 x 2) an.
+   `Ctrl + K - B`: Öffnet bzw. schließt die Sidebar.
+   <code>Ctrl + `</code>: Öffnet bzw. schließt die Python Konsole.

<!---->

+   `Ctrl + =`: Alias für `Ctrl + -`.
