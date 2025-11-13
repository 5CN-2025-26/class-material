
# Thema 8: Border Gateway Protocol (BGP) – Wegwahl, Peering & Routingprinzipien 0.1.1. Ausführliche Zusammenfassung

Der Professor erklärte, dass BGP das zentrale Routingprotokoll des Internets
ist. Es verbindet autonome Systeme (AS) , also große Netzwerke von Providern,
Universitäten oder Organisationen. Während andere Routingprotokolle (z. B.
OSPF, EIGRP, RIP) innerhalb eines Netzwerks arbeiten ( Interior Gateway
Protocols ), ist BGP ein Exterior Gateway Protocol (EGP) – es entscheidet,
welche Wege über AS-Grenzen hinweg genutzt werden.

## 1. Grundidee von BGP

BGP baut Verbindungen zwischen Routern unterschiedlicher AS auf. Diese Router heißen BGP-Peers oder Nachbarn . Zwischen ihnen werden Informationen über erreichbare Netzwerke (Präfixe) ausgetauscht – nicht Hop-Zahlen oder Metriken, sondern Politiken .Der Professor formulierte es so: „BGP ist kein mathematisches Optimierungsprotokoll, sondern ein politisches. Es entscheidet nach Regeln, die der Betreiber festlegt – nicht nach kürzester Strecke.“

## 2. BGP arbeitet über TCP

- BGP nutzt TCP Port 179 zur Verbindung der Nachbarn.
- Damit ist es zuverlässig (kein eigener Paketverlust-Mechanismus nötig).
- Beide Seiten müssen sich aktiv „begegnen“ (gegenseitige Nachbarschaftskonfiguration).

### Peering-Aufbau:

1. TCP-Verbindung herstellen.
2. OPEN-Nachricht austauschen (AS-Nummer, Version).
3. KEEPALIVE-Nachrichten halten die Sitzung aktiv.
4. UPDATE-Nachrichten enthalten Routeninformationen.

## Peering über Loopback & Next-Hop-Self

Der Professor betonte, dass Peering meist nicht über physische Interface-IPs ,
sondern über Loopback-Adressen eingerichtet wird. Grund:
- Interfaces können ausfallen, die Loopback-Adresse bleibt jedoch bestehen.
- Dadurch bleibt das Peering stabil, solange eine IP-Route zur Loopback
  besteht. Damit BGP-Nachbarn diese Loopback-Adresse erreichen, muss eine
  statische Route oder ein IGP (z. B. OSPF) sie bekannt machen.



Kommando-Beispiel (Cisco-Syntax):

```ios
router bgp 65001
    neighbor 10.0.0.2 remote-as 65002
    neighbor 10.0.0.2 update-source loopback0
    neighbor 10.0.0.2 next-hop-self
```

- update-source loopback0 : sagt, dass die Loopback-IP als Quelladresse verwendet wird.
- next-hop-self : zwingt den Router, sich selbst als Next-Hop einzutragen – notwendig, wenn der ur-sprüngliche Next-Hop sonst nicht erreichbar wäre.

Der Professor meinte: „Wenn Sie Peering über Loopbacks machen, müssen Sie das Routing darunter absichern – sonst steht BGP, obwohl TCP läuft.“

## 4. Routenwahl in BGP – keine Hop-Zählung

BGP entscheidet nicht nach „kürzestem Weg“ (wie RIP), sondern nach einer Reihe hierarchischer Attribute , die Prioritäten definieren.

### Wichtigste BGP-Attribute (in Reihenfolge der Auswertung):

1. Weight – Cisco-spezifisch, lokal wichtigster Wert (höher = besser).
2. Local Preference – entscheidet innerhalb des AS, welcher Ausgang bevorzugt wird.
3. AS_PATH – kürzer = besser (weniger durchlaufene AS).
4. Origin – kennzeichnet Ursprung der Route (IGP, EGP, incomplete).
5. MED (Multi-Exit Discriminator) – Empfehlung an Nachbarn, welchen Eingang zu
   wählen (niedriger = besser).
6. eBGP > iBGP – externe Routen werden internen vorgezogen.
7. IGP-Metrik zum Next-Hop – kürzere interne Route bevorzugt. Der Professor
   sagte: „BGP ist wie ein Bewerbungsgespräch – viele Kriterien, und wer am
   besten passt, bekommt den Job.“

## 5. Wichtige BGP-Konzepte

| Begriff                     | Bedeutung                                                         | Beispiel                               |
| --------------------------- | ----------------------------------------------------------------- | -------------------------------------- |
| AS (Autonomous System)      | Sammlung von Routern unter gemeinsamer Verwaltung                 | AS 65000 (Provider A)                  |
| eBGP / iBGP                 | Extern (zwischen AS) / In-tern (innerhalb eines AS)               | eBGP mit Provider, iBGP im Backbone    |
| Route-Reflector             | reduziert Full-Mesh-Anforderungen in iBGP                         | zentraler BGP-Server                   |
| Peering                     | direkter Austausch von Routinginformationen zwischen zwei Routern | BGP Peer = Nachbar                     |
| Next-Hop                    | IP des nächsten Routers zum Ziel                                  | wird oft per „next-hop-self“ angepasst |
| MED                         | Empfehlung an Nachbarn, welchen Eingang zu nehmen                 | beeinflusst eingehenden Traffic        |
| BGP Table vs. Routing Table | BGP kennt viele Wege, installiert aber nur den besten             | show ip bgp vs. show ip route          |

## 6. Troubleshooting & Analyse

Zur Fehlersuche nutzt man vor allem diese Befehle:

- show ip bgp
- show ip bgp summary
- show ip bgp neighbors
- show ip route

- show ip bgp zeigt alle bekannten Routen mit Attributen.
- Nur der beste Pfad landet im Routing-Table ( >) – die anderen bleiben als
  Alternativen gespeichert.
- Wenn Route in BGP-Tabelle, aber nicht im Routing-Table → meist Next-Hop nicht
  erreichbar oder Admin-istrative Distance höher als bei anderer Quelle. Der
  Professor betonte: „Das wichtigste Kommando im BGP ist ‚show ip bgp‘ – dort
  sehen Sie, ob der Router die Route kennt, auch wenn sie noch nicht verwendet
  wird.“

## Beispielhafte Prüfungsfrage (im Stil des Professors)

Frage: „Ein BGP-Router zeigt im Kommando show ip bgp mehrere Routen zu einem
Präfix an, aber nur eine steht im `show ip route`. Erklären Sie, warum das so
ist. Geben Sie außerdem an, in welcher Rei-henfolge BGP seine Routen auswählt
und welche Rolle das Attribut next-hop-self spielt.“

### Musterlösung

1. Erklärung der Situation: show ip bgp zeigt alle bekannten Routen (mögliche
   Pfade). BGP vergleicht sie anhand seiner Attribut-Hierarchie und wählt nur
   den besten Pfad aus. Nur dieser wird in die Routing-Tabelle geschrieben
   (`show ip route`).
2. Entscheidungsreihenfolge (vereinfacht):
    1. Höchster Weight (Cisco-intern)
    2. Höchste Local Preference
    3. Kürzester AS_PATH
    4. Ursprung ( IGP > EGP > incomplete)
    5. Niedrigster MED
    6. eBGP-Routen vor iBGP
    7. Kürzeste IGP-Distanz zum Next-Hop
    8. Kleinste Router-ID

3. Rolle von next-hop-self : Wenn BGP eine Route von einem externen Peer
   erhält, zeigt deren Next-Hop häufig auf den externen Nachbarn. Damit interne
   Router diese Route verwenden können, muss der Router, der sie weitergibt,
   sich selbst als Next-Hop eintragen – das geschieht mit `next-hop-self`. →
   Ohne dieses Kommando kann der in-terne Router den Zielpfad nicht auflösen →
   Route bleibt ungenutzt.

4. Fazit: BGP speichert viele Alternativen, aber nur die beste Route pro
   Zielnetz wird tatsächlich genutzt. Attribut-Prioritäten entscheiden, nicht
   die Hop-Anzahl.

## Lernnotizen & Merksätze

Merksätze:

- „BGP denkt politisch, nicht physikalisch.“
- „Viele Wege führen nach Rom, aber nur einer in die Routing-Tabelle.“
- „Next-Hop-Self rettet das Routing, wenn der Nachbar sonst nicht erreichbar ist.“
- „BGP redet über TCP 179 – langsam, aber zuverlässig.“
- „Weight und Local Preference steuern den Ausgang, MED den Eingang.“

Kernaussagen:

- BGP verbindet autonome Systeme über TCP 179.
- Nur der beste Pfad kommt in die Routing-Tabelle.
- Attribut-Reihenfolge bestimmt Wegwahl.
- `next-hop-self` stellt sicher, dass interne Router externe Routen nutzen
  können.
- Peering über Loopbacks ist stabiler, benötigt aber internes Routing darunter.

Übungsaufgaben:

1. Nenne drei Unterschiede zwischen iBGP und eBGP.
2. Warum nutzt BGP TCP statt UDP?
3. Was passiert, wenn der Next-Hop einer BGP-Route nicht erreichbar ist?
4. Ein Router zeigt zwei Routen mit gleichem AS_PATH, aber unterschiedlichem
   MED. Welche wird gewählt?
5. Erkläre, warum next-hop-self notwendig ist, wenn über ein IGP geroutete
   Loopbacks gepeert werden.
