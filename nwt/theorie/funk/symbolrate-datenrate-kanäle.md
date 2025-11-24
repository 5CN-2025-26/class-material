
---

## Thema: Symbolrate, Datenrate & Kanäle – Grundlagen moderner Datenübertragung

### Ausführliche Zusammenfassung

Der Professor betonte, dass viele Studierende Begriffe wie *Bitrate*, *Symbolrate* und *Kanal* durcheinanderbringen, obwohl sie unterschiedliche physikalische Bedeutungen haben.
Um ein Funk- oder Kabelsystem zu verstehen, muss man wissen, **wie Information im Zeit- und Frequenzbereich verteilt** wird und **was die tatsächliche Datenrate begrenzt**.

---

### 1. **Begriffe & Zusammenhänge**

#### a) **Bitrate (R<sub>b</sub>)**

Die Bitrate gibt an, wie viele **Bits pro Sekunde** übertragen werden.
Beispiel: Ein Datenstrom mit 1 Mbit/s überträgt 1 Million Bits pro Sekunde.

#### b) **Symbolrate (R<sub>s</sub>)**

Die Symbolrate (auch Baudrate) beschreibt, wie viele **Symbole pro Sekunde** gesendet werden.
Ein Symbol kann **mehrere Bits** darstellen – abhängig von der Modulationsart.

Formelbeziehung:
$R_b = R_s \times \text{Bits pro Symbol}$

**Beispiel:**
Bei 16-QAM werden 16 Symbole codiert → 4 Bits pro Symbol.
Wenn 1 000 Symbole/s gesendet werden:

$R_b = 1 000 \times 4 = 4 000 \text{ Bit/s}$

→ **Die Bitrate kann höher sein als die Symbolrate.**

Der Professor sagte dazu:

> „Viele glauben, mehr Bits pro Sekunde heißt, man sendet schneller.
> Nein — man sendet *mehr Information pro Symbol*. Die Symbolrate ist oft physikalisch limitiert durch Bandbreite.“

---

### 2. **Physikalische Grenzen: Bandbreite & Nyquist-Kriterium**

Die maximale Symbolrate hängt direkt von der **Bandbreite des Kanals** ab.
Nach dem **Nyquist-Kriterium** gilt:

$R_s \leq 2B$

* (B): nutzbare Bandbreite des Übertragungskanals
* (R_s): maximal übertragbare Symbolrate (ohne Inter-Symbol-Interferenz)

**Interpretation:**
Ein Kanal mit 10 MHz Bandbreite kann maximal 20 Mbaud Symbolrate übertragen.
Die tatsächliche Bitrate hängt dann vom Modulationsschema ab.

> Beispiel des Professors:
> „Wenn Sie WLAN mit 20 MHz Bandbreite haben, können Sie vielleicht 10 bis 12 Mbaud Symbole unterbringen. Wenn jedes Symbol 6 Bit trägt (64-QAM), ergibt das 60–70 Mbit/s brutto.“

---

### 3. **Kanäle & Multiplexing**

#### a) **Physikalischer Kanal**

* Ein einzelner Übertragungsweg für elektromagnetische Signale (z. B. Frequenzband, Kabel, Antenne).
* In Funknetzen ist er durch Frequenz, Raum und Polarisation definiert.

#### b) **Logischer Kanal**

* Virtuelle Unterteilung eines physikalischen Mediums.
* Wird über Multiplexverfahren realisiert:

  * **Frequenzmultiplex (FDM):** verschiedene Signale → verschiedene Frequenzbereiche
  * **Zeitmultiplex (TDM):** Signale teilen sich denselben Kanal zeitlich
  * **Codemultiplex (CDM):** Signale überlagern sich, werden durch unterschiedliche Codes getrennt
  * **Raummultiplex (MIMO):** mehrere Antennen → parallele Übertragungswege

> Der Professor sagte:
> „Ein Kanal kann gleichzeitig physisch und logisch sein. Im WLAN haben Sie z. B. 20 MHz physisch, aber viele logische Verbindungen gleichzeitig — das ist Multiplexing.“

---

### 4. **Multiplexing-Methoden im Überblick**

| Verfahren                              | Prinzip                                         | Beispiel         |
| -------------------------------------- | ----------------------------------------------- | ---------------- |
| **FDM (Frequency Division Multiplex)** | Aufteilung nach Frequenzen                      | UKW, Kabel-TV    |
| **TDM (Time Division Multiplex)**      | Aufteilung nach Zeitfenstern                    | GSM, Ethernet    |
| **CDM (Code Division Multiplex)**      | Aufteilung nach Signalcodes                     | UMTS, GPS        |
| **SDM (Space Division Multiplex)**     | Nutzung mehrerer Antennenpfade                  | WLAN MIMO, 5G    |
| **OFDM (Orthogonal FDM)**              | Spezielle Form von FDM mit orthogonalen Trägern | WLAN, LTE, DVB-T |

---

### 5. **Beispiel: WLAN-Kanalstruktur**

Bei 802.11n (2,4 GHz):

* Kanalbreite = 20 MHz
* 64 Subträger (davon 52 aktiv)
* Symbolrate = 250 kSym/s
* Modulation: 64-QAM → 6 Bit/Symbol
  → Bruttorate = 250 000 × 6 × 52 = **78 Mbit/s**

> „Wenn man dann MIMO nutzt, verdoppelt oder verdreifacht man die effektive Rate, weil man mehrere physikalische Pfade gleichzeitig benutzt“, erklärte der Professor.

---

### 6. **Mehrkanalsysteme – MIMO (Multiple Input Multiple Output)**

MIMO nutzt mehrere Sende- und Empfangsantennen, um parallele Datenströme zu übertragen.
Die Idee: Jeder Antennenpfad hat eine leicht unterschiedliche Ausbreitung (wegen Reflexionen etc.), was als unabhängiger Übertragungskanal genutzt werden kann.

**Vorteile:**

* Höhere Datenrate (räumliches Multiplexing)
* Höhere Zuverlässigkeit (Diversity-Effekt)
* Bessere Ausnutzung von Mehrwegeausbreitung

**Beispiel:**
WLAN 802.11n mit 2x2 MIMO → 2 parallele Streams à 78 Mbit/s → **156 Mbit/s Brutto**.

---

### Beispielhafte Prüfungsfrage (im Stil des Professors)

> **Frage:**
> „Ein WLAN-System sendet 500 000 Symbole pro Sekunde mit 64-QAM über zwei MIMO-Kanäle.
> Berechnen Sie die Bitrate und erklären Sie, warum die Symbolrate nicht einfach beliebig erhöht werden kann.“

---

### Musterlösung

**1. Gegebene Werte:**

* Symbolrate (R_s = 500 000 \text{Symbole/s})
* Modulation = 64-QAM → 6 Bit/Symbol
* MIMO = 2 parallele Kanäle

**2. Berechnung der Bitrate:**

$R_b = R_s \times \text{Bits/Symbol} \times \text{Kanäle}$

$R_b = 500 000 \times 6 \times 2 = 6 000 000 \text{Bit/s} = 6 Mbit/s$

**3. Warum Symbolrate begrenzt ist:**
Die Symbolrate hängt direkt von der **Bandbreite des Kanals** ab.
Nach Nyquist kann maximal (R_s = 2B) übertragen werden.
Erhöht man die Symbolrate über diesen Wert, entsteht **Inter-Symbol-Interferenz (ISI)** — die Symbole überlappen sich und sind nicht mehr eindeutig unterscheidbar.

**4. Alternativen zur Steigerung der Datenrate:**

* Höhere Modulationsordnung (mehr Bits/Symbol, z. B. 256-QAM)
* Mehr physikalische Kanäle (MIMO, Channel Bonding)
* Größere Bandbreite (z. B. 40 MHz statt 20 MHz bei WLAN)
* Verbesserte Codierung & Fehlerkorrektur (FEC)

---

### Lernnotizen & Merksätze

**Merksätze:**

* „Symbolrate = wie oft gesendet wird, Bitrate = wie viel pro Symbol drinsteckt.“
* „Mehr Bits pro Symbol = höhere Datenrate, aber empfindlicher gegen Störungen.“
* „Bandbreite begrenzt Symbolrate – nicht der Prozessor!“
* „MIMO nutzt den Raum als zusätzlichen Kanal.“
* „OFDM = viele kleine Symbole gleichzeitig, MIMO = viele gleiche Symbole parallel.“

**Kernaussagen:**

* Symbolrate hängt von der physikalischen Kanalbandbreite ab.
* Datenrate = Symbolrate × Bits/Symbol × Kanäle.
* Multiplexing und MIMO ermöglichen höhere Datenraten ohne Erhöhung der Symbolrate.

**Übungsaufgaben:**

1. Ein LTE-System hat 10 MHz Bandbreite, nutzt 64-QAM und 4x4 MIMO.
   → Wie hoch ist die theoretische Bruttodatenrate bei 500 000 Symbolen/s?
2. Erkläre den Unterschied zwischen Frequenz- und Zeitmultiplexing anhand eines praktischen Beispiels (z. B. Radio vs. GSM).
3. Warum wird OFDM mit MIMO kombiniert, obwohl beide bereits Multiplexing nutzen?
4. Skizziere, wie sich die Bitrate verändert, wenn man von 16-QAM auf 64-QAM wechselt, bei gleicher Symbolrate.

---
