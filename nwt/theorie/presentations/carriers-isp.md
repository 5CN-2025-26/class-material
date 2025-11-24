
## Carrier vs. ISP

| Rolle | Beschreibung | Beispiele (AT) |
|------|-------------|----------------|
| **Carrier** | Besitzen **physische Infrastruktur** (Glasfaser, Unterwasserkabel, Kupfer) | **A1, Magenta, 3** |
| **ISP** | Mieten Infrastruktur → bieten **Internetzugang** für Kunden | **Lumen, GM Data, UPC** |

> **In Österreich:** **Alle großen Carrier sind gleichzeitig ISP**

---

## ISP-Hierarchie (Tier-Modell)

| Tier | Merkmale |
|------|---------|
| **Tier 1** | - Globale Reichweite <br> - **Kein Transitkauf** → nur **Peering** <br> - Beispiele: AT&T, Level 3 |
| **Tier 2** | - Regionale bis internationale Reichweite <br> - **Kaufen Transit von Tier 1** <br> - Bieten **Peering + Transit** an |
| **Tier 3** | - Nur **lokale Kunden** <br> - Kaufen Transit von Tier 2/1 |

---

## Peering – Arten & Funktion

| Typ | Beschreibung |
|-----|-------------|
| **Private Peering** | **1:1-Verbindung** zwischen zwei ISPs (direkt) |
| **Public Peering** | Über **Internet Exchange Point (IXP)** – zentraler Knoten |

### Internet Exchange Points (Beispiele)
- **Wien:** **VIX (Vienna Internet eXchange)**
  - Betrieben von der **Universität Wien**
  - Hostet z. B. **Interxion** (Rechenzentrum)
  - **Peering Matrix:** Übersicht, wer mit wem peert
  - **BGP-Tools:** Zeigen advertised Netze

---

## Netzwerktechnologien & Architekturen

| Technologie | Jahr | Prinzip | Nachteil/Vorteil |
|------------|------|--------|------------------|
| **Frame Relay** | 1990er | **Virtual Circuits** (PVC/SVC) <br> - **DLCI** statt Labels | Kostengünstig, aber **kein QoS** |
| **ATM** | 1990er | **Fixed Packet Size (53 Byte)** <br> - **QoS** | Geringere Latenz, aber komplex |
| **MPLS** | 2000er | **Label-basiert (Layer 2.5)** <br> - Trennt Kundennetze <br> - Im **ISP-Backbone** | **Sehr teuer** → dedizierte Leitungen |
| **SD-WAN** | 2010er | **Software-defined** <br> - Steuert Traffic intelligent <br> - Kombiniert Internet + MPLS | **Kosteneffizient** → Hybridlösungen |

### Verbindungstypen (Carrier Ethernet)
| Typ | Struktur |
|-----|---------|
| **E-Line** | **Point-to-Point** |
| **E-LAN** | **Full Mesh** (jeder mit jedem) |
| **E-Tree** | **Hub-and-Spoke** (Zentrale + Filialen) |

---
