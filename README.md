# Druckskript
für die Drucker an der Informatik-Fakultät der Universität Stuttgart

### Anleitung zum aufsetzen für CUPS
1. installiere [cups-pdf](http://freecode.com/projects/cupspdf) für deine Distribution (unter Arch: `sudo pacman -S cups-pdf`)
2. in der Konfiguration für cups-pdf (unter Arch: `/etc/cups/cups-pdf.conf`) setze `PostProcessing /etc/cups/scripts/print-uni`
3. Starte `cups` neu. Ab jetzt wird das Skript nach dem Drucken mit dem PDF-Drucker ausgeführt.

### Customizing
* Um auf beiden Druckern drucken zu können, editiere `etc/cups/printers.conf` und ändere die `DeviceURI` von `cups-pdf:/` auf `cups-pdf:/zarquon` bzw. `cups-pdf:/duesentrieb`. Das Skript druckt jetzt auf dem entsprechenden Drucker.
* Um `cups-pdf` auch verwenden zu können, ohne auf den Poolrechner zu drucken, ändere das Skript, sodass es abbricht, falls die DeviceURI nicht `zarquon` oder `duesentrieb` enthält.

### Troubleshooting
* Verwende SSH-Keys, statt dich mit Passwort zu identifizieren.
* Führe das Skript manuell aus
* Der Log des Skripts steht in /var/spool/cups-pdf/$USERNAME/print-log
