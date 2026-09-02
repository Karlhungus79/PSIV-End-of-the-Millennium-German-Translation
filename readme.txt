================================================================================

  PHANTASY STAR IV: THE END OF THE MILLENNIUM
  German Translation / Deutsche Übersetzung

  Version 1.1
  Release Date: 02.09.2026

  Author: Karlhungus
  Platform: Sega Mega Drive / Genesis

================================================================================


--------------------------------------------------------------------------------
  1. ABOUT THIS PATCH  (English)
--------------------------------------------------------------------------------

This patch translates Phantasy Star IV: The End of the Millennium for the
Sega Mega Drive / Genesis into German. It is an unofficial fan project and
is not affiliated with or endorsed by SEGA.

  Dialogue ............ translated
  Menus / System text . translated
  Item names .......... NOT translated - left in the original English
  Proper names ........ NOT translated - characters, places, techniques
                        and enemies keep their original English names

This was a deliberate decision. Item and proper names are deeply embedded
in the series' identity and are widely recognised by fans in their English
form. Keeping them intact also avoids space and pointer problems in the
menu system.

  NEW IN VERSION 1.1: PROPER GERMAN UMLAUTS

Version 1.0 had to transcribe umlauts the old-fashioned way - ae, oe, ue
and ss - because the game's fonts simply did not contain the characters.
Version 1.1 fixes this at the root: both of the game's fonts have been
extended by seven new glyphs (ä, ö, ü, Ä, Ö, Ü and ß) and the entire
script has been rewritten to correct German orthography. "Schluessel" is
now "Schlüssel", "grosse" is now "große".

The title screen was redrawn as well: it now reads "STARTTASTE DRÜCKEN"
instead of "PRESS START BUTTON".

A full proofreading pass over all 12.018 text strings came with it; see
section 10 for the complete list of corrections.

This is the author's second ROM hacking project, following a German
translation of Phantasy Star III. It was produced solo, with the AI
assistant Claude (Anthropic) used both for the translation itself and as
technical support for script extraction, text alignment and parts of the
assembly work. Every single text string was proofread and approved by the
author before release.

Rather than relying on spot checks, the finished translation was then
verified a second time through a complete recorded playthrough of the
German version on the author's YouTube channel, so every line has also
been seen and checked in its actual in-game context.

  https://www.youtube.com/@rgbretrogaming


--------------------------------------------------------------------------------
  2. REQUIRED ROM
--------------------------------------------------------------------------------

  Game:          Phantasy Star IV - The End of the Millennium (USA)
  Region code:   4  (USA)
  Serial:        GM MK-1307 -00
  Copyright:     (C)SEGA 1994.NOV
  Size:          3.145.728 bytes  (3 MB / 24 Mbit)
  Header:        none - plain headerless .bin / .md dump

  CRC32:         FE236442
  MD5:           84cbd0ff47f3c8e9d21d2c2fc39185fa
  SHA-1:         bc7ff6d6a8408f38562bc610f24645cad6c42629

The patch applies to this exact ROM only. If your file has a different
size or checksum, the patching tool will refuse it.

No ROM is included with this patch and none will be provided. You must
supply your own copy of the game.


--------------------------------------------------------------------------------
  3. HOW TO PATCH
--------------------------------------------------------------------------------

  Patch format:  BPS
  Patch file:    PS4_German_v1.1.bps

  Recommended tool: Floating IPS (Flips)
                    https://www.romhacking.net/utilities/1040/

  Steps:
    1. Open Flips and choose "Apply Patch".
    2. Select PS4_German_v1.1.bps from this archive.
    3. Select your unmodified Phantasy Star IV ROM.
    4. Save the result under a new file name.
       Never overwrite your original ROM.

  Alternatively, use the Online ROM Patcher on ROMhacking.net.

  BPS patches store a checksum of the source ROM. If the tool reports a
  mismatch, your ROM is not the expected version - see section 2.


--------------------------------------------------------------------------------
  4. VERIFYING THE RESULT
--------------------------------------------------------------------------------

  After patching, the file should match these values:

  Size:          3.145.728 bytes
  CRC32:         8776A69F
  MD5:           d5d42e572444dcbde2b670097b92fe54
  SHA-1:         28ec40cb6953d9d4dc1ac36e59981b7e390fd9e1

  Note that the patched ROM is now exactly the same size as the original,
  3.145.728 bytes. Version 1.0 still had to expand the ROM by 51.732 bytes
  because the German script needed more room than the English one. Real
  umlauts made the text short enough (every "ae" became a single "ä") that
  the expansion is no longer necessary. The ROM end address in the header
  is back to the stock value (0x002FFFFF).

  The internal Mega Drive checksum has been recalculated and is valid
  (E3EA), so the patched ROM passes the console's own integrity check.

  The SRAM configuration is unchanged (8 KB at 0x200001-0x203FFF), so
  battery saves work exactly as in the original game. Save files from the
  unpatched version and from version 1.0 remain compatible.


--------------------------------------------------------------------------------
  5. TESTED ON
--------------------------------------------------------------------------------

  Emulator:      ares

  This release was tested in the ares emulator only. Because the ROM is a
  plain 3 MB image again, the padding advice from the version 1.0 readme
  no longer applies - flash carts should accept the file as is, but this
  has not been verified on real hardware for this release.


--------------------------------------------------------------------------------
  6. KNOWN ISSUES
--------------------------------------------------------------------------------

  No issues are known at the time of release.

  Please report text bugs with a savestate or a description of where the
  passage appears. See section 9 for contact details.


--------------------------------------------------------------------------------
  7. CREDITS
--------------------------------------------------------------------------------

  Translation, hacking, testing ......... Karlhungus
  Quality assurance ..................... full recorded playthrough,
                                          see section 1
  Tools ................................. Floating IPS (Flips),
                                          AS macro assembler,
                                          custom script tooling

  The original SEGA staff credits are preserved in full. No developer
  has been removed from or replaced in the in-game credit roll.

  Thanks to the ROMhacking.net community for the documentation and
  utilities that made this project possible, and to everyone who reported
  typos after the 1.0 release.


--------------------------------------------------------------------------------
  8. LEGAL
--------------------------------------------------------------------------------

  Phantasy Star IV: The End of the Millennium is copyright SEGA.
  This is an unofficial, non-commercial fan translation distributed as a
  patch file only. It contains no copyrighted game data.

  The patch may be freely redistributed as long as this readme is
  included and no fee is charged. Do not distribute pre-patched ROMs.


--------------------------------------------------------------------------------
  9. CONTACT
--------------------------------------------------------------------------------

  YouTube ........... https://www.youtube.com/@rgbretrogaming
  Email ............. rgbretrogaming@protonmail.com


--------------------------------------------------------------------------------
  10. CHANGELOG
--------------------------------------------------------------------------------

  v1.1  -  02.09.2026

    Umlauts and eszett
      - Both game fonts extended by ä ö ü Ä Ö Ü ß (dialogue font: 1bpp
        8x16; menu font: 4bpp 8x8, Nemesis compressed)
      - Complete script converted from ae/oe/ue/ss to proper German
        spelling, checked word by word (long vowel/diphthong -> ß,
        short vowel -> ss)
      - Title screen redrawn: "PRESS START BUTTON" -> "STARTTASTE DRÜCKEN"

    German menu texts
      - STATE -> WERTE, MACRO -> MAKRO, AUSRST -> RÜST, VERG -> GIFT,
        PARA -> LÄHM
      - Battle menu (vehicle): ATTAC -> KAMPF, OPTIN -> OPTION
      - Battle menu (on foot): COMD -> BEFEHL, MACR -> MAKRO,
        RENN -> FLUCHT
      - Button config: CAMP/CANCL/SPEAK -> LAGER/ABBR./REDEN,
        "Tasten Setting" -> "Tastenbelegung"
      - Save prompt: "Speicher Slot ?" -> "Speicherplatz?"

    Item descriptions fixed
      - From MOON-DEW onwards, every item in the inventory showed the
        wrong description (TELEPIPE said "revives someone completely",
        ESCAPIPE showed the MAHLAY shield text). The field menu locates
        descriptions by counting $FE separators, and MOON-DEW, STAR-DEW
        and SOL-DEW ended with $FF instead - merging those entries and
        shifting the following 31 descriptions by up to three positions.
        Present since version 1.0.

    Item descriptions no longer overflow their window
      - The menu message window fits 24 characters on two lines; longer
        lines ran past the right border into the neighbouring window
        (SILV-ROD showed "Laconia niedriger Reinheit.", 27 characters).
        14 descriptions were affected. Eleven only needed a different
        line break, three were shortened because they did not fit even
        when hyphenated. Present since version 1.0.

    Layout fix in the battle option windows
      - Both battle option windows are two tiles wider now, so the German
        words fit next to the selection box. This also fixes a display
        bug: the six-letter entries used to overwrite the right-hand
        window border in the vehicle battle menu.

    Spelling corrections in the translation
      interesantes -> Interessantes, durchdrunken -> durchdrungen (12x),
      erhoet -> erhöht, hochfrekuenz -> Hochfrequenz-, Stahlstirband ->
      Stahlstirnband, Lahmung -> Lähmung, aufzgeben -> aufzugeben,
      "Problemeseit" -> "Probleme seit", "starben,und" -> "starben, und",
      "Dein Inventar is voll" -> "ist voll", nordostlich/nördöstlich ->
      nordöstlich, nördwestlich -> nordwestlich, überglückich ->
      überglücklich, blos -> bloß, enthaellt -> enthält, Orbid -> Orbit,
      Intriegen -> Intrigen, Kautz -> Kauz, hütten -> hüten, Bealger ->
      Bälger, vertroettelt -> vertrottelt, Achja -> Ach ja, Dezolianer ->
      Dezorianer, spiralte -> trudelte, plus two truncated sentences and
      several stray spaces.

    Layout
      - Three intro lines were 33 characters long; the intro renderer only
        draws 32, so the last character was silently dropped. Rewrapped.

    Technical
      - The ROM is no longer expanded; it is a stock 3 MB image again.

  v1.0  -  05.08.2026  -  Initial release


================================================================================
================================================================================


--------------------------------------------------------------------------------
  ÜBER DIESEN PATCH  (Deutsch)
--------------------------------------------------------------------------------

Dieser Patch übersetzt Phantasy Star IV: The End of the Millennium für
das Sega Mega Drive ins Deutsche. Es handelt sich um ein inoffizielles
Fanprojekt ohne Verbindung zu SEGA.

  Dialoge ............. übersetzt
  Menüs / Systemtext .. übersetzt
  Gegenstandsnamen .... NICHT übersetzt, im englischen Original belassen
  Eigennamen .......... NICHT übersetzt - Charaktere, Orte, Techniken
                        und Gegner behalten ihre englischen Namen

Das ist eine bewusste Entscheidung. Gegenstands- und Eigennamen sind fest
mit der Identität der Serie verbunden und den meisten Fans nur in ihrer
englischen Form geläufig. Außerdem vermeidet die Beibehaltung Platz- und
Pointer-Probleme im Menüsystem.

  NEU IN VERSION 1.1: ECHTE UMLAUTE

Version 1.0 musste Umlaute noch klassisch umschreiben - ae, oe, ue und
ss -, weil der Zeichensatz des Spiels diese Zeichen schlicht nicht
enthielt. Version 1.1 behebt das an der Wurzel: Beide Schriftarten des
Spiels wurden um sieben neue Zeichen erweitert (ä, ö, ü, Ä, Ö, Ü und ß),
und der komplette Text wurde auf korrekte deutsche Rechtschreibung
umgestellt. Aus "Schluessel" wird "Schlüssel", aus "grosse" wird "große".

Auch der Titelbildschirm wurde neu gezeichnet: Dort steht jetzt
"STARTTASTE DRÜCKEN" statt "PRESS START BUTTON".

Dazu kam ein vollständiger Korrekturdurchgang über alle 12.018 Textstellen
- die vollständige deutsche Änderungsliste steht am Ende dieser Datei
unter "CHANGELOG (Deutsch)".

Dies ist das zweite ROM-Hacking-Projekt des Autors, nach einer deutschen
Übersetzung von Phantasy Star III. Es wurde im Alleingang erstellt, wobei
der KI-Assistent Claude (Anthropic) sowohl für die Übersetzung selbst als
auch als technische Unterstützung bei Skript-Extraktion, Textausrichtung
und Teilen der Assembler-Arbeit zum Einsatz kam. Jede einzelne Textstelle
wurde vom Autor selbst gegengelesen und abgenommen, bevor sie
veröffentlicht wurde.

Statt sich auf Stichproben zu verlassen, wurde die fertige Übersetzung
anschließend ein zweites Mal überprüft: mit einem kompletten
aufgezeichneten Let's Play der deutschen Fassung auf dem YouTube-Kanal
des Autors, sodass jede Zeile auch im tatsächlichen Spielkontext gesehen
und geprüft wurde.

  https://www.youtube.com/@rgbretrogaming


--------------------------------------------------------------------------------
  BENÖTIGTES ROM
--------------------------------------------------------------------------------

  Spiel:         Phantasy Star IV - The End of the Millennium (USA)
  Regionscode:   4  (USA)
  Seriennummer:  GM MK-1307 -00
  Copyright:     (C)SEGA 1994.NOV
  Größe:         3.145.728 Bytes  (3 MB / 24 Mbit)
  Header:        keiner - reiner headerloser .bin-/.md-Dump

  CRC32:         FE236442
  MD5:           84cbd0ff47f3c8e9d21d2c2fc39185fa
  SHA-1:         bc7ff6d6a8408f38562bc610f24645cad6c42629

  Der Patch lässt sich ausschließlich auf dieses ROM anwenden. Ein ROM
  liegt nicht bei und wird auch nicht bereitgestellt.


--------------------------------------------------------------------------------
  ANWENDUNG
--------------------------------------------------------------------------------

  1. Floating IPS (Flips) starten und "Apply Patch" wählen.
  2. Die Datei PS4_German_v1.1.bps aus diesem Archiv auswählen.
  3. Das unveränderte Phantasy Star IV ROM auswählen.
  4. Ergebnis unter neuem Dateinamen speichern - das Original nicht
     überschreiben.

  Meldet das Programm eine falsche Prüfsumme, liegt eine andere
  ROM-Version vor.


--------------------------------------------------------------------------------
  ERGEBNIS PRÜFEN
--------------------------------------------------------------------------------

  Nach dem Patchen sollte die Datei diese Werte aufweisen:

  Größe:         3.145.728 Bytes
  CRC32:         8776A69F
  MD5:           d5d42e572444dcbde2b670097b92fe54
  SHA-1:         28ec40cb6953d9d4dc1ac36e59981b7e390fd9e1

  Das gepatchte ROM ist jetzt exakt so groß wie das Original. Version 1.0
  musste die ROM noch um 51.732 Bytes erweitern, weil der deutsche Text
  mehr Platz brauchte als der englische. Durch die echten Umlaute ist der
  Text kurz genug geworden (aus jedem "ae" wurde ein einzelnes "ä"), dass
  die Erweiterung entfällt. Die ROM-Ende-Adresse im Header steht wieder
  auf dem Originalwert (0x002FFFFF).

  Die interne Mega-Drive-Prüfsumme wurde neu berechnet und ist gültig
  (E3EA). Das gepatchte ROM besteht damit die Integritätsprüfung der
  Konsole.

  Die SRAM-Konfiguration ist unverändert (8 KB bei 0x200001-0x203FFF).
  Batteriespeicherstände funktionieren wie im Original und bleiben auch
  zu Version 1.0 kompatibel.

  Hinweis zu Flash-Karten: Der Hinweis aus der 1.0-Readme, die Datei
  gegebenenfalls auf 4 MB aufzufüllen, ist hinfällig - die ROM ist wieder
  ein glattes 3-MB-Abbild.


--------------------------------------------------------------------------------
  GETESTET AUF
--------------------------------------------------------------------------------

  Emulator:      ares

  Diese Version wurde ausschließlich im Emulator ares getestet. Da die ROM
  wieder ein glattes 3-MB-Abbild ist, sollte sie von Flash-Karten ohne
  Auffüllen akzeptiert werden - dies wurde für diese Version jedoch nicht
  an echter Hardware überprüft.


--------------------------------------------------------------------------------
  CREDITS
--------------------------------------------------------------------------------

  Übersetzung, Hacking, Test ............ Karlhungus

  Die Original-Credits des SEGA-Entwicklerteams sind vollständig
  erhalten. Es wurde kein Entwickler aus dem Abspann entfernt oder
  ersetzt.


--------------------------------------------------------------------------------
  RECHTLICHES
--------------------------------------------------------------------------------

  Phantasy Star IV: The End of the Millennium ist urheberrechtlich
  geschützt durch SEGA. Dies ist eine inoffizielle, nicht kommerzielle
  Fanübersetzung, die ausschließlich als Patchdatei verbreitet wird.
  Sie enthält keine geschützten Spieldaten.

  Die Weitergabe ist gestattet, solange diese Readme beiliegt und keine
  Gebühr erhoben wird. Die Verbreitung vorgepatchter ROMs ist untersagt.


--------------------------------------------------------------------------------
  KONTAKT
--------------------------------------------------------------------------------

  YouTube ........... https://www.youtube.com/@rgbretrogaming
  Email ............. rgbretrogaming@protonmail.com


--------------------------------------------------------------------------------
  CHANGELOG (Deutsch)
--------------------------------------------------------------------------------

  v1.1  -  02.09.2026

    Umlaute und Eszett
      - Beide Schriftarten des Spiels um ä ö ü Ä Ö Ü ß erweitert
        (Dialogschrift: 1bpp 8x16; Menüschrift: 4bpp 8x8, Nemesis-
        komprimiert)
      - Kompletter Text von ae/oe/ue/ss auf korrekte deutsche
        Rechtschreibung umgestellt, Wort für Wort geprüft (langer
        Vokal/Diphthong -> ß, kurzer Vokal -> ss)
      - Titelbildschirm neu gezeichnet: "PRESS START BUTTON" ->
        "STARTTASTE DRÜCKEN"

    Deutsche Menütexte
      - STATE -> WERTE, MACRO -> MAKRO, AUSRST -> RÜST, VERG -> GIFT,
        PARA -> LÄHM
      - Kampfmenü (Fahrzeug): ATTAC -> KAMPF, OPTIN -> OPTION
      - Kampfmenü (zu Fuß): COMD -> BEFEHL, MACR -> MAKRO,
        RENN -> FLUCHT
      - Tastenbelegung: CAMP/CANCL/SPEAK -> LAGER/ABBR./REDEN,
        "Tasten Setting" -> "Tastenbelegung"
      - Speicherdialog: "Speicher Slot ?" -> "Speicherplatz?"

    Gegenstandsbeschreibungen korrigiert
      - Ab MOON-DEW zeigte jeder Gegenstand im Inventar eine fremde
        Beschreibung (TELEPIPE „Erweckt jemand vollständig zum Leben.“,
        ESCAPIPE den Text des MAHLAY-Schilds). Das Feldmenü adressiert die
        Beschreibungen über gezählte $FE-Trenner; bei MOON-DEW, STAR-DEW
        und SOL-DEW stand $FF statt $FE. Dadurch verschmolzen diese
        Einträge mit dem folgenden und die 31 Beschreibungen danach
        verrutschten um bis zu drei Positionen. Fehler stammt aus 1.0.

    Gegenstandsbeschreibungen laufen nicht mehr aus dem Fenster
      - Das Meldungsfenster der Menüs fasst 24 Zeichen in zwei Zeilen;
        längere Zeilen liefen über den rechten Rahmen hinaus ins
        Nachbarfenster (bei SILV-ROD stand „Laconia niedriger
        Reinheit." mit 27 Zeichen). Betroffen waren 14 Beschreibungen.
        Elf brauchten nur einen anderen Zeilenumbruch, drei wurden
        gekürzt, weil sie auch getrennt nicht passten. Fehler aus 1.0.

    Layoutkorrektur in den Kampf-Auswahlfenstern
      - Beide Auswahlfenster im Kampf sind zwei Kacheln breiter, damit
        die deutschen Begriffe neben das Auswahlkästchen passen. Damit
        ist zugleich ein Anzeigefehler behoben: Die sechsstelligen
        Einträge überschrieben im Fahrzeug-Kampfmenü bislang die rechte
        Rahmenspalte des Fensters.

    Rechtschreibkorrekturen in der Übersetzung
      interesantes -> Interessantes, durchdrunken -> durchdrungen (12x),
      erhoet -> erhöht, hochfrekuenz -> Hochfrequenz-, Stahlstirband ->
      Stahlstirnband, Lahmung -> Lähmung, aufzgeben -> aufzugeben,
      "Problemeseit" -> "Probleme seit", "starben,und" -> "starben, und",
      "Dein Inventar is voll" -> "ist voll", nordostlich/nördöstlich ->
      nordöstlich, nördwestlich -> nordwestlich, überglückich ->
      überglücklich, blos -> bloß, enthaellt -> enthält, Orbid -> Orbit,
      Intriegen -> Intrigen, Kautz -> Kauz, hütten -> hüten, Bealger ->
      Bälger, vertroettelt -> vertrottelt, Achja -> Ach ja, Dezolianer ->
      Dezorianer, spiralte -> trudelte, dazu zwei abgeschnittene Sätze
      und mehrere fehlende/doppelte Leerzeichen.

    Layout
      - Drei Intro-Zeilen waren 33 Zeichen lang; der Intro-Renderer
        zeichnet aber nur 32, das letzte Zeichen fiel stillschweigend
        weg. Neu umbrochen.

    Technisch
      - Die ROM wird nicht mehr erweitert, sondern ist wieder ein
        glattes 3-MB-Abbild.

  v1.0  -  05.08.2026  -  Erstveröffentlichung


================================================================================
