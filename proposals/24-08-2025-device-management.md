---
layout: default
title: "Skift fra OS2borgerPC til FleetDM som styringsløsning for Linux-klienter"
author: "Jan Maack Kjerbye"
date: "2025-08-27"
tags: [styring, linux, open source, OS2, FleetDM, samarbejde]
status: "Udkast"
parent: "Proposals"
published: false
---

# Deltagelse i FleetDM projeket
> Moderne styringsløsning til mange klient typer

📆 _Last updated: {{ site.time | date: '%B %d, %Y' }}_

Udkast  
{: .label .label-yellow }

## Baggrund

Den nuværende løsning til styring af Linux-klienter, der er baseret på specialudviklet kode har p.t. over 10 år på bagen og vil fremadrettet kræve betydelige ressourcer til vedligeholdelse og videreudvikling.
Dette forslag har t

## FleetDM: Automatiseret compliance via reconciliation-pattern

Upstream projektet FleetDM adskiller sig fundamentalt fra traditionel device-administration ved at anvende et moderne **reconciliation-baseret driftsparadigme**:

- I stedet for at klikke ind på hver enkelt gruppe af enheder og køre bash-scripts manuelt, defineres den ønskede tilstand centralt som **policies**.
- FleetDM sørger derefter automatisk for at overvåge og rapportere afvigelser — og sættes op til automatisk at udbedre disse afvigelser.
- Dette skaber en **deklarativ og skalerbar tilgang** til compliance, hvor driftsteamet arbejder med ønsket tilstand frem for ad hoc handlinger på arbitrære tidspunkter.
- Systemet overvåger enhedernes tilstand 24/7-356 og frigør personalebindinger så effekterne af almindeligt forekommende hændelser som ferie, barsel, sygdom, jobskifte o.s.v. effektivt afbødes til at have minimalt impact på driften.
- Resultatet er en mere sikkert, robust, ensartet og effektiv adminstration og compliance — med betydligt lavere risko for menneskelige fejl og lavere vedligeholdelsesbyrde.


## Forventede effekter

Et skifte til FleetDM kan levere følgende forventede gevinster:

- Styrket samarbejde med et globalt udviklingsfællesskab
- Højere kvalitet og sikkerhed via automatiserede tests og løbende opdateringer
- Hurtigere onboarding og standardiseret drift

## Anvendte principper

- Åbenhed og genbrug af eksisterende open source-løsninger
- Modularitet og separation af ansvar
- OS²-principper om fælles udvikling og vedligehold
- Enterprise-arkitektur med fokus på skalerbarhed og fremtidssikring

## Risici og mitigering

- **Overgangsrisici ved migrering af klienter fra BorgerPC v.2.x.x**  
  _Afbødes gennem trinvis udrulning og etablering af poc/testmiljøer_

- **Afhængighed af upstream roadmap og governance**  
  _Afbødes ved aktiv deltagelse i FleetDM-community og bidrag til projektet_

- **Risiko for eksternt opkøb af FleetDM og/eller ændring af licenstype**  
  _Afbødes ved løbende overvågning af projektet og en exit-strategi for videreførelse under ny maintainer_

## Bilag og yderligere ressourcer  
_For at understøtte beslutningsgrundlaget og give mulighed for selvstændig vurdering af FleetDM, henvises her til relevante ressourcer:_

### 🎥 Demoer og videoguides

- [FleetDM YouTube-kanal](https://www.youtube.com/@fleetdm) – Demos af Fleet UI, CLI, REST API og Fleet Desktop  
  - *Fleet in under 3 minutes* – Kort introduktion  
  - *Deploy Fleet on Render in five minutes* – Hurtig opsætning  
  - *Sprint demos og roadmap previews* – Indblik i udvikling og nye features

### 📚 Tutorials og onboarding
- [FleetDM Tutorials & Guides](https://fleetdm.com/docs/get-started/tutorials-and-guides) – Komplet samling af guides til opsætning, MDM-migrering, policies, software deployment m.m.
- [Fleetctl Preview](https://fleetdm.com/try-fleet) – Lokal demo med Docker og CLI-værktøjet `fleetctl`
- [FleetDM GitHub Docs](https://github.com/fleetdm/fleet/blob/main/docs/Get%20started/tutorials-and-guides.md) – Tekniske guides til bl.a. Kubernetes, AWS, CentOS og GitHub Actions

### 🧪 Community-erfaringer og brugsscenarier
- [Kicking the Tires on FleetDM](https://keyboardcrunch.com/posts/FleetDM/) – Erfaringer fra homelab og research, inkl. praktiske tips og konfigurationer
- [Fleet Success Stories](https://fleetdm.com/success-stories) – Case studies fra organisationer som Wayfair og Schrödinger
