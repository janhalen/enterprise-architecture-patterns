---
layout: default
title: "🧩 Forslag til Referencearkitektur: connector (arbejdstitel)"
author: "Jan Maack Kjerbye"
date: 2025-08-14
tags: [open source, samarbejde]
status: "Udkast"
parent: Proposals
---

# 🧩 Forslag til referencearkitektur: connector (arbejdstitel)

📆 _Last updated: {{ site.time | date: '%B %d, %Y' }}_

Udkast
{: .label .label-yellow }

## 🎯 Formål
Et fælles projekt for en moderne genbrugelig  snitflade-arkitektur, der understøtter **data-integration** på tværs af offentlige systemer. 

- Skabe råderum til at investere i **øget sikkerhed og resiliens**, via fællesfinansieret udvikling af kildekoden til snitfladerne.

- Levere besparelser ved at **samle udgifterne** til vedligehold omkring EN fælles kildekode. 

- Bane vejen for en **fremtidssikrede, resilliente snitflader** ved at udvikle dem i fællesskab som selvstændige moduler der kan genbruges af alle.

- **Eliminere teknisk gæld** ved at separere snitfladerne fra fagsystemerne og reducere behovet for betydelige mænger duplikeret non-standard infrastruktur kode.

- **Realisere handlefrihed** for de bidragende myndigheder ved at frigøre styring og ejerskab over snitflade koden fra enkelte fagsystemer og leverandører.

- **Frigøre udgifter** til duplikerede snitflade implementeringer i hvert enkelt produkt og udnytte dem til **forretningsfunktioner der skaber reel værdi**

- **Fjerne ventetid og overhead** fra snitflade projekter ved at genanvende udvalgte dele af kildekoden fra eksisterende open source løsninger.

---

## 🏗️ Arkitekturprincipper
- **Open Source**: Transparens og fælles ejerskab.
- **Modularitet**: Komponenter kan udskiftes, tilføjes og tilpasses efter den enkelte myndigheds behov.
- **Standardisering**: Bruger velkendte, velunderstøttede protokoller og formater.
- **Genbrug**: Konfigurationer er løskoblede fra funktionskoden og gør genbrug simpelt.
- **Automatisering**: Moderne indbygget automatisering skaber mulighed for transparens og resilliens, uden tab af effektivitet.

---

## 🔧 Teknisk Struktur
- Projektet er p.t. bygget op i en **sandbox** for eksperimenter og samarbejde.
- Der er fokus på **dataflow** og **integration**, men selve koden er endnu minimal.
- Diagrammer og dokumentation er under opbygning – mulighed for at bidrage!

---

## Risisci

| ID | Risiko (årsag → effekt) | Sandsynlighed | Konsekvens | Risikoniveau | Afbødende tiltag | Ejer | Status |
|---:|---|:---:|:---:|:---:|---|---|---|
| R1 | Utilstrækkelig opbakning og ressourcer → projektet mangler kritisk masse og fremdrift | Middel | Høj | 🟥 Høj | Etabler sponsor-kreds; identificér 2–3 pilotmyndigheder; hybrid finansiering (timer + midler) | Programleder | Åben |
| R3 | Eksterne afhængigheder (leverandører, integrationer) → forsinkelser og ekstraarbejde | Middel | Middel | 🟧 Middel | Permissiv licens; åbne API’er; referenceimplementering; partnerskab med specialister; fallback-strategier | Arkitekt | Åben |
| R4 | Sikkerheds- eller databeskyttelseshændelse → tillidstab og juridiske konsekvenser | Lav | Høj | 🟧 Middel | Threat modeling; secure SDLC; DPIA; audit-logging; privacy by design | Sikkerhedsansvarlig | Åben |
| R2 | Uklar rollefordeling og scope i opstartsfasen → forsinkelser og friktion | Lav | Middel | 🟨 Lav | Følg OS2’s proces; definér MVP og afgrænsninger; aftal styregruppe tidligt | Programleder | Åben |
| R5 | Manglende drifts- og vedligeholdsmodel → bus factor og driftshuller | Lav | Middel | 🟨 Lav | OS2’s vedligeholdelsesmodel; LTS-branching; rotationsplan; runbooks | DevOps lead | Åben |

**Legend:** Sandsynlighed/Konsekvens = Lav, Middel, Høj.  
**Risikoniveau:** 🟨 Lav · 🟧 Middel · 🟥 Høj.








## 💰 Forventede effekter

- Reducerede udgifter til cybersikkerhed og fejlretning via fælles vedligehold.
- Investeringvillighed i øget kvalitet og resilliens qua de ovenstående besparelser.
- Drastisk minimering af teknisk gæld ved at udfase store mængder uhomogen snitfladekode.
- Realisering af handlefrihed og ejerskab over myndighedens egen data-infrastruktur.


🔗 https://github.com/os2sandbox/connector