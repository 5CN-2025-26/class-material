
##  Thema: Mehrwegeausbreitung, Diversity & Antennenarrays

###  Ausführliche Zusammenfassung

Der Professor erklärte, dass elektromagnetische Wellen sich in der Realität **nicht nur entlang eines einzigen Weges** vom Sender zum Empfänger ausbreiten, sondern häufig über **mehrere Pfade gleichzeitig**. Diese Mehrwegeausbreitung (engl. *Multipath Propagation*) ist eines der wichtigsten Themen der modernen Funktechnik, weil sie sowohl **Probleme** (z. B. Interferenzen) als auch **Chancen** (z. B. MIMO-Technik) bietet.

Er verband dieses Thema mit **Diversity**, **Antennenanordnungen (Arrays)** und **Radarprinzipien**, um zu zeigen, wie dieselben physikalischen Effekte in verschiedenen Anwendungen genutzt oder kompensiert werden.

---

### 1. **Was ist Mehrwegeausbreitung?**

Wenn ein Funksignal ausgesendet wird, trifft es in der Umgebung auf Hindernisse: Gebäude, Bäume, Fahrzeuge, Bodenflächen, Wasser, Wände etc.
Diese können das Signal **reflektieren, beugen oder streuen**.
Dadurch gelangen **mehrere Signalanteile** (mit unterschiedlicher Laufzeit, Phase und Stärke) zum Empfänger.

**Bildlich:**
Das gleiche Signal kommt mehrfach an – einmal direkt, einmal über Wände, einmal vom Boden reflektiert.

> Der Professor veranschaulichte das so:
> „Das ist wie Echo in einem Tunnel. Das Wort kommt mehrfach an – leicht zeitversetzt. Genau das passiert bei Funksignalen auch.“

---

### 2. **Folgen der Mehrwegeausbreitung**

Je nach Phasenlage dieser Signalanteile können sich die Wellen:

* **verstärken** (konstruktive Interferenz), oder
* **auslöschen** (destruktive Interferenz).

Das führt zu **Fading** – schwankender Empfangsfeldstärke am Empfänger.
Die Signalqualität ändert sich schon bei kleinen Positionsänderungen (oft im Zentimeterbereich).

#### Typische Effekte:

* **Rayleigh-Fading**: keine dominante Direktverbindung; viele reflektierte Pfade → starkes Schwanken.
* **Rician-Fading**: es gibt eine starke Direktkomponente + Reflexionen.
* **Shadowing**: langsame Pegeländerung durch Abschattung (z. B. durch Gebäude).

**Alltagsbeispiel:**
WLAN oder Handy-Signal verschwindet, wenn man den Kopf leicht dreht oder einen Schritt zur Seite macht → destruktive Interferenz.

---

### 3. **Gegenmaßnahmen: Diversity-Prinzip**

„Diversity“ bedeutet, **mehrere unabhängige Empfangswege** zu nutzen, um das Risiko eines Fading-Einbruchs zu verringern.
Wenn ein Weg gestört ist, liefert ein anderer noch ein brauchbares Signal.

#### Arten von Diversity:

| Typ                          | Prinzip                                 | Beispiel                            |
| ---------------------------- | --------------------------------------- | ----------------------------------- |
| **Raum-Diversity (Spatial)** | Mehrere Antennen mit Abstand ($\lambda$/2–\$lambda$)    | WLAN-Router mit 2–4 Antennen        |
| **Polarisation-Diversity**   | Unterschiedliche Polarisation (H/V)     | LTE- oder 5G-Antennen mit +45/-45 Grad |
| **Frequenz-Diversity**       | Nutzung mehrerer Frequenzen             | OFDM, Spread Spectrum               |
| **Zeit-Diversity**           | Wiederholung über Zeitfenster           | Fehlerkorrektur, Retransmission     |
| **Code-Diversity**           | Unterschiedliche Codierung (orthogonal) | CDMA-Systeme                        |

> Professor-Kommentar:
> „Diversity ist wie Sicherheitskopien – Sie speichern dasselbe auf mehreren Pfaden. Wenn einer ausfällt, ist das Signal trotzdem da.“

---

### 4. **MIMO (Multiple Input Multiple Output)**

**MIMO-Systeme** nutzen Mehrwege gezielt, statt sie zu bekämpfen.
Jede Sende- und Empfangsantenne erzeugt einen eigenen Signalpfad, der mathematisch durch eine *Kanalmatrix* beschrieben wird.
Diese Pfade können **gleichzeitig unterschiedliche Datenströme** transportieren.


$\mathbf{y} = \mathbf{H} \cdot \mathbf{x} + \mathbf{n}$


* $(\mathbf{H})$: Kanalmatrix (z. B. 2×2 bei zwei Sende- und zwei Empfangsantennen)
* $(\mathbf{x})$: gesendete Signale
* $(\mathbf{y})$: empfangene Signale
* $(\mathbf{n})$: Rauschen

**Beispiel:** WLAN 2x2 MIMO → zwei parallele Datenströme → doppelte Datenrate.

Der Professor betonte:

> „MIMO ist das Gegenteil von Diversity – statt nur zu sichern, nutzt man Mehrwege produktiv, um mehr Daten zu schicken.“

---

### 5. **Antennenarrays & Richtwirkung**

Ein **Antennenarray** besteht aus mehreren Einzelantennen, die phasenrichtig gespeist werden.
Dadurch lassen sich Signale **gezielt verstärken oder auslöschen**, um Strahlungsrichtungen zu steuern – dieses Prinzip nennt man **Beamforming**.

* Wird das Signal in einer bestimmten Richtung phasenverschoben eingespeist, addieren sich die Wellen konstruktiv → Richtstrahlung.
* In anderen Richtungen löschen sie sich aus → Unterdrückung von Störsignalen.

**Anwendungen:**

* WLAN Access Points mit adaptivem Beamforming
* 5G-Basisstationen mit „Massive MIMO“
* Radarsysteme (zur Entfernungsmessung, Geschwindigkeitsbestimmung)

**Vorteil:**

* Bessere Reichweite
* Höheres SNR
* Geringere Interferenz mit anderen Nutzern

---

### 6. **Radarprinzip & Dopplereffekt (kurz)**

Radar basiert auf demselben physikalischen Prinzip:
Eine elektromagnetische Welle wird ausgesendet und reflektiert.
Aus der **Laufzeit** → Entfernung,
aus der **Frequenzverschiebung (Doppler)** → Geschwindigkeit.

$f_D = \frac{2v}{\lambda}$

**Beispiel:**
Ein Auto mit 100 km/h (~27,8 m/s) und $\lambda$ = 3 cm → Doppler-Verschiebung $\approx$ 1,85 kHz.

---

### Beispielhafte Prüfungsfrage (im Stil des Professors)

> **Frage:**
> „Erklären Sie, was unter Mehrwegeausbreitung zu verstehen ist und welche Probleme sie verursacht.
> Nennen Sie zwei technische Verfahren, mit denen diese Effekte reduziert oder genutzt werden können, und erläutern Sie kurz deren Funktionsweise.“

---

### Musterlösung

**1. Definition:**
Mehrwegeausbreitung beschreibt das Phänomen, dass ein Funksignal über mehrere verschiedene Wege (direkt, reflektiert, gebeugt) zum Empfänger gelangt.
Die Signalanteile treffen zeitlich und phasenverschoben ein, wodurch Interferenzen entstehen.

**2. Problem:**
Die überlagerten Wellen können sich gegenseitig verstärken oder auslöschen → Fading.
Das führt zu schwankender Signalstärke und höheren Bitfehlern, besonders bei Bewegung oder Reflexion an Gebäuden.

**3. Gegenmaßnahmen / Nutzung:**

* **Diversity-Verfahren:** mehrere Antennen (Raumdiversität) → Empfänger wählt den besten Signalpfad aus.
* **OFDM:** verteilt das Signal auf viele schmale Frequenzbänder → Mehrwege erzeugen nur Phasenverschiebungen, keine symbolübergreifenden Fehler.
* **MIMO:** nutzt Mehrwege gezielt, um mehrere Datenströme gleichzeitig zu übertragen.

**4. Beispiel:**
WLAN mit 2x2 MIMO kann bei gleichem Frequenzband doppelte Datenrate erreichen, weil es zwei unabhängige Übertragungspfade (durch Reflexionen) nutzt.
So wird Mehrwegeausbreitung nicht bekämpft, sondern ausgenutzt.

---

### Lernnotizen & Merksätze

**Merksätze:**

* „Jede Reflexion ist ein neuer Weg – nützlich oder störend.“
* „Fading = Signal tanzt im Raum – manchmal laut, manchmal leise.“
* „Diversity rettet das Signal, MIMO macht es doppelt so schnell.“
* „Beamforming ist gerichtetes Hören – der Empfänger schaut dahin, wo das Signal herkommt.“
* „Radar misst die Zeit, Doppler die Geschwindigkeit.“

**Kernaussagen:**

* Mehrwegeausbreitung ist unvermeidlich – entscheidend ist, **wie man damit umgeht.**
* Diversity → Zuverlässigkeit, MIMO → Datenrate.
* Antennenarrays und Beamforming → gezielte Richtwirkung, höhere Effizienz.
* In allen modernen Funksystemen (LTE, 5G, WLAN) sind diese Konzepte integriert.

**Übungsaufgaben:**

1. Beschreibe, warum in einem WLAN-Signal die Empfangsstärke stark schwanken kann, wenn man sich im Raum bewegt.
2. Ein 5G-System nutzt 4x4 MIMO. Wie viele unabhängige Datenströme können gleichzeitig übertragen werden?
3. Erkläre den Unterschied zwischen Diversity und MIMO in einem Satz.
4. Welche Rolle spielt der Dopplereffekt bei der Geschwindigkeitsmessung eines Radars?
5. Skizziere eine Situation, in der Mehrwegeausbreitung sowohl nützlich als auch problematisch ist.
