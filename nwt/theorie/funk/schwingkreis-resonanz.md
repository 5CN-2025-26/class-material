

## Thema: Schwingkreis & Resonanz – Der einfachste Sender

### Ausführliche Zusammenfassung

Der Professor erklärte in der Besprechung, dass der **einfachste mögliche Sender** im Grunde nichts anderes ist als ein **elektrischer Schwingkreis**, der eine **resonante Schwingung** erzeugt. Diese Schwingung lässt sich dann über eine Antenne abstrahlen. Das Prinzip ist elementar für alle Hochfrequenzsysteme – egal ob Rundfunk, WLAN, Mobilfunk oder Radar.

---

### 1. **Grundprinzip des Schwingkreises**

Ein Schwingkreis besteht aus:

* einer **Induktivität (L)**, meist eine Spule, und
* einem **Kondensator (C)**, der elektrische Energie speichert.

Diese beiden Bauteile bilden gemeinsam ein System, das elektrische Energie in magnetische und elektrische Energie umwandelt – und zwar **periodisch**, also in Schwingung.
Der Schwingkreis ist somit das elektrische Analogon eines Pendels.

#### Funktionsweise:

1. Der Kondensator wird aufgeladen (z. B. durch eine Spannungsquelle).
2. Wird er entladen, fließt Strom durch die Spule.
3. In der Spule entsteht ein Magnetfeld, das Energie speichert.
4. Wenn das Magnetfeld zusammenbricht, lädt es den Kondensator mit umgekehrter Polarität wieder auf.
5. Dieser Prozess wiederholt sich periodisch – eine **Schwingung** entsteht.

---

### 2. **Resonanzbedingung**

Bei einem idealen, ungedämpften Schwingkreis gilt:

$\omega_0 = \frac{1}{\sqrt{LC}}$

oder als Frequenz:

$f_0 = \frac{1}{2\pi \sqrt{LC}}$

Das ist die **Resonanzfrequenz**.
Hier gleichen sich die Blindwiderstände von Spule und Kondensator genau aus:

$X_L = X_C \quad \Rightarrow \quad \omega L = \frac{1}{\omega C}$


→ Das bedeutet: Die Impedanz des Schwingkreises ist minimal (Serienschwingkreis) bzw. maximal (Parallelschwingkreis). Nur bei dieser Frequenz schwingt das System „von selbst“.

---

### 3. **Dämpfung & Verluste**

In der Realität gibt es Widerstände (R), z. B. im Draht oder durch Strahlungsverluste.
Deshalb ist jeder reale Schwingkreis **gedämpft** – die Schwingung klingt ab, wenn keine Energie nachgeliefert wird.

Das Maß dafür ist der **Gütefaktor (Q)**:

$Q = \frac{\omega_0 L}{R}$

Hoher Q-Faktor → geringe Verluste → schmalbandige Resonanz.
Niedriger Q-Faktor → hohe Verluste → breitbandige Resonanz.

---

### 4. **Der Schwingkreis als Sender**

Wenn man dem Schwingkreis regelmäßig Energie zuführt (z. B. durch einen Verstärker oder Transistor), kann er **dauerhaft schwingen**.
Diese Schwingung wird dann über eine Antenne **abgestrahlt** – das ist die Grundidee jedes Senders.

* Der Schwingkreis bestimmt die **Trägerfrequenz**.
* Die Antenne wandelt die Schwingung in elektromagnetische Wellen um.
* Eine Modulation (z. B. AM, FM, PM) überlagert Information auf diese Schwingung.

> Der Professor sagte sinngemäß:
> „Wenn Sie verstehen, dass jeder Sender im Kern nur ein resonanter Schwingkreis ist, haben Sie 80 % der Grundlagen der Funktechnik verstanden.“

---

### 5. **Serien- vs. Parallelschwingkreis**

| Eigenschaft                   | Serienschwingkreis         | Parallelschwingkreis                     |
| ----------------------------- | -------------------------- | ---------------------------------------- |
| Aufbau                        | L und C in Serie           | L und C parallel                         |
| Resonanzimpedanz              | Minimum                    | Maximum                                  |
| Strom / Spannung bei Resonanz | Strom maximal              | Spannung maximal                         |
| Anwendung                     | z. B. Oszillatoren, Filter | z. B. Empfangsfilter, Antennenabstimmung |

In Sendern werden beide Varianten eingesetzt:

* **Serienschwingkreis** im Oszillator zur Erzeugung der Trägerschwingung
* **Parallelschwingkreis** in der Antennenanpassung oder im Empfänger zur Filterung

---

### 6. **Physikalische Analogie: Mechanischer Schwinger**

Der Professor nutzte zur Erklärung das Beispiel eines **mechanischen Pendels**:

* Die Masse entspricht der **Induktivität L** (trägt Energie in Bewegung).
* Die Feder entspricht dem **Kondensator C** (trägt Energie im elektrischen Feld).
* Der Luftwiderstand entspricht dem **Widerstand R** (Dämpfung).

Wird das Pendel angestoßen (Energieeinspeisung), schwingt es um seine Ruhelage – genau wie der Strom im Schwingkreis um den Gleichgewichtszustand.

---

### Beispielhafte Prüfungsfrage (im Stil des Professors)

> **Frage:**
> „Erklären Sie, warum ein einfacher Schwingkreis als Sender betrachtet werden kann.
> Welche physikalische Bedeutung hat die Resonanzfrequenz, und wie beeinflussen L und C diese?
> Geben Sie ein Beispiel, wie man mit praktischen Werten (L = 10 µH, C = 100 pF) die Sendefrequenz abschätzen kann.“

---

### Musterlösung

**1. Warum Schwingkreis = Sender:**
Ein Schwingkreis (L + C) erzeugt elektrische Schwingungen durch Energieaustausch zwischen Magnetfeld (Spule) und elektrischem Feld (Kondensator).
Wenn diese Schwingungen über eine Antenne geleitet werden, entstehen elektromagnetische Wellen – genau das tut ein Sender.
→ Der Schwingkreis bestimmt die Frequenz, die Antenne strahlt sie ab.

**2. Bedeutung der Resonanzfrequenz:**
Die Resonanzfrequenz ist die natürliche Eigenfrequenz, bei der das System ohne äußeren Antrieb schwingt.
Hier sind induktiver und kapazitiver Blindwiderstand gleich groß, aber entgegengesetzt:

$X_L = X_C \Rightarrow \omega_0 = \frac{1}{\sqrt{LC}}$

Das System benötigt die geringste Energie, um in Resonanz zu bleiben.

**3. Einfluss von L und C:**

* Erhöhung von L oder C → niedrigere Frequenz (langsamere Schwingung).
* Verringerung von L oder C → höhere Frequenz (schnellere Schwingung).
  Physikalisch: größere Spule oder größerer Kondensator = „träge“, daher tiefere Frequenz.

**4. Beispielrechnung:**

$f_0 = \frac{1}{2\pi\sqrt{LC}} = \frac{1}{2\pi\sqrt{10\cdot10^{-6} \cdot 100\cdot10^{-12}}}$


$= \frac{1}{2\pi\sqrt{10^{-15}}} \approx \frac{1}{2\pi\cdot3,16\cdot10^{-8}} \approx 5,0 \text{ MHz}$


→ Die Schaltung würde also auf etwa **5 MHz** schwingen – im Kurzwellenbereich.

**5. Zusatz: Dämpfung**
Wird der Schwingkreis nicht nachgespeist, klingt die Schwingung ab.
Deshalb nutzt man Verstärker (z. B. Transistor oder Röhre), um die Energieverluste auszugleichen → **Oszillator** entsteht → Basis eines Senders.

---

### Lernnotizen & Merksätze

**Merksätze:**

* „Jeder Sender ist nur ein Schwingkreis, der Energie verliert und nachgefüttert wird.“
* „Großes L oder C → tiefe Frequenz, kleines L oder C → hohe Frequenz.“
* „Resonanz = Blindanteile heben sich auf, Energie pendelt verlustfrei hin und her.“
* „Dämpfung tötet die Schwingung – Verstärkung hält sie am Leben.“

**Kurzformeln:**

$f_0 = \frac{1}{2\pi\sqrt{LC}}, \quad Q = \frac{\omega_0 L}{R}$


**Übungsaufgaben:**

1. Berechne $(f_0)$ für $L = 1 µH, C = 10 pF$.
2. Was passiert mit der Frequenz, wenn man C verdoppelt?
3. Welche Bauelemente beeinflussen die Güte des Schwingkreises am stärksten?
4. Skizziere Spannung und Strom in einem gedämpften Schwingkreis über der Zeit.
