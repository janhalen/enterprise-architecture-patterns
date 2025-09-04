---
layout: default
title: "💻 Referencearkitektur: Overgang fra OS2borgerPC til samlet, moderne klientstyring"
summary: "Fra specialudviklet løsning til en fælles, skalerbar og open source-baseret platform, der understøtter alt fra kiosk-PC’er til kontorarbejdspladser – med højere sikkerhed, lavere vedligehold og stærkere samarbejde."
author: "Jan Maack Kjerbye"
date: "2025-08-24"
tags: [styring, linux, open source, OS2, FleetDM, samarbejde]
status: "Udkast"
parent: "Proposals"
published: true
---

{% include header_metadata.html %}

Udkast  
{: .label .label-yellow }

## Hensigtserklæring

Vi står over for et strategisk valg: Skal vi fortsætte med en aldrende, specialudviklet løsning til Linux-klientstyring – eller tage springet til en moderne, fælles platform, der bygger på åbne standarder og globalt samarbejde?

Dette forslag anbefaler en **kontrolleret overgang til FleetDM**, en open source-løsning, der muliggør **automatiseret compliance, skalerbar drift og lavere totalomkostninger**.  
Målet er at skabe en **fælles styringsmodel for alle klienttyper** – fra en kiosk-PC i borgerservice, et digitalt skilt på en NUC eller Raspberry Pi, til en let kontor-PC eller en maskine med adgang til biblioteks- og internetservices.

---

## Baggrund

Den nuværende løsning til styring af Linux-klienter er over 10 år gammel og kræver stigende ressourcer til vedligehold og videreudvikling.  
En fremtidssikret løsning skal:

- Reducere afhængigheden af specialudviklet kode
- Understøtte flere klienttyper og brugsscenarier
- Bygge på åbne standarder og fælles udvikling

---

## FleetDM: Automatiseret compliance via reconciliation-pattern

FleetDM adskiller sig fra traditionel device-administration ved at anvende et **reconciliation-baseret driftsparadigme**:

- **Deklarativ styring:** Policies definerer ønsket tilstand centralt – ikke manuelle scripts på enkelte enheder.
- **Automatiseret overvågning og udbedring:** Systemet rapporterer afvigelser og kan automatisk korrigere dem.
- **Skalerbarhed og robusthed:** Driftsteamet arbejder med ønsket tilstand frem for ad hoc handlinger.
- **Kontinuerlig compliance:** 24/7-overvågning reducerer effekten af ferie, sygdom og jobskifte.
- **Lavere risiko og vedligeholdelsesbyrde:** Mindre manuel håndtering, færre fejl.

---

## Forventede gevinster

- **Styrket samarbejde** med globalt open source-fællesskab
- **Højere kvalitet og sikkerhed** via automatiserede tests og løbende opdateringer
- **Hurtigere onboarding** og standardiseret drift på tværs af klienttyper
- **Fleksibilitet:** Understøtter alt fra ARM-baserede enheder til fulde arbejdsstationer

---

## Anvendte principper

- **Åbenhed og genbrug** af eksisterende open source-løsninger
- **Modularitet og separation af ansvar**
- **OS²-principper** om fælles udvikling og vedligehold
- **Enterprise-arkitektur** med fokus på skalerbarhed og fremtidssikring

---

## Risici og mitigering

- **Migreringsrisici fra BorgerPC v.2.x.x**  
  _Afbødes gennem trinvis udrulning og etablering af testmiljøer_

- **Afhængighed af upstream roadmap**  
  _Afbødes ved aktiv deltagelse i FleetDM-community og bidrag til projektet_

- **Risiko for ændring i licens eller ejerskab**  
  _Afbødes ved overvågning og exit-strategi for videreførelse under ny maintainer_

---

## Bilag og ressourcer

- **Why FleetDM?**  
  [FleetDM Official Docs](https://fleetdm.com/docs)

- **Getting Started**  
  [FleetDM Tutorials & Guides](https://fleetdm.com/docs/get-started/tutorials-and-guides)

- **Community & Success Stories**  
  [FleetDM Success Stories](https://fleetdm.com/docs)

  **Case study**
  [Remediating the xz vulnerability with Fleet](https://fleetdm.com/guides/remediating-the-xz-vulnerability-with-fleet)

- **Demo Videos**  
  [FleetDM YouTube Channel](https://www.youtube.com/@fleetdm)
---
