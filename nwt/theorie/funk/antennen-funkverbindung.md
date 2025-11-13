
## Thema: Antennen & Funkverbindungen

### Zusammenfassung

Die Qualität einer Funkverbindung wird durch eine Vielzahl physikalischer und technischer Faktoren bestimmt, die gemeinsam das Signal beeinflussen, das am Empfänger ankommt. Der Professor betonte, dass der Begriff „Qualität“ eigentlich kein exakter technischer Terminus ist, sondern sich in der Praxis auf messbare Größen wie **Sendeleistung**, **Antennengewinn**, **Richtcharakteristik**, **Polarisation**, **Impedanzanpassung** und **Dämpfung** zurückführen lässt.

#### 1. **Sendeleistung (P_t})**

Sie beschreibt die abgegebene Energie des Senders pro Zeit. Je höher die Sendeleistung, desto größer die abgestrahlte Feldstärke. Allerdings steigt die Reichweite nicht linear mit der Leistung – eine Verdopplung der Entfernung erfordert eine Vervierfachung der Leistung, da die Feldstärke quadratisch mit dem Abstand abnimmt (Freiraumdämpfung).


$P_r = P_t \times G_t \times G_r \times \left(\frac{\lambda}{4\pi R}\right)^2$

Diese Beziehung (Friis-Gleichung) verdeutlicht den Zusammenhang zwischen Sendeleistung, Antennengewinnen und der Entfernung (R).

#### 2. **Antennengewinn (G) und Direktivität**

Der Antennengewinn beschreibt, wie stark eine Antenne die abgestrahlte Energie in eine bevorzugte Richtung bündelt.

* **Isotrope Antenne**: strahlt gleichmäßig in alle Richtungen (theoretisches Modell, 0 dBi).
* **Richtantenne**: konzentriert Energie, hat daher höheren Gewinn in dB (z. B. 6 dBi, 12 dBi usw.).
  Die **Direktivität** ist das Maß dieser Bündelung, während der Gewinn zusätzlich Verluste durch Ineffizienzen berücksichtigt.

#### 3. **Polarisation**

Die Polarisation gibt die Schwingungsebene des elektrischen Feldes an.

* Vertikale Polarisation → Feldvektor schwingt vertikal.
* Horizontale Polarisation → Feldvektor schwingt horizontal.
  Für optimalen Empfang muss die Polarisation von Sender und Empfänger übereinstimmen. Ein Mismatch kann zu Dämpfungen von über 20 dB führen.

#### 4. **Antennenwiderstand / Impedanzanpassung**

Eine Antenne hat einen **Eingangswiderstand** (typisch 50 $\Omega$). Ist dieser nicht an die Sendeendstufe angepasst, kommt es zu Reflexionen — ein Teil der Energie wird nicht abgestrahlt, sondern zurückgeworfen.
Das **Stehwellenverhältnis (SWR)** beschreibt dieses Verhältnis. Optimal ist SWR = 1.
→ Je besser die Anpassung, desto effizienter die Abstrahlung.

#### 5. **Wetter, Umgebung, Material**

Die Umgebung beeinflusst die Dämpfung stark. Regen, Nebel, Schnee oder Hindernisse (Gebäude, Bäume) absorbieren oder streuen Signale, besonders bei höheren Frequenzen (GHz-Bereich).
Auch das Material der Antenne spielt eine Rolle (Leitfähigkeit, Korrosionsschutz). Aluminium oder Kupfer sind Standard, da sie gute elektrische Eigenschaften besitzen.

#### 6. **Modulationseinfluss**

Die Modulation selbst (AM, FM, QAM etc.) bestimmt nicht direkt die physikalische Reichweite, wohl aber die **Signalrobustheit** gegenüber Rauschen. Frequenzmodulierte Signale (FM) sind z. B. weniger störanfällig als Amplitudenmodulierte (AM).

#### 7. **Beispielhafte Betrachtung laut Professor**

Im Gespräch betonte der Professor, dass man den Begriff „Qualität“ durch konkrete Messgrößen ersetzen sollte. Wenn man eine Funkstrecke verbessern will, schaut man nicht auf „Qualität“, sondern auf:

* Feldstärke (in dBµV/m)
* Empfangsleistung (in dBm)
* Signal-Rausch-Verhältnis (SNR)
* Fehlerrate (BER)

Er brachte als Beispiel an:

> „Wenn ich die Antenne leicht drehe oder den Abstand ändere, verändert sich die Empfangsleistung dramatisch. Also reden wir besser von Leistung, Antennengewinn und Dämpfung – das sind die messbaren Größen, nicht einfach ‚Qualität‘.“

---

### Beispielhafte Prüfungsfrage (im Stil des Professors)

> **Frage:**
> „Angenommen, Sie betreiben eine Funkstrecke zwischen zwei Gebäuden mit 2,4 GHz WLAN.
> Trotz 100 m Sichtverbindung haben Sie eine instabile Verbindung.
> Welche physikalischen Ursachen können das erklären und wie könnten Sie die Verbindung verbessern, **ohne** die Sendeleistung zu erhöhen?“

---

### Beispielhafte Antwort

**Analyse der Situation:**
2,4 GHz WLAN → Wellenlänge etwa 12,5 cm.
Über 100 m im Freifeld sollte das Signal stabil sein – Instabilität deutet auf **Fehlausrichtung, Polarisationsfehler, Impedanzmismatch oder Reflexionen** hin.

**Mögliche Ursachen:**

1. **Fehlende Polarisationstreue** – Sender und Empfänger sind unterschiedlich polarisiert (z. B. eine vertikal, eine horizontal). → Verlust bis zu 20 dB.
2. **Richtantennen nicht korrekt ausgerichtet** – durch den engen Öffnungswinkel kann das Signal schwanken.
3. **Mehrwegeausbreitung** – Reflexionen an Gebäudefassaden führen zu Interferenzen (Fading).
4. **Impedanzmismatch** – falsche Kabel oder Adapter mit 75 $\Omega$ statt 50 $\Omega$.
5. **Wetter oder Hindernisse** – Feuchtigkeit oder metallische Gegenstände in der Fresnel-Zone.

**Verbesserungsmöglichkeiten ohne Leistungserhöhung:**

* Polarisation von Sender und Empfänger identisch ausrichten.
* Antenne mit höherem Gewinn (z. B. Yagi oder Parabolantenne) einsetzen → fokussierte Abstrahlung.
* Antennen präzise ausrichten (Signal-Peak durch Messung finden).
* Höher montieren, um Fresnel-Zone freizuhalten.
* Gute Koaxialkabel mit korrektem Wellenwiderstand verwenden.

**Zusammenfassung:**
Die Reichweite einer Funkstrecke hängt nicht nur von der Sendeleistung ab, sondern von einer Kombination aus physikalischen Parametern, Antennentechnik und Umgebungsbedingungen. Eine korrekte Anpassung und Ausrichtung kann oft mehr bewirken als reine Leistungssteigerung.

---

### Lernnotizen & Merksätze

**Merksätze:**

* „Verdopplung der Entfernung → 6 dB weniger Signal.“
* „Ohne Anpassung keine Leistung: 50 $\Omega$ muss zu 50 $\Omega$ passen.“
* „Polarisation muss übereinstimmen – sonst sendet man in die falsche Ebene.“
* „Ausrichtung schlägt Wattzahl.“

**Übungsaufgabe:**
Berechne den theoretischen Verlust bei einer 2,4 GHz-Funkstrecke über 100 m im Freiraum.

$L_{fs}(dB) = 20\log_{10}\left(\frac{4\pi d}{\lambda}\right)$

Einsetzen:
$\lambda = \frac{c}{f} = \frac{3\cdot10^8}{2,4\cdot10^9} = 0,125 m$
$\Rightarrow L_{fs} = 20\log_{10}\left(\frac{4\pi \cdot 100}{0,125}\right) \approx 100 dB$

→ Der Empfänger braucht also eine Antenne und einen Empfänger, die zusammen ca. 100 dB Verlust ausgleichen können (durch Gewinn und Empfindlichkeit).
