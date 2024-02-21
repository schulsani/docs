---
title: Code Uploaden
layout: home
nav_order: 2
parent: Esp32
grand_parent: Setup
 
---

**Arduino ESP32 T-Display-S3 Setup Guide**

---

**Installationsanleitung für Arduino ESP32 T-Display-S3**

---

**Installation der Arduino-IDE**

1. Laden Sie die Arduino-IDE von der offiziellen Website herunter und installieren Sie sie gemäß den Anweisungen.

2. Installieren Sie Arduino ESP32 V 2.0.5 oder eine höhere Version bis V3.0.

---

**Bibliothek einrichten**

1. Laden Sie T-Display-S3 herunter und verschieben Sie sie in den Arduino-Bibliotheksordner (z. B. C:\Benutzer\IhrName\Dokumente\Arduino\libraries).

2. Kopieren Sie alle Ordner im "lib"-Ordner in den Arduino-Bibliotheksordner (z. B. C:\Benutzer\IhrName\Dokumente\Arduino\libraries).

---

**Öffnen des Codes**

1. Klonen Sie das [Code-Repository](https://github.com/schulsani/client/blob/main/Code.ino) und öffnen Sie die heruntergeladene Datei.

2. Doppelklicken Sie auf die heruntergeladene Datei "Code.ino", um sie in der Arduino-IDE zu öffnen.

---

**Arduino-IDE-Einstellungen**

Öffnen Sie die Arduino-IDE und navigieren Sie zu "Werkzeuge". Wählen Sie die Einstellungen gemäß der Tabelle unten aus:

| Einstellung                   | Wert                    |
|-------------------------------|-------------------------|
| Board                         | ESP32S3 Dev Module      |
| Port                          | Ihr Port                |
| USB CDC On Boot               | Aktivieren              |
| CPU Frequency                 | 240MHZ(WiFi)            |
| Core Debug Level              | Keine                   |
| USB DFU On Boot               | Deaktivieren            |
| Erase All Flash Before Sketch Upload | Deaktivieren      |
| Events Run On                 | Core1                   |
| Flash Mode                    | QIO 80MHZ               |
| Flash Size                    | 16MB(128Mb)             |
| Arduino Runs On               | Core1                   |
| USB Firmware MSC On Boot      | Deaktivieren            |
| Partition Scheme              | 16M Flash(3M APP/9.9MB FATFS) |
| PSRAM                         | OPI PSRAM               |
| Upload Mode                   | UART0/Hardware CDC      |
| Upload Speed                  | 921600                  |
| USB Mode                      | CDC und JTAG            |

Die fettgedruckten Optionen sind erforderlich, andere werden entsprechend den tatsächlichen Bedingungen ausgewählt.

---

**Hochladen des Codes**

1. Klicken Sie auf "Hochladen".

2. Warten Sie, bis die Kompilierung und das Schreiben abgeschlossen sind.

---

Bitte beachten Sie, dass diese Anleitung auf dem Arduino-Code basiert, der unter [diesem GitHub-Repository](https://github.com/schulsani/client/blob/main/Code.ino) verfügbar ist.