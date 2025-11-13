
# Modulationsarten – Information auf Träger aufbringen

## Ausführliche Zusammenfassung

Der Professor erklärte, dass **Modulation** im Kern immer bedeutet,
eine **Information** (Sprache, Musik, Daten) auf eine **hochfrequente
Trägerschwingung** aufzubringen. Diese Trägerschwingung dient als
„Transportmittel“, um das Signal über größere Entfernungen zu
senden, während das ursprüngliche Informationssignal (z. B.
Sprache mit 3 kHz Bandbreite) allein nicht weit kommen würde.

---

## 1. Warum überhaupt Modulation?

Unmodulierte Signale mit niedriger Frequenz (z. B. Audiosignale)
könnten keine brauchbare Antenne nutzen:
- Eine Antenne ist nur effizient, wenn ihre Länge in der
  Größenordnung einer halben Wellenlänge liegt.
- Ein 3 kHz-Signal hätte eine Wellenlänge von etwa 100 km –
  völlig unpraktisch.

Deshalb wird das Signal auf eine hohe Trägerfrequenz „gehoben“,
z. B. 100 MHz beim UKW-Rundfunk.

Dadurch:

- wird die Antenne technisch realisierbar,
- lassen sich viele Sender durch Frequenztrennung unterscheiden,
- kann man das Signal besser filtern und verstärken.

---

## 2. Analoge Modulationsarten

Bei analogen Modulationen wird ein kontinuierliches Signal auf
den Träger aufgebracht.

### a) Amplitudenmodulation (AM)

- Die **Amplitude** der Trägerschwingung wird proportional zur
  Nachricht verändert.
- Trägerfrequenz bleibt konstant, nur ihre Stäkr schwankt.

Formelhaft: $s(t) = [1 + m(t)] \cdot \cos(\omega_c t)$

**Eigenschaften**:

- Einfach zu erzeugen und zu empfangen.
- Störanfälliger gegen Rauschen (weil Störungen ebenfalls die Amplitude verändern).
- Geringer Wirkungsgrad (viel Energie im Träger).

**Beispiel**: Mittelwellen- und Langwellenrundfunk.

Der Professor kommentierte:

"Die Amplitudenmodulation ist technisch simpel, aber in einer
lauten Umgebung ineffizient - jedes Rauschen ändert sofort die
Signalstärke."

---

### b) Frequenzmodulation (FM)

- Hier wird die **Frequenz** des Trägers verändert, abhängig vom
  Nachrichtensignal.
- Die Amplitude bleibt konstant.
- Informationsgehalt steckt in den **Frequenzabweichungen**.

**Eigenschaften**:

- Deutlich robuster gegen Störungen, weil Rauschen vor allem die Amplitude
  betrifft.
- Höherer Bandbreitenbedarf.
- Besseres Signal-to-Noise-Ratio bei schwachem Empfang.

**Beispiel**:

„Wenn Sie ein Autoradio hören und das Signal leicht verrauscht,
merken Sie, dass FM trotzdem noch klar bleibt – das ist der
Vorteil dieser Modulationsart.“

---

### c) Phasenmodulation (PM)

- Die **Phase** der Trägerschwingung wird in Abhängigkeit vom Nachrichtensignal
  verändert.
- Eng verwandt mit FM, da Frequenz = zeitliche Ableitung der Phase.

**Eigenschaften**:

- Wird meist in digitalen Systemen genutzt (z.B. PSK).
- Analoge PM ist selten

---

## 3. Digitale Modulationsarten

Bei digitalen Verfahren werden **diskrete Symbole** (0, 1 oder
Symbolmuster) auf den Träger codiert. Diese Verfahren sind die
Grundlage aller modernen Systeme (WLAN, LTE, 5G).

### a) ASK (Amplitude Shift Keying)

- Digitale Version vom A:: Träger ist an ("1") oder aus ("0).
- Einfach, aber sehr störanfällig gegen Amplitudenrauschen.

### b) FSK (Frequency Shift Keying)

- Digitale Version von FM: Zwei (oder mehrere) Frequenzen repräsentierten Bitzustände.
- Robust, weit verbreitet in Funkfernbedienungen, alten Modems, RFID.

### c) PSK (Phase SHift Keying)

- Die Phase der Trägerschwingung wird in diskreten Stufen
  geändert.
- **BPSK**: 0° = Bit 0, 180° = Bit 1
- **QPSK**: vier Phasen (00, 01, 10, 11).
- Sehr effizient, relativ robust.

### d) QAM (Quadrature Amplitude Modulation)

- Kombination aus Amplituden- und Phasenänderung.
- Zwei Träger (Quadratur = 90° Phasenversatz) werden überlagert.
- Ermöglicht viele Zustände pro Symbol: 16-QAM, 64-QAM; 256-QAM etc.
- Höhere Datenrate, aber empfindlicher gegen Rauschen.

Der Professor erwähnte: "QAM ist im Prinzip wie zwei PSK-Signale, die um 90
Grad verschoben gleichzeitig gesendet werden - mehr Information pro Symbol,
aber mehr Empfindlichkeit gegenüber Störungen."

### e) OFDM (Orthogonal Frequency Division Multiplexing)

- Statt ein Signal zu modulieren, werden **viele schmale Träger gleichzeitig**
  genutzt, die zueinander orthogonal sind.
- Jedes Teilband überträgt einen Teil der Daten (z.B. per QAM).
- Vorteile: robust gegen Mehrwegeausbreitung, effizient in Frequenznutzung.
- Wird in allen modernen Standards eingesetzt: WLAN, LTE, 5G, DVB-T

**Warum robust?** Jede Subträgerfrequenz ist langsam genug, dass
Mehrwege-Echos nur Phasenverschiebungen erzeugen, keine
kompletten Auslöschungen.

---

## 4. Vergleich - analoge vs. digitale Modulation

| Kriterium   | Analoge Modulation      | Digitale Modulation            |
| ----------- | ----------------------- | ------------------------------ |
| Signalart   | kontinuierlich          | diskret                        |
| Robustheit  | gering (Rauschanfällig) | hoch (Fehlerkorrektur möglich) |
| Bandbreite  | kleiner                 | größer                         |
| Komplexität | einfach                 | höher                          |
| Beispiele   | AM, FM, PM              | FSK, PSK, QAM, OFDM            |

---

## Beispielhafte Prüfungsfrage

**Frage:** "Vergleichen Sie AM, FM und QAM in Hinblick auf
Robustheit gegen Störungen, Bandbreite und Datenrate. Erklkären
Sie außerdem kurz, warum OFDM in mordernen WLAN-Systemen
verwendet wird."

### Vergleich der Verfahren

| Merkmal            | AM                          | FM                          | QAM                                       |
| ------------------ | --------------------------- | --------------------------- | ----------------------------------------- |
| Was wird variiert? | Amplitude                   | Frequenz                    | Amplitude und Phase                       |
| Störanfälligkeit   | hoch (Rauschen = Amplitude) | gering (Amplitude konstant) | mittel - abhänig von Störabstand          |
| Bandbreite         | gering                      | größer (Frequenzhub)        | variabel, abhängig von Modulationsordnung |
| Datenrate          | niedrig                     | moderat                     | hoch (mehr Bits/Symbol)                   |
| Empfängeraufwand   | gering                      | mittel                      | hoch (I/Q-Demodulation)                   |

### Warum OFDM?

- Teilt das Spektrum in viele schmale, orthogonale Unterträger.
- Jeder Unterträger wird langsam moduliert (z.B. mit QAM).
- Mehrwegausbreitung führt nur zu unterschiedlichen Laufzeiten, die im
  Empfänger korrigiert werden (per FFT).
- Hohe spektrale Effizienz, da Träger überlappen dürfen, ohne sich zu stören.

**Beispiel**: In WLAN 802.11 n (2,4 GHz) nutzt man 64 Subträger,
davon 52 für Daten. Bei 64-QAM → 6 Bits/Symbol × 52 = 312 Bits
pro OFDM-Symbol.

---

## Lernnotizen & Merksätze

**Merksätze**:

- "Modulation = Information auf einen Träger setzen."
- "AM ändert die Höhe, FM die Geschwindigkeit, PM die Phase der Schwingung."
- "QAM = zwe PSK-Signale in Quadratur → mehr Bits pro Symbol."
- "OFDM nutzt viele Träger gleichzeitig, um Echos zu tolerieren."

**Kernaussagen:**

- Analoge Verfahren → einfach, aber anfällig
- Digitale Verfahren → komplex, aber effizient und fehlerkorrigierbar.
- Modulationsordnung (z.B. 16-QAM vs. 64-QAM) bestimmt Bits pro Symbol → mehr
  Datenrate, aber höherer SNR-Bedarf.

**Übungsaufgaben**

1. Zeichne das Zeit- und Spektraldiagramm einer AM- und FM-Schwingung.
2. Berechne die erforderliche Bandbreite für ein FM-Signal mit ±75 kHz Hub und
   15 kHz Audiofrequenz (Car- son-Regel).
3. Wie viele Bits pro Symbol trägt ein 64-QAM-Signal?
4. Warum ist OFDM bei WLAN robuster gegen Reflexionen als eine einfache
   QAM-Modulation?
