---
layout: default
title: "🧩 Referencearkitektur: connector"
author: "Jan Maack Kjerbye"
date: 2025-08-14
tags: [open source, samarbejde]
summary: "En moderne genbrugelig  snitflade-arkitektur, der understøtter data-integration på tværs"
status: "Udkast"
parent: Proposals
---
{% include header_metadata.html %}


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


## 💰 Forventede effekter

- Reducerede udgifter til cybersikkerhed og fejlretning via fælles vedligehold.
- Investeringvillighed i øget kvalitet og resilliens qua de ovenstående besparelser.
- Drastisk minimering af teknisk gæld ved at udfase store mængder uhomogen snitfladekode.
- Realisering af handlefrihed og ejerskab over myndighedens egen data-infrastruktur.


🔗 https://github.com/os2sandbox/connector