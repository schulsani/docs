---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: Raspberry
id: 5HR-CTPH-DZU-0HK
slug: raspberry
isVisible: true
lastUpdated: '2024-02-20 05:46:24'
---
<div><p># Einrichtung eines Raspberry Pi mit schulsani.local als IP-Adresse</p></div>

<div><p><br></p></div>

<div><p>## Voraussetzungen:</p></div>

<div><p>- Raspberry Pi (beliebiges Modell)</p></div>

<div><p>- MicroSD-Karte (mindestens 8 GB)</p></div>

<div><p>- Computer mit SD-Kartenleser</p></div>

<div><p>- Netzwerkverbindung</p></div>

<div><p><br></p></div>

<div><p>## Schritte:</p></div>

<div><p><br></p></div>

<div><p>1. **Raspberry Pi OS herunterladen und auf die MicroSD-Karte flashen:**</p></div>

<div><p>- Laden Sie das neueste Raspberry Pi OS von der offiziellen Website herunter.</p></div>

<div><p>- Verwenden Sie ein Tool wie Etcher, um das Betriebssystem auf die MicroSD-Karte zu flashen.</p></div>

<div><p><br></p></div>

<div><p>2. **Konfiguration der Datei "wpa_supplicant.conf":**</p></div>

<div><p>- Erstellen Sie eine Datei namens "wpa_supplicant.conf" auf der bootfähigen Partition der MicroSD-Karte.</p></div>

<div><p>- Fügen Sie die folgenden Zeilen hinzu und ersetzen Sie "YOUR_SSID" und "YOUR_PASSWORD" durch den Namen Ihres WLANs und Ihr WLAN-Passwort:</p></div>

<div><p><br></p></div>

<div><p>```plaintext</p></div>

<div><p>country=DE</p></div>

<div><p>ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev</p></div>

<div><p>update_config=1</p></div>

<div><p><br></p></div>

<div><p>network={</p></div>

<div><p>ssid="YOUR_SSID"</p></div>

<div><p>psk="YOUR_PASSWORD"</p></div>

<div><p>key_mgmt=WPA-PSK</p></div>

<div><p>}</p></div>

<div><p>```</p></div>

<div><p><br></p></div>

<div><p>3. **Statische IP-Adresse konfigurieren:**</p></div>

<div><p>- Erstellen Sie eine neue Datei mit dem Namen "schulsani.local" unter dem Verzeichnis "/etc/dhcpcd.conf" auf dem Raspberry Pi.</p></div>

<div><p>- Fügen Sie folgende Zeilen hinzu, um die statische IP-Adresse festzulegen:</p></div>

<div><p><br></p></div>

<div><p>```plaintext</p></div>

<div><p>interface wlan0</p></div>

<div><p>static ip_address=192.168.1.100/24</p></div>

<div><p>static routers=192.168.1.1</p></div>

<div><p>static domain_name_servers=192.168.1.1</p></div>

<div><p>```</p></div>

<div><p><br></p></div>

<div><p>4. **Raspberry Pi starten:**</p></div>

<div><p>- Legen Sie die MicroSD-Karte in den Raspberry Pi ein und starten Sie ihn.</p></div>

<div><p>- Warten Sie, bis der Raspberry Pi hochgefahren ist und eine Verbindung zum WLAN hergestellt hat.</p></div>

<div><p><br></p></div>

<div><p>5. **Testen der Verbindung:**</p></div>

<div><p>- Öffnen Sie einen Webbrowser und geben Sie "schulsani.local" in die Adressleiste ein.</p></div>

<div><p>- Sie sollten nun auf die Weboberfläche des Raspberry Pi zugreifen können.</p></div>

<div><p><br></p></div>

<div><p>Durch diese Schritte sollte Ihr Raspberry Pi erfolgreich mit der IP-Adresse "schulsani.local" eingerichtet sein.</p></div>

<br />