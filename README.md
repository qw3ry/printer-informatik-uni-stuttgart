# Druckskript
für die Drucker an der Informatik-Fakultät der Universität Stuttgart

### Anleitung zum Aufsetzen für CUPS
1. installiere [cups-pdf](http://freecode.com/projects/cupspdf) für deine Distribution (unter Arch: `sudo pacman -S cups-pdf`)
2. kopiere (oder symlinke) `print-uni` nach `/etc/cups/scripts`
2. in der Konfiguration für cups-pdf (unter Arch: `/etc/cups/cups-pdf.conf`) setze `PostProcessing /etc/cups/scripts/print-uni`
3. Starte `cups` neu. Ab jetzt wird das Skript nach dem Drucken mit dem PDF-Drucker ausgeführt.
4. Passe das Skript an deine Bedürfnisse an

### Customizing
* Verändere das Skript, so dass es deinem Setup gerecht wird (Username 
anpassen, Pfade ändern, ...)
* Um auf beiden Druckern drucken zu können, editiere `etc/cups/printers.conf` und ändere die `DeviceURI` von `cups-pdf:/` auf `cups-pdf:/zarquon` bzw. `cups-pdf:/duesentrieb`. Das Skript druckt jetzt auf dem entsprechenden Drucker.
* Um `cups-pdf` auch verwenden zu können, ohne auf den Poolrechner zu drucken, ändere das Skript, sodass es abbricht, falls die DeviceURI nicht `zarquon` oder `duesentrieb` enthält.

### Troubleshooting
* Verwende SSH-Keys, statt dich mit Passwort zu identifizieren. Dies 
funktioniert in einem nicht-interaktiven Skript natürlich nicht.
* Erstelle das Verzeichnis ~/print-jobs auf deinem Pool-Account
* Führe das Skript testweise manuell aus
* Der Log des Skripts steht in /var/spool/cups-pdf/$USERNAME/print-log
