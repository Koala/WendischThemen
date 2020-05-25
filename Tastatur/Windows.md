## |\\| **[Startseite](README.md)** |X| **[Smartphone](Smartphone.md)** |X| **[Linux](Linux.md)** |/|  

# Windows

## Windows 10

Externer Link!  
Der Inhalt bezieht sich auf Obersorbisch. Die Verfahrensweise gilt aber ebenso für Niedersorbisch.  
[Sorbische Tastatur für Windows 10](https://domizna.org/index.php?id=3187)


## Windows 7

Sollte nicht mehr verwendet werden. Aber wer es noch einsetzt ...

Externer Link!  
Der Inhalt bezieht sich auf Obersorbisch. Die Verfahrensweise gilt aber ebenso für Niedersorbisch.  
[Sorbische Tastatur für Windows 7](https://domizna.org/index.php?id=2046)

---

## Windows 10 - alternative Möglichkeit

Getestet mit Windows 10 - Version 1909  

Mit Hilfe des Programmes [Microsoft Keyboard Layout Creator 1.4](https://www.microsoft.com/en-us/download/details.aspx?id=22339) (kurz: **MKLC**) ist es möglich, ein Tastaturlayout an seine eigenen Bedürfnisse anzupassen.  

An diesem Beispiel möchte ich zeigen, wie die Tastatur so angepasst werden kann, dass die Buchstaben **ł** und **Ł** über die Taste **l** bzw. **L** erreichbar sind und die Taste **#** ihre Funktion behält. Das **ł** bei der Taste **l** zu finden empfinde ich einfach viel intuitiver und es passt besser zum Layout unter [Linux](Linux.md).  

### Vorab:
Das fertige Layout befindet sich hier: [Layout_SorbischAngepasst](files/Layout_SorbischAngepasst.7z).  
Die Quelldatei, zum Import in den MKLC befindet sich hier: [Layout_SorbischAngepasst_Source](files/Layout_SorbischAngepasst_Source.klc).  

### Los gehts
Das Programm [Microsoft Keyboard Layout Creator 1.4](https://www.microsoft.com/en-us/download/details.aspx?id=22339) downloaden:  

![MKLC Internet](assets/201_MKLC.png)  

und starten:  

![MKLC gestartet](assets/202_MKLC.png)  

Es kann sein, dass es noch eine Warnung wegen fehlendem **.NET Framework Version 2.0.50727** gibt:  

![Warnung zu fehlendem .NET](assets/203_WarungDotNet.png)  

Wie du das beheben kannst, findet du hier (weiter unten): [.NET Framework nachinstallieren](#.NET_Framework_nachinstallieren)  

Den Installationprozess in 3 Schritten durchgehen:  

![Schritt 1](assets/204_Install_Step_1.png) ![Schritt 2](assets/205_Install_Step_2.png) ![Schritt 3](assets/206_Install_Step_3.png)

Dann das Programm starten:  

![Windows Menü](assets/207_Programm_Start.png) ![Windows Menü](assets/208_Programm_Gestartet.png)

Als erstes muss das benötigte Tastaturlayout geladen werden (Sorbisch erweitert):  

![Menü File](assets/209_LoadExistingKeyboard.png) ![Layout Auswahl](assets/210_LoadExistingKeyboard_SorbischErweitert.png)

Klicke das **l** an und klicke dann auf **All**:  

![Menü File](assets/211_L.png) ![Menü File](assets/212_L_All.png)

Im folgenden Fenster trage im unteren Bereich bei **ctrl+alt+\<Key>** ein **U+0142** ein und
bei **Shift+ctrl+alt+\<Key>** ein **U+0141**. Angezeigte Zeichen rechts sind dann **ł** und **Ł**.    

![142+141](assets/214_L_142+141.png)

So, jetzt noch den Tasten **#** und **'** wieder zu ihren Ausgaben verhelfen.
Das gleiche Vorgehen wie zuvor.  

![Raute-Taste](assets/215_Altes_L.png)

Taste anklicken, dann auf **All** und im Fenster dann die Änderungen vornehmen.  
Bei **\<Key>** trage ein **U+0023**, bei **shift+\<Key>** trage ein **U+0027**:  

![0023+0027](assets/217_Altes_L_Neue_Einstellungen.png)

Nun können die neuen Einstellungen getestet werden. Dazu im Menü **Project/Test Keyboard Layout...** auswählen.  

![Menü Layouttest](assets/218_Layout_Test.png)

Im darauf folgenden Fenster kann munter drauf losgeschrieben werden:  

![Layouttest](assets/219_Layout_Test.png)

Wenn alles gut war, müssen noch ein paar Einstellungen vorgenommen werden.
Öffne die Einstellungen im Menü unter **Project/Properties...***:  

![Menü Properties](assets/220_Einstellungen.png)

Hier kann nun ein Projekt-Name vergeben werden. Unter **Description** steht die Bezeichnung, mit der später die Tastatur in den Windowseinstellungen gefunden werden kann. **Company** und **Copyright** kann nach belieben befüllt oder leer gelassen werden.  
**WICHTIG** ist die Einstellung bei **Language**. Hier muss von **Upper Sorbian (Germany)** auf **Lower Sorbian (Germany)** umgestellt werden. Rechts steht dann **DS**.

![Language](assets/222_Sprache_LowerSorbian.png)

Wenn das alles fertig ist, dann geht es jetzt an die Erstellung der DLL.  
Starte mit dem Menü **Project/Build DLL and Setup Package** den Build Prozess:  

![Language](assets/223_BuildDLL.png)

Danach erscheint eine Meldung die uns fragt, ob wir uns das Log ansehen wollen. Wollen wir aber nicht.  

![Warnung](assets/224_Warnung.png)

Nach dem das Layout generiert wurde, kann die nächste Frage dann mit "Ja" beantwortet werden.  

![Layout Generiert](assets/225_LayoutGeneriert.png)

Im sich öffnenden Verzeichnis das Setup zur Installation starten und fertig wäre der erste Teil.  

![Installation komplett](assets/226_InstallationComplete.png)

Jetzt noch ein paar Einstellungen zur Sprache in den Windows eigenen Einstellungen. Öffne die Windowseinstellungen und gibt in das Suchfeld **sprache** ein; wähle dann **Sprache und Tastaturoptionen ändern** aus.   

![Systemeinstellungen](assets/227_Systemeinstellungen.png)

Im unteren Bereich sollte **Dolnoserbšćina** zur Auswahl stehen. Das einmal anklicken und mit einmal Klick auf den Pfeil nach (ganz) oben verschieben.  

![Dolnoserbšćina](assets/228_Dolnoserb.png) ![nach oben](assets/229_Dolnoserb_NachOben.png)

Als nächstes **Optionen** anklicken. Hier sollte unter **Tastaturen** unsere neue Tastatur zu sehen sein. In meinem Fall ist es **Sorbisch erweitert - Custom**    

![Optionen](assets/230_Dolnoserb_Optionen.png) ![Tastatur](assets/231_Dolnoserb_Tastatur.png)

... und rechts untem im Systemtray erscheint nun der Sprachumschalter mit vorausgeähltem **DSB**.  

![Sprachwahl](assets/232_SprachwahlSichtbar.png)


# # # # # # # # # # # # #   
#### # # # # E N D E # # # #  
# # # # # # # # # # # # #  


---
### .NET Framework nachinstallieren

[Anleitung auf Englisch](https://answers.microsoft.com/en-us/windows/forum/windows_10-hardware/microsoft-keyboard-layout-creator-14-instalation/092881f1-470b-4a66-889f-59e868c6b25a?auth=1)

- drücke die Taste **Windows Logo**+**R**
- gib **appwiz.cpl** ein und drücke **Enter**:  

![appwiz.cpl](assets/100_appwiz.cpl.png)  
- im erscheinenden Fenster klicke links den Link **Windows-Feature aktivieren oder deaktivieren** an:  

![Windows-Features](assets/101_WindowsFeatures.png)  
- markiere das Kästchen neben **.NET Framework 3.5**:  

![.NET Framework 3.5](assets/102_NETFramework35.png)  

- mit OK bestätigen und Windows die notwendigen Dateien automatisch herunterladen lassen:  

![Dateien herunterladen](assets/103_DateienHerunterladen.png)

- danach kann das Programm erneut gestartet werden  
