---
title: Node Red
layout: home
parent: Setup
---
# Einrichtung eines Raspberry Pi mit schulsani.local als IP-Adresse

## Voraussetzungen:

- Raspberry Pi (beliebiges Modell)

- MicroSD-Karte (mindestens 8 GB)

- Computer mit SD-Kartenleser

- Netzwerkverbindung

## Schritte:

1. **Raspberry Pi OS herunterladen und auf die MicroSD-Karte flashen:**

- Laden Sie das neueste Raspberry Pi OS von der offiziellen Website herunter.

- Verwenden Sie ein Tool wie Etcher, um das Betriebssystem auf die MicroSD-Karte zu flashen.

2. **Konfiguration der Datei "wpa_supplicant.conf":**

- Erstellen Sie eine Datei namens "wpa_supplicant.conf" auf der bootfähigen Partition der MicroSD-Karte.

- Fügen Sie die folgenden Zeilen hinzu und ersetzen Sie "YOUR_SSID" und "YOUR_PASSWORD" durch den Namen Ihres WLANs und Ihr WLAN-Passwort:

```plaintext

country=DE

ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev

update_config=1

network={

ssid="YOUR_SSID"

psk="YOUR_PASSWORD"

key_mgmt=WPA-PSK

}

```

3. **Statische IP-Adresse konfigurieren:**

- Erstellen Sie eine neue Datei mit dem Namen "schulsani.local" unter dem Verzeichnis "/etc/dhcpcd.conf" auf dem Raspberry Pi.

- Fügen Sie folgende Zeilen hinzu, um die statische IP-Adresse festzulegen:

```plaintext

interface wlan0

static ip_address=192.168.1.100/24

static routers=192.168.1.1

static domain_name_servers=192.168.1.1

```

4. **Raspberry Pi starten:**

- Legen Sie die MicroSD-Karte in den Raspberry Pi ein und starten Sie ihn.

- Warten Sie, bis der Raspberry Pi hochgefahren ist und eine Verbindung zum WLAN hergestellt hat.

5. **Testen der Verbindung:**

- Öffnen Sie einen Webbrowser und geben Sie "schulsani.local" in die Adressleiste ein.

- Sie sollten nun auf die Weboberfläche des Raspberry Pi zugreifen können.

Durch diese Schritte sollte Ihr Raspberry Pi erfolgreich mit der IP-Adresse "schulsani.local" eingerichtet sein.

