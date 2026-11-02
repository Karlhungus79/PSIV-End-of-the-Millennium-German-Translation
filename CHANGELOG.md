# Changelog

Alle nennenswerten Änderungen an der deutschen Übersetzung von
*Phantasy Star IV: The End of the Millennium* (Sega Mega Drive).

Das Format orientiert sich an [Keep a Changelog](https://keepachangelog.com/de/1.1.0/),
die Versionierung an [Semantic Versioning](https://semver.org/lang/de/).

---

## [1.2] – 2026-11-02

Komfortupdate: ein neues **EXTRAS**-Menü im START-Fenster. Die Übersetzung
selbst ist unverändert gegenüber 1.1.

### Hinzugefügt

* **Fünfter START-Menüeintrag „EXTRAS“** mit vier Einstellungen:
  * `EXP MESETA` 1X / 2X / 4X: EXP- und Meseta-Belohnung pro Gegner wird beim
    Kampfende vor der Verteilung vervielfacht (Obergrenze 65.535 pro Gegner).
  * `ZUFALLSKAMPF` AN / AUS: unterdrückt nur Zufallskämpfe, keine Story-Kämpfe.
  * `KAMPF 2X` AUS / START / IMMER: Die Kampflogik läuft zweimal pro Bild
    (nur wenn START gehalten wird bzw. immer). Grafikübertragung und
    VBlank-Takt bleiben unverändert, Textausgabe und Musik werden nicht
    schneller.
  * `LAUFEN 2X` AUS / AN: nutzt die im Original vorhandene, aber ungenutzte
    4-Pixel-Schrittstufe der Lauftabelle. In Events und bei Fahrzeugen inaktiv.
* Neues Fenster 8 in der Fenstergruppe des System-Menüs (`Win_QOL`), Systemfenster
  um zwei Zeilen höher.

### Technisch

* Einstellungen im bisher unbenutzten RAM `$FFFFEF50`–`$FFFFEF53`, alle
  Startwerte 0 = Originalverhalten; sie werden nicht im Spielstand gespeichert.
* ROM-Größe unverändert (3.145.728 Bytes), ROM-Ende `0x002FFFFF`, interne
  Prüfsumme neu berechnet (`EE48`). SRAM-Konfiguration und Spielstände
  unverändert und kompatibel.
* Prüfsummen der gepatchten ROM: CRC32 `ECC48D6F`, MD5
  `d534643c2f0302caf09da2defb5f6889`, SHA-1
  `957c5e96acef8fd9589b1b57cdb5e4777722339d`.
* Savestates älterer Versionen sind nicht mehr kompatibel, da sich der
  Programmcode verschoben hat.

---

## [1.1] – 2026-09-02

Das große Umlaut-Update. Version 1.0 musste Umlaute noch als `ae`/`oe`/`ue`
und `ss` umschreiben, weil die Schriftarten des Spiels die Zeichen nicht
enthielten. Diese Version behebt das an der Wurzel und bringt gleich einen
vollständigen Korrekturdurchgang über den gesamten Text mit.

### Hinzugefügt

* **Echte Umlaute und Eszett im ganzen Spiel.** Beide Schriftarten wurden um
  je sieben Zeichen erweitert:
  * Dialogschrift (`graphics/font/Dialogue Font.bin`, 1bpp, 8×16): `ß` auf dem
    bis dahin ungenutzten Mittelpunkt-Slot `$38`, `ä ö ü Ä Ö Ü` auf den freien
    Slots `$4A`–`$4F`. Die Bitmap musste nicht vergrößert werden.
  * Menüschrift (`graphics/font/Font nemesis.bin`, 4bpp, 8×8, Nemesis-komprimiert):
    sieben neue Kacheln, Einträge `$58`–`$5E` in `wincharset.asm`. Die neu
    komprimierte Tabelle wurde per Dekomprimier-Rückvergleich verifiziert.
* **Deutscher Titelbildschirm.** „PRESS START BUTTON“ heißt jetzt
  „STARTTASTE DRÜCKEN“. Der Schriftzug ist Grafik, kein Text – vier der elf
  Nemesis-Kacheln (`P`, `B`, `U`, `O`) wurden zu `D`, `K`, `Ü`, `C` neu
  gezeichnet, die Enigma-Plane-Map neu kodiert. Beide Dateien sind zufällig
  exakt so groß wie vorher.

### Geändert

* **Kompletter Text auf korrekte deutsche Rechtschreibung umgestellt.**
  `ae`/`oe`/`ue` → `ä`/`ö`/`ü`, `ss` → `ß`, letzteres Wort für Wort nach der
  Regel *langer Vokal/Diphthong → ß, kurzer Vokal → ss* geprüft (270
  Kandidatenwörter, 95 Umstellungen). Echte Diphthonge (*Feuer*, *bauen*,
  *Quelle*) und Komposita mit Wortgrenze (*Aussage*, *Lebensstil*) blieben
  unangetastet.
* **Deutsche Menütexte.**

  | Stelle | vorher | nachher |
  |---|---|---|
  | Hauptmenü | `STATE` | `WERTE` |
  | Hauptmenü / Makro-Fenster | `MACRO` | `MAKRO` |
  | Hauptmenü | `AUSRST` | `RÜST` |
  | Statusanzeige | `VERG` | `GIFT` |
  | Statusanzeige | `PARA` | `LÄHM` |
  | Kampfmenü (Fahrzeug) | `ATTAC` | `KAMPF` |
  | Kampfmenü (Fahrzeug) | `OPTIN` | `OPTION` |
  | Kampfmenü (zu Fuß) | `COMD` | `BEFEHL` |
  | Kampfmenü (zu Fuß) | `MACR` | `MAKRO` |
  | Kampfmenü (zu Fuß) | `RENN` | `FLUCHT` |
  | Tastenbelegung | `CAMP` / `CANCL` / `SPEAK` | `LAGER` / `ABBR.` / `REDEN` |
  | Optionen | `Tasten Setting` | `Tastenbelegung` |
  | Speicherdialog | `Speicher Slot ?` | `Speicherplatz?` |

* **ROM wird nicht mehr erweitert.** Version 1.0 brauchte 51.732 Bytes extra,
  weil der deutsche Text länger war als der englische. Durch die echten
  Umlaute (aus `ae` wird ein Zeichen statt zwei) passt alles wieder in die
  Original-ROM: exakt 3.145.728 Bytes, ROM-Ende zurück auf `$2FFFFF`. Damit
  entfällt auch der Hinweis, die Datei für Flash-Karten auf 4 MB aufzufüllen.
* **Kampf-Auswahlfenster zwei Kacheln breiter.** Beide Hauptmenü-Fenster im
  Kampf (zu Fuß 8, im Fahrzeug 9 Kacheln) boten neben dem Auswahlkästchen
  nur Platz für vier bzw. fünf Zeichen. Sie sind jetzt beide 10 Kacheln
  breit, damit `BEFEHL` / `MAKRO` / `FLUCHT` und `KAMPF` / `OPTION` /
  `FLUCHT` vollständig hineinpassen. Der japanische Zweig behält seine
  Originalmaße.
* **Drei Intro-Zeilen neu umbrochen.** Der Intro-Renderer zeichnet nur 32
  Zeichen pro Zeile; das 33. fiel stillschweigend weg. Betroffen waren
  „der Kunst und den Wissenschaften,“ (Komma fehlte), „starben, und die
  fortgeschrittene“ und „Grenze ein dunkles, altes Übel...“. Der Wortlaut
  ist unverändert, nur die Umbrüche liegen anders.

### Behoben

Rechtschreibfehler der Übersetzung, gefunden bei einem systematischen
Wörterbuchabgleich aller 12.018 Textstellen (239.162 Zeichen):

| falsch | richtig | Fundstellen |
|---|---|---|
| `durchdrunken` | durchdrungen | 12 |
| `interesantes` | Interessantes | 1 |
| `erhoet` / `erhöt` | erhöht | 2 |
| `hochfrekuenz` | Hochfrequenz- | 2 |
| `Stahlstirband` | Stahlstirnband | 2 |
| `Lahmung` | Lähmung | 1 |
| `aufzgeben` | aufzugeben | 1 |
| `Dein Inventar is voll!` | … ist voll! | 2 |
| `überglückich` | überglücklich | 2 |
| `Problemeseit Anbeginn.` | Probleme seit Anbeginn. | 1 |
| `starben,und` | starben, und | 1 |
| `Danke...,oh.` | Danke..., oh. | 1 |
| `nordostlich`, `nördöstlich` | nordöstlich | 2 |
| `nördwestlich`, `nördwest-` | nordwestlich, nordwest- | 2 |
| `blos` | bloß | 1 |
| `enthaellt` / `enthällt` | enthält | 1 |
| `Orbid` | Orbit | 1 |
| `Intriegen` | Intrigen | 1 |
| `Kautz` | Kauz | 1 |
| `hütten` (Gumbious-Tempel) | hüten | 1 |
| `Bealger` | Bälger | 1 |
| `vertroettelt` | vertrottelt | 1 |
| `Achja` | Ach ja | 1 |
| `Dezolianer` | Dezorianer | 1 |
| `spiralte abwärts` | trudelte abwärts | 1 |
| `eine Nervensäge !` | eine Nervensäge! | 1 |
| abgeschnittener Satz in dialogue 43 | „…Aufgaben nichts zu tun hatte.“ | 1 |

**Vertauschte Gegenstandsbeschreibungen behoben.** Im Inventar zeigten ab
MOON-DEW alle Gegenstände eine fremde Beschreibung – TELEPIPE etwa „Erweckt
jemand vollständig zum Leben.“ und ESCAPIPE den Text des MAHLAY-Schilds.
Ursache: Die Beschreibungstabelle des Feldmenüs wird über gezählte
`$FE`-Trenner adressiert, und bei MOON-DEW, STAR-DEW und SOL-DEW stand
jeweils `$FF` statt `$FE`. Dadurch verschmolzen diese Einträge mit dem
folgenden, und alle 31 Beschreibungen danach rutschten um bis zu drei
Positionen. Die drei Trenner sind korrigiert; die Zuordnung wurde
anschließend im fertigen ROM für alle 160 Gegenstände nachgeprüft. Der
Fehler stammt aus Version 1.0.

**Zu breite Gegenstandsbeschreibungen umgebrochen.** Das Meldungsfenster der
Menüs fasst 24 Zeichen in zwei Zeilen; längere Zeilen liefen über den rechten
Fensterrahmen hinaus ins Nachbarfenster – sichtbar etwa bei SILV-ROD, wo
„Laconia niedriger Reinheit.“ (27 Zeichen) den Rahmen überschrieb. Betroffen
waren 14 Beschreibungen. Bei elf davon genügte ein anderer Zeilenumbruch, der
Wortlaut ist unverändert; drei passten auch getrennt nicht in 2 × 24 Zeichen
und wurden gekürzt (siehe „Wortlaut“ weiter unten). Auch dieser Fehler stammt
aus Version 1.0.

Dazu ein Anzeigefehler: Im Fahrzeug-Kampfmenü ist das Fenster nur neun
Kacheln breit, der Text beginnt aber in Spalte 3 – ein sechsstelliger
Eintrag lief damit genau auf die rechte Rahmenspalte. Das betraf `FLUCHT`
schon in Version 1.0 und mit `KAMPF`/`OPTION` alle drei Einträge. Durch das
breitere Fenster steht der Rahmen wieder frei.

`Bealger` war dabei ein Folgefehler der alten Umschreibung: gemeint waren
„Bälger“, geschrieben war `Bealger` statt `Baelger`, weshalb die
Umlaut-Umwandlung nicht griff.

### Unverändert

* Gegenstands-, Eigen-, Orts-, Technik- und Gegnernamen bleiben englisch.
* Die Wortwahl der Übersetzung wurde nicht angefasst – korrigiert wurden
  ausschließlich Schreibweise und Zeilenumbrüche. **Drei Ausnahmen**, weil
  der Text sonst nicht in das 24 Zeichen breite Meldungsfenster passte:

  | Gegenstand | vorher | nachher |
  |---|---|---|
  | PENGU-FEED | „Gegenstand zum Herbeirufen des Dezoris Pinguins." | „Gegenstand zum Rufen des Dezoris Pinguins." |
  | PLSM-RIFLE | „Tragbares Partikelgewehr, das Protonenstrahlen abfeuert." | „Partikelgewehr, das Protonenstrahlen abfeuert." |
  | WAVE-SHOT | „Waffe, die zerstörerische Schallwellen ausstrahlt." | „Waffe, die Schallwellen ausstrahlt." |
* Die Original-Credits des SEGA-Entwicklerteams sind vollständig erhalten.
* Kein Gameplay-Mod: Werte, Formeln, Erfahrungstabellen und Gegner sind
  unverändert.

### Prüfsummen

| | Ausgangs-ROM (USA) | Gepatchte ROM 1.1 |
|---|---|---|
| Größe | 3.145.728 | 3.145.728 |
| CRC32 | `FE236442` | `8776A69F` |
| MD5 | `84cbd0ff47f3c8e9d21d2c2fc39185fa` | `d5d42e572444dcbde2b670097b92fe54` |
| SHA-1 | `bc7ff6d6a8408f38562bc610f24645cad6c42629` | `28ec40cb6953d9d4dc1ac36e59981b7e390fd9e1` |

Interne Mega-Drive-Prüfsumme `E3EA`, gültig. SRAM unverändert
(8 KB, `$200001`–`$203FFF`) – Spielstände aus 1.0 bleiben kompatibel.

---

## [1.0] – 2026-08-05

### Hinzugefügt

* Erste Veröffentlichung der deutschen Übersetzung.
* Dialoge, Menü- und Systemtexte vollständig übersetzt.
* Gegenstands- und Eigennamen bewusst im englischen Original belassen.
* Qualitätssicherung durch ein komplett aufgezeichnetes Let's Play der
  deutschen Fassung, so dass jede Textzeile im Spielkontext gesichtet wurde.

### Bekannte Einschränkung

* Keine Umlaute: Der Zeichensatz des Spiels enthielt sie nicht, daher
  `ae`/`oe`/`ue`/`ss` als Umschreibung. Behoben in 1.1.

[1.1]: #11--2026-09-02
[1.0]: #10--2026-08-05
