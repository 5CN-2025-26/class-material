
##  Thema: Wellenarten & Ionosphäre – Raumwelle, Bodenwelle, Direktwelle

### Ausführliche Zusammenfassung

Funkwellen breiten sich nicht auf eine einzige Art aus – ihre Ausbreitung hängt stark von der **Frequenz**, der **Sendeleistung**, den **Eigenschaften der Atmosphäre** und der **Oberfläche der Erde** ab. Der Professor erklärte, dass insbesondere bei klassischen Rundfunksystemen (Lang-, Mittel-, Kurzwelle) die Ausbreitungsart entscheidend für die Reichweite ist.

Er unterschied dabei mehrere **Haupttypen elektromagnetischer Wellen**, die sich auf verschiedene Weise vom Sender zum Empfänger bewegen:

---

### 1. **Bodenwelle (Ground Wave)**

* Sie folgt der Erdoberfläche, also der „Bodenkrümmung“.
* Besonders ausgeprägt bei niedrigen Frequenzen (Lang- und Mittelwelle, < 3 MHz).
* Die Welle „haftet“ quasi an der Erdoberfläche, wird dabei aber zunehmend gedämpft.
* Dämpfung hängt stark von der **Bodenleitfähigkeit** ab (Meerwasser leitet sehr gut → große Reichweite; trockener Sandboden → hohe Verluste).
* Anwendung: AM-Rundfunk, maritime Kommunikation, Navigationssysteme auf Langwelle.

**Beispiel aus dem Unterricht:**
Der Professor erwähnte, dass man früher mit Mittelwellenrundfunk problemlos Hunderte Kilometer weit senden konnte, **weil sich die Bodenwelle an der Erdkrümmung entlang ausbreitet**, während heutige UKW-Sender (VHF) das nicht mehr schaffen.

---

### 2. **Raumwelle (Sky Wave)**

* Entsteht, wenn das Funksignal die **Ionosphäre** erreicht, dort reflektiert oder gebrochen wird und zurück zur Erde fällt.
* Dadurch sind sehr große Distanzen möglich (oft mehrere Tausend Kilometer).
* Typisch für Frequenzen im **Kurzwellenbereich (3–30 MHz)**.
* Die Reichweite hängt stark von der **Ionisierungsschicht** ab, die wiederum durch Sonnenstrahlung und Tageszeit beeinflusst wird.
* Nachts reflektiert die Ionosphäre stärker (bessere Reichweiten), tagsüber oft schwächer.

**Atmosphärische Schichten laut Professor:**

1. **Troposphäre** – bis ca. 10–15 km: Wetter, Wolken, kaum Funkreflexion.
2. **Stratosphäre** – bis 50 km: kaum relevant für Funk.
3. **Mesosphäre** – bis 85 km: Übergangszone.
4. **Ionosphäre** – 85–600 km: enthält elektrisch geladene Teilchen (Ionen), reflektiert Funkwellen bestimmter Frequenzen.

Die Ionosphäre wird in D-, E- und F-Schichten unterteilt:

* **D-Schicht**: absorbiert stark (tagsüber).
* **E-Schicht**: kann reflektieren, aber schwach.
* **F-Schicht (F1/F2)**: Hauptreflexion für Kurzwellen (nachts besonders aktiv).

Der Professor erklärte:

> „Ob eine Raumwelle entsteht, hängt nicht einfach von der Frequenz ab, sondern von der Kombination aus Leistung und Ionisationszustand. Mit genügend Leistung kann man fast jede Schicht erreichen – aber das ist energetisch ineffizient.“

---

### 3. **Direktwelle (Line of Sight, LOS)**

* Bewegt sich direkt vom Sender zum Empfänger – wie ein Lichtstrahl.
* Nur bei „Sichtverbindung“ möglich.
* Typisch für **UKW, WLAN, Mikrowellen, Satellitenkommunikation**.
* Reichweite begrenzt durch Erdkrümmung (etwa 40 km bei hohen Antennenmasten).
* Gebäude, Bäume, Berge → Abschattung.
* Bei höheren Frequenzen (z. B. 2,4 GHz WLAN oder 5G im Millimeterbereich) wird selbst Regen relevant.

Der Professor verglich das so:

> „UKW ist quasi wie Licht – was Sie nicht sehen, erreicht Sie nicht.“

---

### 4. **Faktoren, die die Ausbreitung beeinflussen**

| Faktor               | Wirkung                                                           |
| -------------------- | ----------------------------------------------------------------- |
| Frequenz             | Niedrige Frequenzen → Bodenwellen; hohe Frequenzen → Direktwellen |
| Tageszeit            | Ionosphäre reflektiert nachts besser                              |
| Sonnenaktivität      | Erhöhte Ionisation → bessere Reflexion                            |
| Gelände & Oberfläche | Wasser → bessere Bodenwelle; Beton → mehr Reflexion               |
| Wetter               | Regen/Nebel → Dämpfung bei Mikrowellen                            |
| Sendeleistung        | Erhöht Reichweite, aber nicht immer linear                        |

---

### Zusammenhänge – Beispielrechnungen

**Fresnel-Zone**
Für Direktwellenverbindungen (z. B. WLAN) ist entscheidend, dass die sogenannte *Fresnel-Zone* frei bleibt. Sie beschreibt den Bereich um die direkte Sichtlinie, in dem Reflexionen destruktiv interferieren können.
Faustregel:

$r_n = \sqrt{\frac{n \lambda d_1 d_2}{d_1 + d_2}}$

– die erste Fresnel-Zone (n=1) sollte zu mindestens 60 % frei von Hindernissen sein.

---

### Beispielhafte Prüfungsfrage (im Stil des Professors)

> **Frage:**
> „Sie betreiben eine Kurzwellenverbindung mit 7 MHz zwischen Wien und Kairo.
> Am Tag ist das Signal stark gedämpft, nachts hingegen klar und stabil.
> Erklären Sie anhand der ionosphärischen Schichten, warum das so ist,
> und welche Wellenart hier vorliegt.“

---

### Musterantwort

**Schritt 1 – Einordnung der Wellenart:**
7 MHz liegt im Kurzwellenbereich → typischerweise Ausbreitung als **Raumwelle** über Reflexion an der Ionosphäre.

**Schritt 2 – Erklärung des Tages/Nacht-Unterschieds:**

* Tagsüber: Sonneneinstrahlung erzeugt die **D-Schicht** (60–90 km), die stark dämpft → Signal wird absorbiert, bevor es die F-Schicht erreicht.
* Nachts: D-Schicht verschwindet, F-Schicht bleibt bestehen → Signal erreicht diese Höhe, wird reflektiert → große Reichweiten möglich.

**Schritt 3 – Fazit:**

* Am Tag → starke Dämpfung durch D-Schicht, kaum Reflexion → schlechter Empfang.
* In der Nacht → D-Schicht weg, Reflexion an F2-Schicht → stabile Raumwelle.

**Schritt 4 – Zusatzfaktor:**
Die Frequenz (7 MHz) liegt knapp unterhalb der maximalen nutzbaren Frequenz (MUF) für diese Reflexion; wäre sie höher, würde sie nicht mehr zurückreflektiert, sondern ins All entweichen.

---

### Lernnotizen & Merksätze

**Merksätze:**

* „Langwelle folgt dem Boden, Kurzwelle springt vom Himmel, UKW sieht nur was im Blick ist.“
* „Ionosphäre reflektiert nachts, absorbiert tagsüber.“
* „Regen stört Mikrowelle, Sonne stört Kurzwelle.“
* „Fresnel-Zone frei halten – sonst Schatten in der Funkverbindung.“

**Übungsaufgabe:**
Ein Funkamateur betreibt eine 3,5 MHz-Verbindung (80 m-Band) zwischen Innsbruck und Berlin.
Nachts funktioniert sie gut, am Tag fast gar nicht.
→ Welche Schicht der Atmosphäre ist verantwortlich und warum?
**Antwort:** Die D-Schicht absorbiert tagsüber die niedrigen Frequenzen vollständig; nachts verschwindet sie, und die Wellen können an der F-Schicht reflektiert werden.
