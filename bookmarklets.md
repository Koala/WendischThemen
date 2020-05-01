# Bookmarklets für die Seite http://dolnoserbski.de/dnw/ (Deutsch->Niedersorbisch) und http://dolnoserbski.de/ndw/ (Niedersorbisch->Deutsch)

Wie funktioniert das?
- Im Browser ein neues Lesezeichen so erstellen, dass es in der Lesezeichenleiste des Browsers erscheint.
- Einen Namen eingeben.
- Bei "Adresse" die komplette Zeile ab "javascript" einfügen
- Fertig

Jetzt ist folgendes damit möglich:
1. Wenn nur das Lesezeichen angeklickt wird geht ein kleines Fenster auf in dem das zu suchende Wort eingegeben werden kann.
2. Es kann ein Wort im Browser markiert werden, dann wird auf das Lesezeichen geklickt und es wird ein neuer Tab im Browser
   geöffnet und die Suche nach dem zuvor markierten Wort startet sofort.

Getestet mit Firefox Version 76.0 - 30.04.2020

## Deutsch-Niedersorbisches Wörterbuch

http://dolnoserbski.de/dnw/suche?wuraz=auto&pozicija=lema \\
**Lemma**
```
javascript:s=document.getSelection();if(!s||s==%27%27){void(s=prompt(%27Suche%20mit%20Lemma%20(Grundform).%20Suchbegriff%20auf%20Deutsch%20eingeben:%27,%27%27))};if(s){w=open(%27http://dolnoserbski.de/dnw/suche?wuraz=%27+encodeURIComponent(s)+%27&pozicija=lema%27,%27%27,%27%27);w.focus();}
```

http://dolnoserbski.de/dnw/suche?wuraz=auto&pozicija=s%C5%82owo \\
**ganzes Wort**
```
javascript:s=document.getSelection();if(!s||s==%22%22){void(s=prompt(%27Suche%20mit%20ganzes%20Wort.%20Suchbegriff%20auf%20Deutsch%20eingeben:%27,%27%27))};if(s){w=open(%27http://dolnoserbski.de/dnw/suche?wuraz=%27+encodeURIComponent(s)+%27&pozicija=s%C5%82owo%27,%27%27,%27%27);w.focus();}
```

http://dolnoserbski.de/dnw/suche?wuraz=auto&pozicija=zachopje%C5%84k
**Wortanfang**
```
javascript:s=document.getSelection();if(!s||s==%22%22){void(s=prompt(%27Suche%20mit%20Wortanfang.%20Suchbegriff%20auf%20Deutsch%20eingeben:%27,%27%27))};if(s){w=open(%27http://dolnoserbski.de/dnw/suche?wuraz=%27+encodeURIComponent(s)+%27&pozicija=zachopje%C5%84k%27,%27%27,%27%27);w.focus();}
```

http://dolnoserbski.de/dnw/suche?wuraz=auto&pozicija=srjedk
**im Wort**
```
javascript:s=document.getSelection();if(!s||s==%22%22){void(s=prompt(%27Suche%20im%20Wort.%20Suchbegriff%20auf%20Deutsch%20eingeben:%27,%27%27))};if(s){w=open(%27http://dolnoserbski.de/dnw/suche?wuraz=%27+encodeURIComponent(s)+%27&pozicija=srjedk%27,%27%27,%27%27);w.focus();}
```

http://dolnoserbski.de/dnw/suche?wuraz=auto&pozicija=k%C3%B3%C5%84cowka
**Wortende**
```
javascript:s=document.getSelection();if(!s||s==%22%22){void(s=prompt(%27Suche%20am%20Wortende.%20Suchbegriff%20auf%20Deutsch%20eingeben:%27,%27%27))};if(s){w=open(%27http://dolnoserbski.de/dnw/suche?wuraz=%27+encodeURIComponent(s)+%27&pozicija=k%C3%B3%C5%84cowka%27,%27%27,%27%27);w.focus();}
```

## Dolnoserbsko-nimske słowniki

http://dolnoserbski.de/ndw/pytanje?slownik=\*&psistup=serbski&pisanje=originalne&pozicija=slowo
**genaue Suche (alle Bücher, Niedersorbisch, Original, Suche ganzes Wort)**
```
javascript:s=document.getSelection();if(!s||s==%22%22){void(s=prompt(%27Suchbegriff%20auf%20Sorbisch%20eingeben:%27,%27%27));};if(s){w=open(%27http://dolnoserbski.de/ndw/pytanje?wuraz=%27+encodeURIComponent(s)+%27&slownik=*&psistup=serbski&pisanje=originalne&pozicija=slowo%27,%27%27,%27%27);w.focus();}
```

http://dolnoserbski.de/ndw/pytanje?slownik=\*&psistup=serbski&pisanje=originalne&pozicija=srjedk
**ungenaue Suche (alle Bücher, Niedersorbisch, Original, Suche im Wort)**
```
javascript:s=document.getSelection();if(!s||s==%22%22){void(s=prompt(%27Ungenaue%20Wortsuche.%20Suchbegriff%20auf%20Sorbisch%20eingeben:%27,%27%27));};if(s){w=open(%27http://dolnoserbski.de/ndw/pytanje?wuraz=%27+encodeURIComponent(s)+%27&slownik=*&psistup=serbski&pisanje=originalne&pozicija=srjedk%27,%27%27,%27%27);w.focus();}
```
