## |\\| **[Startseite](README.md)** |X| **[Windows](Windows.md)** |X| **[Smartphone](Smartphone.md)** |/|  

# Linux

Das Nachfolgende wird etwas technisch ;-)

Da Linux ein sehr flexibles System ist, kann hier nur der aktuelle Stand wiedergegeben werden.

Verwendete und getestete Systeme: Debian 10 (Buster) und Debian 9 (Stretch) jeweils mit KDE


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
