## |\\| **[Startseite](README.md)** |X| **[Windows](Windows.md)** |X| **[Smartphone](Smartphone.md)** |/|  

# Linux

Da Linux ein sehr flexibles System ist, kann hier nur der aktuelle Stand wiedergegeben werden.

Verwendete und getestete Systeme: Debian 10 (Buster) und Debian 9 (Stretch) jeweils mit KDE und deutscher QWERTZ-Tastatur

---
## Der Standard

Im einfachsten Fall, sind Akut, Caron und ł über die Tastatur wie folgt erreichbar.  
* Akut ´  
Befindet sich zwischen **ß** und **Backspace** (Rückschritttaste)  
Drücke diese Taste einmal und danach z.B. das c => ć bzw. für den Großbuchstaben **Shift**+c  
* Caron ̌  
Befindet sich "versteckt" unter dem **ä**  
Drücke gleichzeitig **AltGr**+**Shift**+**ä** und danach z.B. das c => č  
Bzw. für den Großbuchstaben drücke gleichzeitig **AltGr**+**Shift**+**ä** und dann **Shift**+**c** => Č  
* ł / Ł (lstroke)  
Drücke **AltGr**+**l** => ł bzw. **AltGr**+**Shift**+l => Ł  


Da mir das mit dem Caron schreiben auf Dauer aber zu umständlich war, habe ich eine Alternative ersonnen, die auf die gleiche Art und Weise wie bei Windows funktioniert.  
Das Akut und des **ł** bleiben dabei unberührt und sind weiterhin ganz einfach über den bereits genannten (logischeren) Weg erzeugbar.  

---

Das Nachfolgende wird nun etwas technisch ;-)


### vorab ein Tipp
Verkonfiguriert?

Verwende **setxkbmap** ohne weitere Option um dein Layout wieder zurückzusetzen.  
Siehe: [How do I clear xmodmap settings?](https://askubuntu.com/a/1155211)

## Vorbereitung

Benötigt wird das Acute und das Caron (Hatschek)

Speichere erst einmal das aktuelle Layout.

**xmodmap -pk > layout.txt**




## Die Datei ".Xmodmap":

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
Die Datei muss im Home des Benutzers abgelegt werden. Sie wird dann beim Systemstart automatisch geladen.

Händisch kann die Datei über eine Konsole geladen werden:

**xmodmap .Xmodmap**



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
