
# Teil 2 – Kompaktes Handout / Lernskript

## Überblick

* Thema: MPLS-Backbone & BGP Policy-Routing
* Ziel: Pfadmanipulation, Policy Enforcement, Governance
* Struktur: MPLS als Data Plane, BGP als Control & Policy Plane

---

## BGP-Basics

| Begriff                    | Bedeutung                                                 |
| -------------------------- | --------------------------------------------------------- |
| **AS (Autonomous System)** | Logische Routingdomäne eines Providers                    |
| **BGP Speaker**            | Router mit aktivem BGP-Prozess                            |
| **Peering**                | Logische Verbindung zwischen AS (nicht physisch adjazent) |
| **eBGP / iBGP**            | Austausch zwischen / innerhalb von AS                     |
| **Full-Mesh-Problem**      | iBGP skaliert schlecht → Route Reflectors nötig           |

---

### Wichtige Attribute

| Attribut             | Funktion                        | Richtung | Typ       |
| -------------------- | ------------------------------- | -------- | --------- |
| **AS-Path**          | Sequenz der durchlaufenen AS    | Beide    | Mandatory |
| **Next-Hop**         | Adresse des nächsten Routers/AS | Beide    | Mandatory |
| **Local Preference** | Bevorzugung eingehender Pfade   | Inbound  | Optional  |
| **MED**              | Bevorzugung ausgehender Pfade   | Outbound | Optional  |
| **Community**        | Gruppierung von Routen          | Beides   | Optional  |

---

### Politische und ökonomische Aspekte

* Pfadwahl durch **Konzerninteressen** (z. B. Telekom Austria → BT Group).
* **Routing-Sanktionen** durch AS-Filter (z. B. Blockierung von Ländern).
* **Peering am VIX:** täglich verhandelt; abhängig von Auslastung und Ereignissen.

---

### Compliance & Sicherheit

* **Bogons:** nicht vergebene, aber routbare IPs → Sicherheitsrisiko.
* **Haftung:** Geschäftsführer bleibt verantwortlich (Sorgfaltspflicht).
* **Lösung:** wöchentliche Prüfung, Reporting-Prozesse, Compliance-Beauftragter.
* **Device Hardening:** RFC 1918-Filter an Edge-Routern.

---

### BGP-Stabilität

* **Route Flapping** → instabile Präfixe
* **Route Dampening** → temporäre Unterdrückung
* Ziel: **Stabilität > Geschwindigkeit**

---

## Typische Prüfungsfragen

1. Erklären Sie den Unterschied zwischen `Local Preference` und `MED`.
2. Wie dient der `AS-Path` zur Loop Detection?
3. Was ist eine BGP Community und wofür wird sie eingesetzt?
4. Warum benötigt iBGP Route Reflectors?
5. Was sind „Bogons“ und wie schützt man sich dagegen?
6. Welche Rolle spielt BGP im MPLS-Backbone?
7. Wie kann BGP als politisches Instrument wirken?

---

## Merksätze aus der Vorlesung

> „BGP ist kein Routing-, sondern ein Politikprotokoll.“
>
> „Unwissenheit schützt nicht vor Haftung – auch nicht im Datacenter.“
>
> „Je größer das Netz, desto mehr ist Routing Prozessmanagement.“
>
> „Wer das Route Reflector Problem versteht, besteht die Reifeprüfung.“
