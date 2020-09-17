# TDD Workshop

## Vorbereitungen
Aus Einfacheitsgründen verwenden wir für den Workshop eine Linuxumgebung, deshalb sind zunächst folgende Tätigkeiten durchzuführen:
* Installiert WSL 2
* Installiert eine Ubuntu VM für WSL 2
* Installiert VSCode (wenn noch nicht vorhanden)

* Öffnet eine Shell und startet die WSL vom (Befehl "wsl")
* Navigiert zu Eurem Checkout (also dieses Verzeichnis). In WSL sind die Laufwerke unter /mnt/<Laufwerksname> zu finden. D:/work wäre also /mnt/d/work.
* Öffnet VSCode in der Shell ("code ."), es wird ein VSCode mit einer Remoteverbindung zur VM geöffnet (sichtbar links unten im VSCode Fenster, dort sollte der VM Name stehen, z.B. WSL: Ubuntu-20.04)
* Installiert gcc (sudo apt install gcc)
* Installiert cmake (sudo apt install cmake)
* Kompiliert das Workshopprojekt einmal durch, um sicherzustellen, dass alles korrekt konfiguriert ist:

Also, im "build" Verzeichnis:
cmake .. -DCMAKE_BUILD_TYPE=Debug -G "Unix Makefiles" 
make all

* Prüft ob die Binaries alle da sind (unter build/sources und build/tests sollte ein Executable liegen)