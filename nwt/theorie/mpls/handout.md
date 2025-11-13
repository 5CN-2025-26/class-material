
# Teil 2 – Kompaktes Lernskript / Handout

## Grundkonzept

* Layer 2.5 Technologie zwischen Ethernet (L2) und IP (L3)
* Kombination aus Routing (Control Plane) und Switching (Data Plane)
* Overlay-Prinzip: Labels statt IP-Adressen
* Ziele: **Performance, QoS, Skalierbarkeit, Traffic Engineering**

---

## Begriffe und Komponenten

| Begriff              | Beschreibung                                            |
| -------------------- | ------------------------------------------------------- |
| **MPLS Domain**      | Logisches Netzwerk, meist ein AS                        |
| **LSR**              | Label Switching Router                                  |
| **PE / CE**          | Provider Edge / Customer Edge                           |
| **Ingress / Egress** | Eintritt / Austritt in die MPLS-Domäne                  |
| **Label**            | 20-Bit-Identifier für FEC                               |
| **LDP**              | Label Distribution Protocol – dynamisches Label-Mapping |
| **FEC**              | Forwarding Equivalence Class                            |
| **LFIB / LIB / FIB** | Weiterleitungstabellen für MPLS                         |
| **PHP**              | Penultimate Hop Popping – letzte Etappe unlabeled       |

---

## Protokollintegration

* IGP (OSPF / EIGRP) → Pfadberechnung
* LDP → Label-Vergabe
* MPLS → Weiterleitung
* BGP → Policy-Layer (on top of MPLS)

---

## Traffic Engineering

* Label Stacking für Pfadvorgabe
* QoS & Latency über EIGRP-Metriken
* **K1–K5:** Bandwidth, Delay, Reliability, Load, MTU

---

## Control vs Data Plane

| Ebene             | Aufgabe                                   |
| ----------------- | ----------------------------------------- |
| **Control Plane** | Routing, Protokolle, Management           |
| **Data Plane**    | Forwarding, CEF, Label-Switching          |
| **CEF**           | Cisco Express Forwarding → Cached Lookups |

---

## Sicherheitsaspekte

* Labels im Klartext → Manipulationsrisiko
* Angriffspunkte: LDP, Label-Spoofing
* Schutz: Authentifizierung, konsequentes Device Hardening
* **Fehlerquelle:** vorkonfigurierte Hot-Standby-Router

---

## Prüfungsrelevante Themen

1. Erklären Sie den Begriff „Forwarding Equivalence Class“.
2. Was macht das Penultimate Hop Popping (PHP)?
3. Wie unterscheidet sich Control Plane von Data Plane?
4. Was leistet das Label Distribution Protocol (LDP)?
5. Welche Rolle spielt EIGRP in modernen MPLS-Netzen?
6. Wie kann CEF die Leistung verbessern?
7. Welche Tabellen existieren in einem MPLS-Router?

---

## Merksätze aus der Vorlesung

> „MPLS ist das erste Overlay – alles andere ist darauf gebaut.“
>
> „Wer Labels versteht, versteht WAN.“
>
> „Control Plane ist das Hirn – Data Plane die Muskulatur.“
>
> „Wenn du Penultimate Hop Popping erklärst, hast du den Test bestanden.“

---
