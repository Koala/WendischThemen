#Herausvorderungen beim Schreiben von Sonderzeichen

Das Nachfolgende wird etwas technisch ;-)

##System: Linux

Das Schreiben der Sonderzeichen (ě, č, ŕ, ń usw.) kann machnchmal sehr mühsam sein.

Da Linux ein sehr flexibles System ist, kann hier nur der aktuelle Stand wiedergegeben werden.
Verwendetes System: Debian 10



xmodmap -pk

##Tipp
Verkonfiguriert?

Verwende "setxkbmap" ohne weitere Option um dein Layout wieder zurückzusetzen.
Siehe: https://askubuntu.com/a/1155211 (How do I clear xmodmap settings?)

##Die Datei "".Xmodmap":

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

.
