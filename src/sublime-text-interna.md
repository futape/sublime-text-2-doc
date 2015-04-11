Sublime Text Interna
==================

1.  [Das Data Verzeichnis](#das-data-verzeichnis)
2.  [Packages](#packages)
3.  [Sublime-Text-spezifische Dateien](#sublime-text-spezifische-dateien)





Das *Data* Verzeichnis
--------------------

Beinahe alle für Sublime Text relevanten Daten werden im sogenannten *Data* Verzeichnis abgelegt. Dies ist je nach Plattform ein anderes.

+   **Windows**: `%APPDATA%\Sublime Text 2`
+   **OS X**: `~/Library/Application Support/Sublime Text 2`
+   **Linux**: `~/.config/sublime-text-2`

Für portable Installationen, ist das *Data* Verzeichnis ein Unterverzeichnis des Verzeichnisses, in das Sublime Text extrahiert wurde, namens `Data`.

Ein wichtiges Unterverzeichnis des Data Verzeichnisses ist das ***Packages* Verzeichnis**, welches nahezu sämtliche Erweiterungen und Einstellungen für Sublime Text enthält und den Namen `Packages` trägt. Dieses Verzeichnis kann über das Menü <code><em>Preferences</em> &gt; <em>Browse Packages...</em></code> geöffnet werden.





Packages
--------

Packages sind Erweiterungen für Sublime Text und enthalten Dinge wie Snippets, Macros, Keymaps, Plugins, Einstellung etc.  
Sie existieren in zwei Formen:

+   Als Unterverzeichnis des Packages Verzeichnisses (im Folgenden als *Package Verzeichnis* bezeichnet), oder
+   als `.sublime-package` Datei in einem Unterverzeichnis des Data Verzeichnisses namens `Installed Packages`.

Ein besonderes Package Verzeichnis ist das ***User* Verzeichnis**.  
Dies trägt den Namen `User` und ist dazu gedacht, nutzerdefinierte Erweiterungen und Einstellungen zu beherbergen. Es unterscheidet sich von allen anderen Package Verzeichnissen dadurch, dass es bei Updates von Sublime Text nicht verändert wird.

Eine Besonderheit an ***Installed Packages*** (`.sublime-package` Dateien) ist, dass sie wiederhergestellt werden können wenn das Packages Verzeichnis einmal gelöscht werden sollte. Für jedes solcher Packages erstellt Sublime Text ein neues Package Verzeichnis mit dessen Inhalt.





Sublime-Text-spezifische Dateien
-----------------------------

+   `.sublime-settings`: [Einstellungen](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/customization/settings.html) (JSON)
+   `.sublime-build`: [*Build Systems*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/file_processing/build_systems.html) (JSON)
+   `.sublime-project`: [Projekte](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/file_management/file_management.html#projects) (Definition; JSON)
+   `.sublime-workspace`: Tritt im Zusammenhang mit `.sublime-project` Dateien auf und enthält Daten, die den aktuellen Zustand des geöffneten Projekts, wie geöffnete Dateien oder Änderungen an diesen, beschreiben. Diese Dateien bedürfen i.d.R. keiner manuellen Änderungen und würden, anders als `.sublime-project` Dateien, niemals zu einer Versionskontrolle hinzugefügt werden.
+   `.sublime-keymap`: [*Key Bindings*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/customization/key_bindings.html) (JSON)
+   `.sublime-macro`: [*Macros*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/extensibility/macros.html) (JSON)
+   `.sublime-snippet`: [*Snippets*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/extensibility/snippets.html) (XML)
+   `.sublime-completions`: [*Completions*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/extensibility/completions.html) (JSON)
+   `.sublime-commands`: [*Commands*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/extensibility/command_palette.html) (*Commands Palette*; JSON)
+   `.sublime-menu`: Menüs
+   `.sublime-theme`: Themes (UI/Anwendung)
+   `.sublime-package`: [*Sublime Text Package Archives*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/extensibility/packages.html) (Zip)
+   `.py`: [Plugins](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/extensibility/plugins.html) (Python)
+   `.tmLanguage`: [*Syntax Definitions*](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/extensibility/syntaxdefs.html) (XML/Plist)
+   `.tmPreferences`: *Syntax Preferences*
+   `.tmTheme`: Themes (*Syntax Highlighting*)
+   `.dic`: Ein Wörterbuch (*Dictionary*), genutzt von der Rechtschreibprüfung
