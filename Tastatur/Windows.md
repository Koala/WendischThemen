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
