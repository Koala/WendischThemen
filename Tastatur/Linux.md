## |\\| **[Startseite](README.md)** |X| **[Windows](Windows.md)** |X| **[Smartphone](Smartphone.md)** |/|  

# Linux

Da Linux ein sehr flexibles System ist, kann hier nur der aktuelle Stand wiedergegeben werden.

Verwendete und getestete Systeme:  
Debian 10 (Buster) und Debian 9 (Stretch) jeweils mit KDE und deutscher QWERTZ-Tastatur  

---
## Der Standard

Im einfachsten Fall, sind Akut, Caron und ł über die Tastatur wie folgt erreichbar.  
* [Akut](https://de.wikipedia.org/wiki/Akut)  
Befindet sich zwischen **ß** und **Backspace** (Rückschritttaste)  
Drücke diese Taste einmal und danach z.B. das c => ć bzw. für den Großbuchstaben **Shift**+**c** => Ć  
* [Caron](https://de.wikipedia.org/wiki/Hatschek)  
Befindet sich "versteckt" unter dem **ä**  
Drücke gleichzeitig **AltGr**+**Shift**+**ä** und danach z.B. das c => č  
Bzw. für den Großbuchstaben drücke gleichzeitig **AltGr**+**Shift**+**ä** und dann **Shift**+**c** => Č  
* ł / Ł (lstroke)  
Drücke **AltGr**+**l** => ł bzw. **AltGr**+**Shift**+**l** => Ł  


Da mir das mit dem Caron schreiben auf Dauer aber zu umständlich war, habe ich eine Alternative ersonnen, die auf die gleiche Art und Weise wie bei Windows funktioniert.  
Das Akut und des **ł** bleiben dabei unberührt und sind weiterhin ganz einfach über den bereits genannten (logischeren) Weg erzeugbar.  

---

Das Nachfolgende wird nun etwas technisch ;-)


### vorab ein Tipp
Verkonfiguriert?

Verwende **setxkbmap** ohne weitere Option um dein Layout wieder zurückzusetzen.  
Siehe: [How do I clear xmodmap settings?](https://askubuntu.com/a/1155211)

## Vorbereitung

Das Caron wird im folgenden auf die Taste links neben der 1 gelegt.  
Bevor es richtig los geht, wird das aktuelle Tastaturlayout in einer Datei gespeichert.  
Dies geschieht mit:  

**xmodmap -pk > layout.txt**

Nun sieh nach, ob die benötigte Taste wie in meinem Beispiel, den KeyCode 49 hat.
Du kannst in der Datei layout.txt danach suchen oder einfach diesen Befehl ausführen:  

**xmodmap -pk | grep dead_circumflex**

Die Ausgabe könnte dann so aussehen:  

    48         0x00e4 (adiaeresis)     0x00c4 (Adiaeresis)     0x00e4 (adiaeresis)     0x00c4 (Adiaeresis)     0xfe52 (dead_circumflex)  0xfe5a (dead_caron)     0xfe52 (dead_circumflex)        0xfe5a (dead_caron)
    49         0xfe52 (dead_circumflex)        0x00b0 (degree) 0xfe52 (dead_circumflex)        0x00b0 (degree) 0x1002032 (U2032) 0x1002033 (U2033)       0x1002032 (U2032)

KeyCode 49 enthält hier das **^** (dead_circumflex) und das **°** (degree) Zeichen.  
Sollte bei dir eine andere Nummer für diese beiden Zeichen erscheinen, dann verwende im weiteren Verlauf diese Nummer.  
Als nächstes muss die Datei **.Xmodmap** erstellt werden. Es ist auf die Schreibweise, am Anfang der Punkt und ein großes X, zu achten.  


## Die Datei ".Xmodmap"

```
! Reload this file with:
! xmodmap .Xmodmap
!
! aus dead_circumflex wird dead_caron
! 1 - normale Taste ˇ
! 2 - Shift °
! 3 - AltGr ^
! 4 - AltGr+Shift ′
keycode 49 = dead_caron degree dead_circumflex dead_caron dead_circumflex U2032

! Originalbelegung:
! keycode  49 = dead_circumflex degree dead_circumflex degree U2032 U2033 U2032
```
Nicht verwirren lassen, von der mehrfachen Nennung des dead_caron in der Datei. Das muss so sein :-D  
Die Datei muss im Home-Verzeichnis des Benutzers abgelegt werden. Sie wird dann beim Systemstart automatisch geladen.

Händisch kann die Datei mit dem Befehl **xmodmap** über eine Konsole geladen werden. Die Änderungen werden sofort ausgeführt.  

**xmodmap .Xmodmap**

Sollte etwas nicht stimmen, kann nachgesehen werden, ob das dead_caron richtig übernommen wurde.  

**xmodmap -pk | grep dead_caron**

Bei mir sieht das jetzt so aus:

    48         0x00e4 (adiaeresis)     0x00c4 (Adiaeresis)     0x00e4 (adiaeresis)     0x00c4 (Adiaeresis)     0xfe52 (dead_circumflex)  0xfe5a (dead_caron)     0xfe52 (dead_circumflex)        0xfe5a (dead_caron)
    49         0xfe5a (dead_caron)     0x00b0 (degree) 0xfe52 (dead_circumflex)        0xfe5a (dead_caron)     0xfe52 (dead_circumflex)  0x1002032 (U2032)

Das Caron erscheint nun nach einmaligem Druck auf die Taste. Das Grad-Zeichen mittels der Shift-Taste und das Circumfelx ist auch noch auf der Taste. Jetzt allerdings erreichbar mit **AltGr**+die Taste.

Auf diese Art und Weise kann auch eine beliebig andere Taste verändert werden. Je nach Arbeitsweise.  
Linux ist da sehr, sehr flexibel ;-D  
Und solltest du dich mal vertan haben, führe einfach ein [Reset](#vorab-ein-Tipp) aus.

## Hinweis - falls "zoom" unter Debian Stretch installiert ist

zoom benötigt das Paket **ibus**. Dieses wird automatisch mit installiert.  
Bei Debian Stretch wird aber **ibus** nicht automatisch mit gestartet.  
Bei Debian Buster sind die notwendigen Dateien für den automatische Start vorhanden.  

Der automatische Start kann wie folgt erstellt werden.  
Diese Einstellung muss in jedem Benutzerverzeichnis einzeln erfolgen.  

```
cd ~/.config/autostart-scripts/
touch ibus.sh
chmod 744 ibus.sh
```

Schreibe in die **ibus.sh**
```
#!/usr/bin/env bash
exec ibus-daemon -drx
```

```
cd ~
touch .xprofile
```

Schreibe in die **.xprofile**
```
export GTK_IM_MODULE=ibus
export XMODIFIERS=@im=ibus
export QT_IM_MODULE=ibus
```

Quelle: https://forum.manjaro.org/t/solved-kde-and-ibus/87662/10




.
