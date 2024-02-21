---
title: Benutzung 
layout: home
nav_order: 
---
## Benutzung
Um das System zu benutzen muss man einfach nur schulsani.local öffnen und dort das Passwort eingeben *(Standardpasswort: Geheim)*
## Login
![enter image description here](https://i.postimg.cc/3NMBg3Kd/Video-Capture-20240216-075345.jpg)
## Formular
Nun kann Raum und Unfall angeben werden


![enter image description here](https://i.postimg.cc/KjZbvSdg/Video-Capture-20240216-075802.jpg)

## Bestätigung
Nun wird angezeigt das der Unfall abgesendet wurde und auch wenn er bestätigt wurde
![enter image description here](https://i.postimg.cc/xCGY2TF2/Video-Capture-20240216-075807.jpg)
## Passwort ändern
Um das Passwort zu ändern öffne die cmd und gebe 

    sudo nano /var/www/HTML/form.php
ein nun kannst du in der unten gezeigten Zeile das  Passwort ändern

    
    if ($_POST['pw'] == "Geheim") {
    } else {        echo '<p>Passwort ist falsch. Sie werden in 2 Sekunden zur&uuml;ck geleitet.</p>';        header("Refresh: 2; url=index.html");        exit();    }
