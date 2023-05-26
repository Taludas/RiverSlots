# RiverSlots

![Thumbnail](docs/Thumbnail_169.png)

Dieses Repo enthält Inseldateien, um Flussbauplätze und dazugehörige Flussgebäude, wie sie in Enbesa zu finden sind, auf allen Inseln der Alten und Neuen Welt zu integrieren.

## How to use

- Verwendet entweder den [iModYourAnno](https://github.com/anno-mods/iModYourAnno/releases) Mod-Manager oder wisst [wie man Mods manuell installiert](https://github.com/jakobharder/anno1800-mod-loader#mods).
- Wenn ihr die Mod manuell herunterlädt, verwendet das Archiv aus [GitHub Releases](https://github.com/Taludas/RiverSlots/releases). Ladet nicht das gesamte Repo herunter!

**Diese Mod ERFORDERT ein neues Savegame! Andernfalls werden die Inseln keine Fluss-Slots anzeigen**

**Aufgrund der enormen Größe der Inseldateien besteht die Mod aus vier Zip-Dateien!**  
Bitte ladet alle Dateien, um die beabsichtigte volle Erfahrung zu bekommen. Ihr könnt auch entsprechende Paare wählen,  so dass die Fluss-Slots nur in der jeweiligen Region zur Verfügung stehen (OW/OW und NW/NW).

**Bekannte Inkompatibilitäten**

Aufgrund der Natur der Mod können bestimmte Mods, die Karten-Templates verändern, meine Mod beeinträchtigen. Diese Mods bearbeiten in der Regel die Karten-Templates, um mehr/weniger kontinentale Inseln (Crown Falls, Manola) einzubeziehen oder sie zu anderen Sessions hinzuzufügen. Wenn ihr diese Mods verwenden, erhaltet ihr auf den kontinentalen Inseln keine Flussbauplätze. Alle anderen Inseln, die über den Zufalls-Pool hinzugefügt werden, sind davon nicht betroffen und werden Fluss-Slots haben. Es hängt auch von der Reihenfolge ab, in der die Kartenmods geladen werden. Wenn meine Mod nach ihr geladen wird, besteht eine gute Chance, dass ich die Änderungen der Kartenmod mit meinem Karten-Template für Cap Trewlany überschreibe. In diesem Fall hat CF zwar Fluss-Slots, aber man verpasst die Änderungen aus der Map-Mod.

## Changelog
<details>
    <summary>Patch Notes Version 1.0.2</summary>

* Hotfix für viele kleine Bugs:
- Behebt das Problem, bei dem die Wassermühle für Mehl nicht im Baumenü für Kekse erscheint.
- Behebt das Problem, dass die KI-Gegner auf Bauern-Stufe hängen bleiben, weil sie die Flusssägemühle bauen wollen, aber nicht können, da sie erst bei Handwerkern freigeschaltet wird.
- Hinzufügen mehrerer Inkompatibilitäten: Include NorthernRiversRemoved, MapSeeds Patch3, da sie Inseln mit Flussbauplätzen entfernen/verändern.
- Fügt Kompatibilät mit Jakobs Alternative Needs hinzu, sodass die Gemüsefarm im Baumenü für Fisch wieder erscheint.
</details>
<details>
    <summary>Patch Notes Version 1.0.1</summary>

* Neues Feature:
    - Getrenntes Bau-Menü für Fluss-Gebäude in OW und NW (OW: Ende des Bauern-Menüs und Anfang des Verbrauchsgüter-Menüs, NW: nach Lagerhaus im Jornalero-Menü und Anfang des Verbrauchsgüter-Menüs)
    - Deutsches Readme

* Hotfix für viele kleine Bugs:
- Fluss-Sägemühlen in OW und NW werden nun korrekt mit 1 Farmer/1 Jornalero aufgedeckt
    - Behebt das Problem des doppelten Bau-Menü-Eintrags für alle Gebäude aufgrund des Updates auf GU17.1, behebt die Bedingungen, unter denen der Fallback-Eintrag im Menü erscheint
    - Korrektur der fehlenden Übersetzung für River Sawmill NW in der deutschen Lokalisierung
- Behebung von Grafikproblemen bei Clay Collector OW/NW (Feedbackunit mit AdapttoTerrainHeight clippt durch Mesh, Cutout Mesh sichtbar bei DX12)
    - Behebung von Grafikproblemen bei Goldwäscher (Cutout-Mesh bei DX12 sichtbar)
- Behebung von Grafikproblemen bei River Fishery und River Fishoil Factory (fehlende Props und falsche Laufsequenz bei Walking Fisher)
</details>
<details>
    <summary>Patch Notes Version 1.0.0</summary>

* Erstveröffentlichung
    - Flussbauplätze für Alte und Neue Welt
    - Erste Fluss-Gebäude für die Alte und Neue Welt hinzugefügt
        - OW: Fluss-Fischerei, Fluss-Tonsammler, Fluss-Sägemühle, Fluss-Mehlmühle, Fluss-Kraftwerk
        - NW: Fluss-Fischölfabrik, Fluss-Perlenfarm, Fluss-Tonsammler, Fluss-Sägewerk, Goldwäscher, Fluss-Kraftwerk
</details>

## Mod-Beschreibung mit Übersicht der Hauptmerkmale
**Bitte denkt daran, immer das Changelog zu überprüfen, um die neuen oder geänderten Funktionen zu sehen.**

![banner](docs/banner.png)
### Riverslots
Auf jeder Insel gibt es jetzt eine unterschiedliche Anzahl von Flussbauplätzen (von 1 auf den mittleren Inseln bis zu 10 auf CF). Diese funktionieren genau wie die in Enbesa. Slot-Gebäude können über beide Seiten des Flussbauplatzes verbunden werden. Da das UI hartcoded ist, können wir leider kein schönes Interface zur Verfügung stellen, um Gebäude direkt auf dem Slot zu bauen, man muss sie aus dem Baumenü auswählen.

Dieser Mod ist vor allem als Modder-Ressource relevant, da er die notwendigen Inseldateien bereitstellt, um ein Projekt mit eigenen Fluss-Slot-Gebäuden zu starten. Es steht also jedem frei, diese in seine eigene Mod einzubinden, als Abhängigkeit via modinfo.json Datei. Aufgrund der enormen Größe der Mods würde ich nicht empfehlen, sie als Unterordner in eurer Mod bereitzustellen.

![banner_riverslotbuildings_ow](docs/banner_riverslotbuildings_ow.png)
### Riverslot Buildings OW
Diese Mod enthält fünf neue Gebäude, die zu den neu eingeführten Fluss-Slots in der Alten Welt passen. Sie alle produzieren Vanilla-Güter mit einer geringfügig schnelleren Rate als ihre Nicht-Fluss-Gegenstücke. Das Flusskraftwerk hat die gleiche Reichweite wie das Vanilla-Ölkraftwerk. Ihr findet die Gebäude entweder in ihren jeweiligen Produktionsketten, einer eigenen Gebäudekategorie oder direkt neben dem Vanillagebäude.

Die folgenden Gebäude sind für den Bau von Fluss-Slots verfügbar:
- Flussfischerei (50 Bauern)
- Fluss-Lehmsammler (1 Arbeiter)
- Fluss-Sägemühle (1 Handwerker)
- Fluss-Mehlmühle (1 Handwerker)
- Flusskraftwerk (1 Ingenieur)

Mit iMYA könnt ihr einstellen, mit welchen Gebäuden ihr spielen möchtet.

![banner_riverslotbuildings_nw](docs/banner_riverslotbuildings_nw.png)
### Riverslot Buildings NW
Diese Mod enthält sechs neue Gebäude, die zu den neu eingeführten Fluss-Slots in der Neuen Welt passen. Sie alle produzieren Vanilla-Güter mit einer geringfügig schnelleren Rate als ihre Nicht-Fluss-Gegenstücke. Das Flusskraftwerk hat die gleiche Reichweite wie das Vanilla-Ölkraftwerk. Ihr findet die Gebäude entweder in ihren jeweiligen Produktionsketten, in einer eigenen Gebäudekategorie oder direkt neben dem Vanillagebäude.

Die folgenden Gebäude sind für den Bau von Fluss-Slots verfügbar:
- Fluss-Fischölfabrik (50 Jornaleros)
- Fluss-Perlenfarm (500 Jornaleros)
- Fluss-Lehmsammler (1 Obrero)
- Sägewerk am Fluss (1 Obrero)
- Goldwäscher (300 Obrero)
- Fluss-Kraftwerk (900 Artista)

Mit iMYA könnt ihr einstellen, mit welchen Gebäuden ihr spielen möchtet.

## Special Thanks
Vielen Dank an Taubenangriff für die Bereitstellung von River Slot Locations für die fünf vanilla NW large islands und die 6 vanilla medium islands. Er hatte die ursprüngliche Idee hinter dieser Mod bereits in den frühen Tagen des New Horizons Projects, aber da das Hinzufügen von River Slots ziemlich mühsam ist, bin ich eingesprungen und habe passende Standorte für alle Inseln der Alten Welt sowie die neu hinzugekommenen Inseln der Neuen Welt nach DLC12 gefunden.