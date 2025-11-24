
# Überblick - Handout

* Thema: Dynamic Multipoint VPN (DMVPN)
* Kombination aus GRE, NHRP, IPsec
* Architektur: Hub-and-Spoke mit dynamischen Spoke-to-Spoke-Tunneln
* Ziele: Skalierbarkeit, Redundanz, dynamische Tunnel, Zero-Touch-Deployment

---

## Hauptkomponenten

| Komponente | Funktion                                   |
| ---------- | ------------------------------------------ |
| Hub        | NHRP-Server, zentrale Steuerung, Redirects |
| Spoke      | NHRP-Client, registriert sich beim Hub     |
| Overlay    | GRE- oder IPsec-basiertes virtuelles Netz  |
| Underlay   | Physisches Transportnetz (z. B. Internet)  |

---

## Phasen von DMVPN

| Phase | Charakteristik                    | Kommunikation                  |
| ----- | --------------------------------- | ------------------------------ |
| 1     | Statische Tunnel (P2P GRE)        | Nur über Hub                   |
| 2     | Dynamische Tunnel (mGRE + NHRP)   | Spoke-to-Spoke möglich         |
| 3     | Redirects + automatisches Routing | Optimale Pfade, optional IPsec |

---

## Protokolle

* **NHRP:** Auflösung logischer Next-Hops → physische Adressen
* **OSPF:** Routing innerhalb des Overlays

  * Wichtige Typen: Point-to-Multipoint, Non-Broadcast
  * Split-Horizon vermeiden → Priority 0 für Spokes
* **IPsec:** Verschlüsselung (Phase 3+), IKEv2, PKI optional

---

### Vorteile

* Skalierbar (Hunderte Standorte)
* Zero-Touch Deployment → SD-WAN
* Spoke-to-Spoke und Hub-to-Hub Kommunikation
* Multicast-fähig
* Overlay-unabhängig (IPv4, IPv6, MPLS, OT-Protokolle)

---

## Prüfungsrelevanz

| Schwierigkeitsgrad | Szenario                           | Bewertung          |
| ------------------ | ---------------------------------- | ------------------ |
| Basis              | Phase 1, statisch, unverschlüsselt | Mindestanforderung |
| Fortgeschritten    | Phase 2, dynamisch                 | gute Note          |
| Sehr gut           | Phase 3, Redirect, OSPF korrekt    | sehr gute Note     |
| Exzellent          | Phase 3 + IPsec (IKEv2/PKI)        | Höchstbewertung    |

**Erwartet:** funktionierendes Overlay, dynamisches Routing, saubere Struktur, Zeitmanagement.

**Tipp des Professors:**

> „Übung ist Intelligenztest. Wer DMVPN Phase 3 konfigurieren kann, versteht WAN.“

---

## Praxisbeispiele

* **Industrie (OT):** Fernsteuerung von Anlagen (z. B. Vöest Hochofen)
* **Cloud:** Standortanbindung an Rechenzentren
* **Mobilfunk:** MSC-to-MSC-Kommunikation
* **Terminalserver / VPN über NAT:** DMVPN über doppelten Tunnel

---

## Typische Prüfungsfragen

* Erklären Sie den Aufbau eines DMVPN-Phase-3-Netzes.
* Beschreiben Sie den Unterschied zwischen NHRP Registration und Resolution.
* Welche OSPF-Network-Types eignen sich für Multipoint-Topologien?
* Warum ist Split-Horizon in DMVPN relevant?
* Wie kann IPsec in ein dynamisches GRE-Netz integriert werden?
* Welche Vorteile bietet DMVPN gegenüber statischen Site-to-Site-VPNs?

---

## Merksätze aus dem Unterricht

> „Routing kommt erst, wenn der Boden gebaut ist.“
> → Erst Overlay etablieren, dann Routing aktivieren.

> „IPv6 macht alles einfacher – aber verkauft keine Services.“
> → Hinweis auf wirtschaftliche Relevanz klassischer Overlays.

> „clear ip ospf process – der emotionale Reset von OSPF.“
> → Befehl nach jeder Konfigurationsänderung nötig.
