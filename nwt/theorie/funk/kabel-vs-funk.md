
## Thema: Kabel vs. Funk – Shared Media, CSMA/CA & Frequenzregulierung

### Ausführliche Zusammenfassung

Der Professor betonte in der Besprechung, dass sich **Kabel-** und **Funkübertragungen** nicht nur technisch, sondern auch **rechtlich und organisatorisch** grundlegend unterscheiden.
Beide Systeme übertragen dieselben Arten von Datenpaketen, doch die Umgebung und die Art, wie mehrere Teilnehmer das Medium nutzen, sind völlig verschieden.
Diese Unterschiede sind entscheidend für den Entwurf von Protokollen (z. B. Ethernet vs. WLAN) und für den Zugriff auf Frequenzen.

---

### 1. **Unterschied: Privates vs. gemeinsames Übertragungsmedium**

#### a) **Kabelnetze**

* Physisches Medium (z. B. Kupfer, Glasfaser) gehört meist **dem Betreiber oder Nutzer** selbst.
* Zugriff kann kontrolliert werden – typischerweise Punkt-zu-Punkt oder Segment-basierte Netze.
* Beispiel: Ethernet-Kabel, Glasfaserleitungen, DSL.
* **Eigentumsrechtlich privat**: Niemand außer dem Eigentümer darf das Signal einspeisen.
* Keine staatliche Frequenzregulierung notwendig, solange keine Abstrahlung erfolgt.

#### b) **Funknetze**

* Luft ist ein **gemeinsames, öffentliches Medium** – niemand „besitzt“ die Funkfrequenz.
* Daher wird das Spektrum von Behörden (in Österreich z. B. RTR – *Rundfunk & Telekom Regulierungs-GmbH*) **koordiniert**.
* Jeder darf prinzipiell funken, **aber nur innerhalb genehmigter Frequenzbänder** und mit bestimmten Leistungsgrenzen.
* Beispiele:

  * WLAN → ISM-Bänder (2,4 GHz, 5 GHz)
  * Mobilfunk → lizenzierte Bänder (z. B. 700 MHz, 3,6 GHz)
  * Polizei, Rettung, Flugfunk → exklusive Zuteilung

> Der Professor meinte:
> „Im Kabel gehört das Medium Ihnen, im Funk gehört es uns allen – und genau das macht Funk so viel schwieriger.“

---

### 2. **Shared Media & Zugriffsverfahren**

Da beim Funk viele Geräte gleichzeitig denselben Frequenzbereich verwenden, muss geregelt werden, **wer wann senden darf**.
Hier kommen **Zugriffsverfahren (MAC-Methoden)** ins Spiel.

#### a) **Ethernet (Kabel) – CSMA/CD**

* **Carrier Sense Multiple Access / Collision Detection**
* Alle Geräte hören, ob das Medium frei ist („Carrier Sense“).
* Wenn frei → senden.
* Wenn zwei gleichzeitig senden → Kollision erkannt (Collision Detection).
* Beide stoppen und senden nach Zufallszeit neu.
* Funktioniert, weil Kollisionen im Kabel messbar sind (durch Spannungspegel).

#### b) **WLAN (Funk) – CSMA/CA**

* **Carrier Sense Multiple Access / Collision Avoidance**
* Geräte hören ebenfalls, ob der Kanal frei ist.
* Da man im Funk aber nicht immer erkennen kann, ob ein anderer gerade sendet (z. B. verdeckte Stationen), wird **Kollisionserkennung durch Vermeidung ersetzt.**
* Sender „fragt an“, bevor er sendet (RTS/CTS – *Request to Send / Clear to Send*).
* Empfänger bestätigt, wann gesendet werden darf.
* Sollen Kollisionen **vorher** vermieden werden, nicht erst erkannt.

> Professor-Kommentar:
> „Funk ist wie Reden in einem dunklen Raum – man hört, wenn’s ruhig ist, aber man weiß nicht, ob gerade wer in der Ecke flüstert. Deshalb fragt WLAN vorher höflich: ‚Darf ich jetzt?‘“

---

### 3. **Frequenznutzung & Regulierung**

#### a) **Regulierungsbehörde (RTR in Österreich)**

* Legt fest, **welche Frequenzen** für welche Anwendungen genutzt werden dürfen.
* Unterscheidet zwischen:

  * **Lizenzpflichtigen Bändern** (z. B. Mobilfunk, Flugfunk, Behördenfunk)
  * **Lizenzfreien ISM-Bändern** (Industrial, Scientific, Medical) → z. B. WLAN 2,4 GHz

#### b) **Ziel der Regulierung**

* Vermeidung von Störungen zwischen Systemen.
* Gewährleistung sicherer Dienste (z. B. Notruf, Luftfahrt).
* Koordinierung zwischen Ländern (ITU).

#### c) **Leistungsbeschränkungen**

* In lizenzfreien Bändern sind Sendeleistungen begrenzt, z. B.:

  * 2,4 GHz WLAN: max. 100 mW (20 dBm)
  * 5 GHz WLAN: teils 200 mW, aber mit „DFS“ (Radar-Erkennung)

→ Zweck: Niemand darf den gemeinsamen Äther „überstrahlen“.

---

### 4. **Vergleich – Kabel vs. Funk**

| Merkmal             | Kabel               | Funk                                     |
| ------------------- | ------------------- | ---------------------------------------- |
| Eigentum            | privat              | öffentlich                               |
| Kollisionserkennung | möglich (CSMA/CD)   | nicht möglich (nur Vermeidung – CSMA/CA) |
| Dämpfung            | berechenbar, gering | stark abhängig von Umgebung              |
| Sicherheit          | physisch begrenzt   | offen, abhörbar                          |
| Bandbreite          | hoch, stabil        | schwankend                               |
| Regulierung         | kaum nötig          | gesetzlich geregelt (RTR, ITU)           |

---

### 5. **Shared Media und Netzdesign**

In gemeinsam genutzten Medien (Shared Media) entsteht eine Konkurrenzsituation:
Mehr Teilnehmer = geringere verfügbare Datenrate pro Nutzer.
Deshalb werden Verfahren wie:

* **Channel Bonding** (mehrere Frequenzkanäle bündeln),
* **QoS** (Quality of Service – Priorisierung bestimmter Datenströme), und
* **Raumaufteilung (Cell Splitting)** eingesetzt, um die Effizienz zu erhöhen.

> Beispiel des Professors:
> „Wenn alle im selben WLAN sind, wird’s eng. Das ist wie bei einer Party – je mehr Leute reden, desto weniger versteht man. Deshalb teilt man den Raum oder gibt wichtigen Gästen (Rettungsdiensten, Video-Streams) Vorrang.“

---

### Beispielhafte Prüfungsfrage (im Stil des Professors)

> **Frage:**
> „Erklären Sie den Unterschied zwischen CSMA/CD und CSMA/CA.
> Warum ist eine echte Kollisionserkennung im WLAN nicht möglich, und welche Rolle spielt die RTR bei der Nutzung von WLAN-Frequenzen?“

---

### Musterlösung

**1. Unterschied CSMA/CD vs. CSMA/CA**

| Aspekt                 | CSMA/CD (Ethernet)                        | CSMA/CA (WLAN)                                                    |
| ---------------------- | ----------------------------------------- | ----------------------------------------------------------------- |
| Medium                 | Kabel                                     | Funk                                                              |
| Mechanismus            | Kollisionen **erkennen**                  | Kollisionen **vermeiden**                                         |
| Vorgehen               | Senden, Lauschen, Abbruch bei Kollision   | Abwarten, RTS/CTS-Anfrage, dann Senden                            |
| Reaktion auf Kollision | Sofortige Neuübertragung nach Zufallszeit | Übertragung erst, wenn Kanal bestätigt frei                       |
| Grund                  | Spannungspegel messbar                    | Kein gleichzeitiges Senden & Empfangen auf gleichem Kanal möglich |

**2. Warum keine Kollisionserkennung im WLAN möglich?**

* Funkgeräte können nicht gleichzeitig senden und empfangen → sie würden ihre eigene Aussendung „überhören“.
* Außerdem können verdeckte Stationen existieren: zwei Clients hören sich nicht gegenseitig, aber stören denselben Access Point.
  → Daher nur **Collision Avoidance (CA)** möglich.

**3. Rolle der RTR:**

* RTR regelt die Zuteilung und Nutzung von Frequenzen in Österreich.
* Legt fest, welche Bänder lizenzfrei sind (z. B. 2,4 GHz WLAN) und welche nicht.
* Definiert Leistungsgrenzen, Kanäle und Bedingungen (z. B. DFS).
* Ziel: Interferenzfreiheit und faire Nutzung des Frequenzspektrums.

---

### Lernnotizen & Merksätze

**Merksätze:**

* „Im Kabel kann man Kollisionen hören, im Funk muss man sie vermeiden.“
* „CSMA/CD: zuhören – reden – stoppen; CSMA/CA: fragen – warten – senden.“
* „Funk gehört allen, Kabel gehört jemandem.“
* „RTR bestimmt, wer wo reden darf – sonst herrscht Chaos im Äther.“

**Kernaussagen:**

* Funk ist ein Shared Medium → Zugriff muss geregelt werden.
* CSMA/CA ersetzt Kollisionserkennung durch Prävention.
* Frequenzen werden staatlich reguliert; unregulierte Nutzung würde zu Störungen führen.
* Lizenzfreie Bänder sind begrenzt und stark frequentiert.

**Übungsaufgaben:**

1. Warum kann ein WLAN-Client während des Sendens kein fremdes Signal erkennen?
2. Erkläre, was im WLAN passiert, wenn zwei Clients gleichzeitig „RTS“ senden.
3. Nenne zwei Vorteile von Funkübertragung gegenüber Kabel und zwei Nachteile.
4. Welche Konsequenz hätte es, wenn die Frequenzregulierung (z. B. durch RTR) aufgehoben würde?
