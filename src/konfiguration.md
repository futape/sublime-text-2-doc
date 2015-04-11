Konfiguration
============

1.  [Konfigurations-Dateien](#konfigurations-dateien)
2.  [Menüs](#men%C3%BCs)
3.  [Quellen und Priorisierung](#quellen-und-priorisierung)
4.  [Konfigurations-Optionen](#konfigurations-optionen)
    1.  [Whitespace- und Indentation-Optionen](#whitespace--und-indentation-optionen)
    2.  [Darstellungs-Optionen](#darstellungs-optionen)
    3.  [Automatisierung](#automatisierung)
    4.  [Anwendungs- und System-Optionen](#anwendungs--und-system-optionen)
    5.  [Build-Systems- und Error-Optionen](#build-systems--und-error-optionen)
    6.  [Datei- und Verzeichnis-Optionen](#datei--und-verzeichnis-optionen)
    7.  [Eingabe-Optionen](#eingabe-optionen)

    



Konfigurations-Dateien
--------------------

Einstellungen werden in `.sublime-settings` Dateien abgelegt, welche wiederum in Package Verzeichnissen abgelegt werden.  
Es ist empfehlenswert selbst definierte Einstellungen ein einer `.sublime-settings` Datei im User Verzeichnis unterzubringen, da dieses Verzeichnis bei Updates von Sublime Text nicht verändert wird und die Einstellungen somit erhalten bleiben.

Die Dateien enthalten ein einfaches JSON-kodiertes Object, welches auf oberster Ebene als Keys die Namen der Konfigurations-Optionen, und als Werte die daszugehörigen Werte enthält.  
Obwohl der JSON-Standard Kommentare nicht erlaubt, scheinen einzeilige Kommentare (eingeleitet durch `//`) legitim zu sein.

Der Name einer solchen Datei kann quasi frei gewählt werden <!--!-->. Er kann z.B. beschreiben welche Einstellungen in der Datei definiert werden oder worauf sich diese beziehen, oder wofür die Datei verwendet wird bzw. wie sie behandelt wird. Besonderheiten, die bei der Wahl des Dateinamens beachtet werden sollten, werden unten aufgeführt.  
Eine Datei, welche denselben Namen (ohne Datei-Extension) wie eine vorhandene Syntax Definition (`.tmLanguage` Datei) hat, wird nur beim Bearbeiten von entsprechende Dateien (d.h. Dateien, bei denen die entsprechende Syntax Definition in Kraft tritt bzw. bei denen sie verwendet wird), beachtet.  
Ein weiterer besondere Datei ist `Distraction Free.sublime-settings`, welche nur beim Arbeiten im *Distraction Free* Modus angewendet wird.
Außerdem kann eine Angabe von <code>(<em>&lt;platform&gt;</em>)</code> am Ende des Dateinamens und mittels eines Leerzeichens vom Rest des Namens getrennt angegeben werden, wobei *`<platform>`* einer der folgenden Werte sein kann: `Windows`, `Linux`, `OSX`. Eine solche Datei wird nur auf der angegebenen Plattform bzw. auf dem angegebene Betriebssystem beachtet. Die einzige Ausnahme für solche Dateien bilden `.sublime-settings` Dateien im User Verzeichnis. Hier hat diese Angabe keinen besonderen Effekt.

Konfigurations-Dateien, welche sich nur auf einen bestimmten Dateityp bzw. eine bestimmte Syntax Definition beziehen, werden als ***File Type Settings*** bezeichnet und können nur Datei-spezifische Einstellungen, nicht aber welche für die Anwendung definieren.  
Alle anderen Dateien, welche Einstellungen global definieren, werden ***Global Settings*** genannt und können sowohl Datei- als auch Anwendungs-spezifische Einstellungen enthalten.  
Letztere werden gewöhnlich `Preferences.sublime-settings` genannt.





Menüs
-----

Auf Einstellungen kann über das ***Preferences*** Menü zugegriffen werden. Die Menüeinträge verweisen auf folgende Dateien.

+   ***Settings - Default***: <code><em>&lt;Data&gt;</em>/Packages/Default/Preferences.sublime-settings</code>
+   ***Settings - User***: <code><em>&lt;Data&gt;</em>/Packages/User/Preferences.sublime-settings</code>
+   ***Settings - More***:
    +   ***Syntax Specific - User***: <code><em>&lt;Data&gt;</em>/Packages/User/<em>&lt;syntax_definition&gt;</em>.sublime-settings</code>, wobei *`<syntax_definition>`* der Name der `.tmLanguage` Datei, welche die Syntax Definition für die aktuell geöffnete Datei enthält, ist.
    +   ***Distraction Free - User***: <code><em>&lt;Data&gt;</em>/Packages/User/Distraction Free.sublime-settings</code>

Die <code><em>&lt;Data&gt;</em>/Packages/Default/Preferences.sublime-settings</code> Datei sollte allerdings niemals geändert werden, da sie Standardwerte und Beschreibungen (als Kommentare) aller Konfigurations-Optionen enthält und so als Referenz genutzt werden kann. Außerdem wird sie bei Updates von Sublime Text vollständig zurückgesetzt (anders als die Dateien im User Verzeichnis).





Quellen und Priorisierung
-----------------------

Die Werte für Konfigurations-Optionen ergeben sich aus diversen Quellen, welche unten aufgeführt sind.

+   `.sublime-settings` Dateien
+   *Project Settings*
+   *Session Data* (Buffer-spezifische Einstellungen)
+   *Auto Settings*

***Project Settings*** sind Einstellungen, die für ein Projekt individuell in dessen Projektdefinition angegeben werden. Diese beschränken sich auf Datei-spezifische Einstellungen - Also solche, wie sie auch in File Type Settings verwendet werden.  
Für weiter Informationen siehe [*Projekte*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/file_management/file_management.html#projects).

***Session Data*** sind die Daten, die während der Arbeit *an* einer Datei/einem Buffer und *in* Sublime Text gesammelt werden. Sie ergeben sich hauptsächlich durch API Aufrufe, eingeleitet z.B. durch das Auswählen von Menüeinträgen oder Plugins.

***Auto Settings*** werden von Sublime Text selbstständig gewählt und umfassen Einstellungen wie die Auswahl der geeigneten Syntax (-Definition) für eine Datei oder den Indentation Stil.

Eine Konfigurations-Option kann von mehreren Quellen mit unterschiedlichen Werten belegt werden. Um den dominierenden Wert zu bestimmen, werden die Quellen nach festen Regeln priorisiert und die mit der stärksten Priorität gewählt.  
Die Priorisierung wird nach folgender Reihenfolge durchgeführt (unwichtig nach wichtig).

1.  **Global Settings**
    1.  **Default** Package
        1.  **Einfach**
        2.  Passende **Plattform** Angabe
    2.  Andere Packages
        1.  **Einfach**
        2.  **Passende **Plattform** Angabe
    3.  **User** Package
        1.  **Einfach**
        2.  *(Dateien mit Plattform Angabe existieren im User Verzeichnis nicht)*
2.  **Project Settings**
3.  Passende **File Type Settings**
    1.  *(Das Default Package wird keine Datei-Typ-spezifischen Konfigurations-Dateien enthalten)*
    2.  Andere Packages
        1.  **Einfach**
        2.  Passende **Plattform** Angabe
    3.  **User** Package
        1.  **Einfach**
        2.  *(Dateien mit Plattform Angabe existieren im User Verzeichnis nicht)*
4.  **Session Data**
5.  **Auto Settings**

Packages, die zu den *Andere Packages*-Punkten gehören (d.h. alle Packages außer **Default** und **User**), werden für die Priorisierung alphabetisch nach ihren Namen sortiert.





Konfigurations-Optionen
---------------------

Die folgenden Optionen können nur in den **Global Settings** genutzt werden und definieren hauptsächlich wie sich die Anwendung verhält.

+   `theme`: Das Theme, welches das Aussehen der Anwendung definiert. Erwartet den Dateinamen einer `.sublime-theme` Datei (inkl. Dateiendung)
+   `scroll_speed`: Definiert wie schnell sich beim weich auslaufenden Scrollen bewegt werden soll. `0` deaktiviert das auslaufende Scrollen, `1` gibt die initiale Geschwindigkeit an, `0 < scroll_speed < 1` verlangsamt die Bewegung und ein Wert `> 1` erhöht die Geschwindigkeit.
+   `hot_exit`: Wenn diese Option aktiviert ist, wird beim Schließen von ungesicherten Dateien nicht nachgefragt. Die Dateien werden zwischengespeichert und ihr Zustand beim nächsten Start von Sublime Text wiederhergestellt.
+   `remember_open_files`: Falls aktiviert, werden die, beim letzten Beenden von Sublime Text geöffneten, Dokumente beim nächsten Start automatisch wieder geöffnet.
+   `close_windows_when_empty`: Falls aktiviert, wird das Sublime Text Fenster beim Schließen des letzten geöffneten Tabs ebenfalls geschlossen. Anderenfalls bleibt ein leeres Fenster geöffnet.
+   `show_full_path`: Zeigt anstatt nur dem Dateinamen den gesamten Pfad der geöffneten Datei in der Titelleiste des Fensters an.
+   `preview_on_click`: Falls aktiviert, wird bei einem einfachen Klicken auf eine Datei in der Sidebar eine Vorschau des Inhalts der Datei angezeigt.  
    Diese Vorschau wird auch als ***Transient View*** bezeichnet und wird erst durch das Bearbeiten des Inhalts zu einem echten Buffer und erhält einen eigenen Tab. *Ein Transient* View kann durch Drücken von `Esc` verlassen werden. Durch einen Doppelklick auf eine Datei wird die Datei direkt in einem Tab geöffnet.
+   `folder_exclude_patterns`: Eine Liste von Glob Mustern. Passende Verzeichnisse werden aus der Sidebar, GoTo Anything u.A. ausgeschlossen.
+   `file_exclude_patterns`: Eine Liste von Glob Mustern. Passende Dateien werden aus der Sidebar, GoTo Anything u.A. ausgeschlossen.
+   `binary_file_patterns`: Eine Liste von Glob Mustern um Binärdateien anzugeben. Passende Dateien werden aus GoTo Anything und dem File Search ausgeschlossen.
+   `show_tab_close_buttons`: Falls deaktiviert, werden die Buttons zum Schließen eines Tabs nur beim Überfahren eines Tabs mit der Maus angezeigt.
+   `mouse_wheel_switches_tabs`: Falls aktiviert, kann mittels der Scrollrads der Maus zwischen den Tabs gewechselt werden wenn sich die Maus über dem Tabs Bereich befindet.
+   `ignored_packages`: Eine Liste von Packages, die ignoriert und nicht geladen werden sollen.

Alle anderen aufgeführten Optionen können sowohl in den **Global Settings** als auch in den **File Type Settings** definiert werden. Viele von ihnen bestimmen das Verhalten des Editors selbst (d.h. das Verhalten von Sublime Text bei der Textverarbeitung) und machen daher besonders in File Type Settings Sinn.



### Whitespace- und Indentation-Optionen

+   `tab_size`: Die Anzahl an Leerzeichen, die einem Tab entsprechen sollen.
+   `translate_tabs_to_spaces`: Falls aktiviert, werden beim Tippen eines Tabs durch die `Tab` Taste oder bei mittels Auto Indentation hinzugefügten Tabs <!--!--> stattdessen eine entsprechende Anzahl an Leerzeichen eingefügt.
+   `use_tab_stops`: Definiert ob beim Einfügen eines Tabs oder beim Betätigen der `Backspace` Taste statt des tatsächlichen Zeichens eine entsprechende Anzahl an Leerzeichen eingefügt/entfernt werden soll.
+   `detect_indentation`: Falls aktiviert, versucht Sublime Text beim Laden eines Buffers die Art der Indentation (Tabs oder Leerzeichen) und u.U. die Anzahl an Leerzeichen, die verwendet wird um einen Tab zu repräsentieren, zu bestimmen und überschreibt die `translate_tabs_to_spaces` und `tab_size` Optionen.  
    Falls deaktiviert, kann die automatische Bestimmung mittels des <code><em>View</em> &gt; <em>Indentation</em> &gt; <em>Guess Settings From Buffer</em></code> Menüs gestartet werden.
+   `auto_indent`: (De-)Aktiviert Auto Indentation (automatisches Einrücken).
+   `smart_indent`: Falls aktiviert, versucht Sublime Text *smater* zu agieren indem es in bestimmte Situationen, wie z.B. beim Springen in die nächste Zeile nach einem öffnenden `if`-Block (C-Style), Tabs einfügt und die Zeile angemessen einrückt.
+   `indent_to_bracket`: Gibt an ob nach einem Sprung in die nächste Zeile nach einer öffnenden Klammer, welche noch kein schließendes Gegenstück hat, Tabs eingefügt werden sollen um die nächste Zeile bis zur öffnenden Klammer einzurücken. 
+   `trim_automatic_white_space`: Gibt an ob nicht notwendige, durch Auto Indentation hinzugefügten Whitespaces entfernt werden sollen.
+   `draw_white_space`: Definiert in welchen Fällen Whitespaces gekennzeichnet werden sollen. Mögliche Werte sind: `none`, `selection` und `all`.
+   `trim_trailing_white_space_on_save`: Falls aktiviert, werden beim Speichern einer Datei alle Whitespaces am Ende einer Zeile entfernt.



### Darstellungs-Optionen

+   `color_scheme`: Das für das Syntax Highlighting verwendete Theme. Erwartet den Pfad einer `.tmTheme` Datei, relativ zum Data Verzeichnis.
+   `font_face`: Die Schriftart, welche für bearbeitbaren Text verwendet werden soll.
+   `font_size`: Die Größe der Schrift für bearbeitbaren Text.
+   `font_options`: Definiert zusätzliche Optionen für das Rendern der Schrift. Mögliche Werte sind: `bold`, `italic`, `no_antialias`, `gray_antialias`, `subpixel_antialias` und `directwrite` (Windows).
+   `gutter`: Legt fest ob der *Gutter*, die Leiste zur Linken des Textfeldes, welche unter anderem die Zeilennummern enthält, angezeigt werden soll.
+   `rulers`: Legt die horizontale Position der Lineale (*Rulers*) fest. Die angegebene Zahl bestimmt die Anzahl an Zeichen, nach denen das Lineal positioniert werden soll. Erlaubt neben einer einfachen Zahl auch eine Liste von Zahlen um mehrere Lineale zu definieren.
+   `draw_minimap_border`: Falls aktiviert, wird der aktuell sichtbare Bereich des Views in der Minimap hervorgehoben.
+   `highlight_line`: Definiert ob die Zeile, in der sich der Cursor aktuell befindet, hervorgehoben werden soll.
+   `line_padding_top`: Legt den inneren Abstand an der oberen Kante einer Zeile fest (in Pixeln).
+   `line_bottom_top`: Legt den inneren Abstand an der unteren Kante einer Zeile fest (in Pixeln).
+   `scroll_past_end`: Falls aktiviert, wird der scrollbare Bereich am Ende um einen großen Spielraum ergänzt, sodass die untere Zeile noch bis zum oberen Rand des Views gescrollt werden kann.
+   `line_numbers`: (De-)Aktiviert die Anzeige von Zeilennummern im Gutter.
+   `word_wrap`: Falls deaktiviert, werden lange Zeilen, die, die Breite des Views überschreiten, abgeschnitten und eine horizontale Scrollbar wird eingeblendet um den ausgeblendeten Teil der Zeile sichtbar zu machen. Anderenfalls werden Zeilen in die nächste Zeile umgebrochen falls sie die Breite des Views überschreiten.
+   `wrap_width`: Legt die Anzahl an Zeichen fest nach der eine Zeile umgebrochen werden soll. Bei einem Wert von `0` wird die Zeile an die Breite des Views angepasst.  
    Hat nur einen Effekt wenn `word_wrap` aktiviert ist.
+   `indent_subsequent_lines`: Falls aktiviert, werden automatisch umgebrochene Zeilen (s. `word_wrap`) entsprechend der vorherigen Zeile eingerückt.
+   `draw_centered`: Legt fest ob der Text zentriert statt linksbündig dargestellt werden soll.
+   `match_brackets`: Definiert ob Klammernpaare in der Nähe des Cursors hervorgehoben (unterstrichen) werden sollen.
+   `match_brackets_content`: Falls aktiviert, werden Klammernpaare bereits hervorgehoben wenn sich der Cursor irgendwo zwischen ihnen befindet. Anderenfalls muss der Cursor an einer Klammer grenzen.  
    Hat nur einen Effekt wenn `match_brackets` aktiviert ist.
+   `match_brackets_square`: Falls deaktiviert, werden eckige Klammern nicht hervorgehoben.  
    Hat nur einen Effekt wenn `match_brackets` aktiviert ist.
+   `match_bracktets_braces`: Falls deaktiviert, werden geschweifte Klammern nicht hervorgehoben.  
    Hat nur einen Effekt wenn `match_brackets` aktiviert ist.
+   `match_bracktets_angle`: Falls deaktiviert, werden spitze Klammern nicht hervorgehoben.  
    Hat nur einen Effekt wenn `match_brackets` aktiviert ist.



### Automatisierung

+   `auto_match_enabled`: (De-)Aktiviert das automatische Schließen einer geöffneten Klammer, eines öffnenden Anführungszeichens etc.
+   `save_on_focus_lost`: Falls aktiviert, werden Dateien beim Wechseln in eine andere Datei oder gar eine andere Anwendung automatisch gesichert.
+   `find_selected_text`: Gibt an ob beim Öffnen des *Search Panels*, der aktuell ausgewählte Text (falls vorhanden) automatisch in das Eingabefeld für den Suchterm kopiert werden soll.
+   `word_separators`: Definiert Zeichen, welche das Ende bzw. den Beginn eines Wortes kennzeichnen. Diese werden bei Operationen wie dem Bewegen des Cursors bei gedrückter `Alt` Taste verwendet. Einige andere Operationen, wie z.B. das Umbrechen einer zu langen Zeile, beachten diese Option allerdings nicht.
+   `ensure_newline_at_eof_on_save`: Legt fest ob beim Speichern einer Datei automatisch ein Zeilenumbruch am Ende des Inhalts eingefügt werden soll falls nicht bereits einer existiert.



### Anwendungs- und System-Optionen

+   `spell_check`: (De-)Aktiviert die Rechtschreibprüfung (*Spell Checker*).
+   `dictionary`: Das Wörterbuch, welches von der Rechtschreibprüfung genutzt wird.  
    Erwartet einen Pfad zu einer `.dic` Datei, relativ zum Data Verzeichnis.
+   `fallback_encoding`: Definiert das Encoding, welches genutzt werden soll wenn das Encoding eines Buffers nicht automatisch bestimmt werden kann. Automatisch bestimmbare Encodings sind: ASCII, UTF-8 und UTF-16.
+   `default_line_ending`: Gibt an welche Art von Zeilenumbrüchen verwendet werden sollen.  
    Für den Wert `windows` wird ein *Carriage Return* und ein *Line Feed* (`CRLF`) genutzt, und bei einem Wert von `unix` wird ein einfacher *Line Feed* (`LF`) verwendet. Bei einer Angabe von `system` wird der verwendete Zeilenumbruchtyp automatisch auf Basis der Plattform/des Betriebssystems bestimmt.
+   `auto_complete`: (De-)Aktiviert das automatische Anzeigen des Auto-Vervollständigungs-Popus.  
    Falls deaktiviert, kann `Ctrl + Space` oder `Alt + /` verwendet werden um das Pupup anzuzeigen und `Tab` verwendet werden um den ersten Eintrag direkt einzufügen (falls `tab_completion` aktiviert ist).
+   `tab_completion`: Falls aktiviert, wird beim Betätigen der `Tab` Taste automatisch der erste Eintrag aus der Auto-Vervollständigungs-Liste eingefügt. <!--!-->
+   `auto_complete_commit_on_tab`: Standardmäßig wird ein ausgewählter Eintrag aus der Auto-Vervollständigungs-Liste beim Drücken der `Enter` Taste angewendet. Ist diese Option aktiviert, wird stattdessen die `Tab` Taste verwendet. [Dies wird empfohlen](https://www.sublimetext.com/docs/2/auto_complete.html) und hat den Vorteil, dass so durch einfaches Drücken von `Enter` ein Zeilenumbruch eingefügt werden kann.



### Build-Systems- und Error-Optionen

+   `result_file_regex`: Ein regulärer Ausdruck, welcher genutzt wird um Informationen zu betreffenden Dateien aus einer Error Ausgabe zu extrahieren.
+   `result_line_regex`: Ein regulärer Ausdruck, welcher genutzt wird um Informationen zu den involvierten Zeilen einer Dateien aus einer Error Ausgabe zu extrahieren.
+   `result_base_dir`: Gibt ein Verzeichnis an, in dem nach den mittels `result_file_regex` extrahierten Dateien gesucht wird.
+   `build_env`: Eine Liste von Pfadangeben, welche standardmäßig in *Build Systems* verfügbar sein sollen.



### Datei- und Verzeichnis-Optionen

+   `default_dir`: Legt das Standardverzeichnis zum Abspeichern von Dateien fest.



### Eingabe-Optionen

+   `command_mode`: (De-)Aktiviert den *Command Mode* (anstelle des *Insert Mode*).  
    Falls aktiviert, werden *Key Strokes* ignoriert.
