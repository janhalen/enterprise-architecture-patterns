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

## Baggrund

Den nuværende løsning til styring af Linux-klienter er over 10 år gammel og kræver stigende ressourcer til vedligehold og videreudvikling.
Vi står over for et strategisk valg: Skal vi fortsætte med en aldrende, specialudviklet løsning til Linux-klientstyring – eller tage springet til en moderne, fælles platform, der bygger på åbne standarder og globalt samarbejde?

Dette forslag anbefaler en **kontrolleret overgang**, til en genbrugelig [upstream](https://maximilianmichels.com/2021/upstream-first/) open source-løsning, der muliggør **automatiseret compliance, skalerbar drift og lavere totalomkostninger**.  
Målet er at skabe en **fælles automatiseret styringsmodel for alle klienttyper** – fra en kiosk-PC i borgerservice, et digitalt skilt på en NUC eller Raspberry Pi, til en let kontor-PC eller en maskine med adgang til biblioteks- og internetservices.

---

## FleetDM: Automatiseret compliance via reconciliation-pattern

FleetDM adskiller sig fra traditionel device-administration ved at anvende et **reconciliation-baseret driftsparadigme**:

- **Deklarativ styring:** Policies definerer ønsket tilstand centralt – ikke manuelle scripts på enkelte enheder.
- **Automatiseret overvågning og udbedring:** Systemet rapporterer afvigelser og kan automatisk korrigere dem.
- **Skalerbarhed og robusthed:** Driftsteamet arbejder med ønsket tilstand frem for ad hoc handlinger.
- **Kontinuerlig compliance:** 24/7-overvågning reducerer effekten af ferie, sygdom og jobskifte.
- **Lavere risiko og vedligeholdelsesbyrde:** Mindre manuel håndtering, færre fejl.

Tilføjet 10 okt 2025
{: .label .label-green }

### Zero Trust Network Access (ZTNA)

Ved at integrere FleetDM med en open source-implementering af ZTNA kan løsningen hærdes betydeligt via en **Software-Defined Perimeter (SDP)**, der lukker for traditionelle angrebsflader og realiserer ekstra fordele ved et Zero Trust-miljø.

| Sikkerhed 🛡️ | Pålidelighed 🚀 | Kontrol 🚦 |
| :--- | :--- | :--- |
| **Usynligt privat netværk** (Netværksforbindelser udstilles ikke offentligt). | **Stabile forbindelser uanset device lokation** (Virker på tværs af alle netværk uden firewall-ændringer). | **Central styring af adgangsregler** (Netværksregler styres ét sted frem for mange distribuerede firewalls). |
| **Styrede klient adgange via politikker** (Enheder får kun adgang, f.eks hvis de er i en sund sikkerhedstilstand). | **Enkel klient identifikation** (Logiske navne til alle typer klienter'er, istedet for IP-adresser). | **Separation af Ansvar** (Adskiller kontrollen af netværket fra den daglige drift af services). |
| **Automatisk og Sikker Opkobling** (Automatiserede, sikre opsætningsflows). | | |

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
- **Standardiseret løsnings-arkitektur** med fokus på skalerbarhed og fremtidssikring

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

- **Testimonials**  
  [Is it any good? What people are saying?](https://fleetdm.com/testimonials)

- **Case study**  
[Remediating the xz vulnerability with Fleet](https://fleetdm.com/guides/remediating-the-xz-vulnerability-with-fleet)

- **Demo Videos**   
  [FleetDM YouTube Channel](https://www.youtube.com/@fleetdm)

- **Getting Started**  
  [FleetDM Tutorials & Guides](https://fleetdm.com/docs/get-started/tutorials-and-guides)

---
