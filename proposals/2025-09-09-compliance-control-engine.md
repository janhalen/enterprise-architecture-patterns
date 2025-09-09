---
layout: default
title: "Automatiseret kontrolmotor for databehandling med OPA og OpenTelemetry"
author: "Jan Maack Kjerbye"
date: "2025-09-09"
tags: ["GDPR", "compliance", "OPA", "OpenTelemetry", "automatisering", "kontrolmotor", "security-by-design"]
status: "Udkast"
parent: "Proposals"
published: false
---

{% include header_metadata.html %}

Udkast  
{: .label .label-yellow }

## Baggrund

Datatilsynets skabeloner til konsekvensanalyse af databehandling er i dag baseret på manuelle vurderinger og dokumentation i Excel eller Word. Denne tilgang er ofte reaktiv og baseret på juridisk ansvar, hvor organisationer erklærer overholdelse uden teknisk bevisførelse. Der mangler en automatiseret og proaktiv metode til at sikre, dokumentere og auditere lovlig databehandling — især i komplekse og dynamiske systemlandskaber.

## Formål og forventet effekt

Denne indsats har til formål at udvikle en automatiseret kontrolmotor, der evaluerer databehandling mod GDPR-krav ved hjælp af Open Policy Agent (OPA) og OpenTelemetry (OTEL).  
De ønskede effekter af indsatsen omfatter:

- Objektiv og maskinlæsbar evaluering af databehandling
- Automatisk dokumentation og audit trail for compliance
- Proaktiv blokering af ulovlig eller risikabel databehandling
- Reduktion af manuelt arbejde og juridisk usikkerhed
- Understøttelse af security-by-design og security-by-default

## Anvendte principper

Indsatsen bygger på følgende principper:

- **Deklarativ compliance**: Regler defineres som Rego-policies i OPA
- **Observability**: Alle evalueringer logges via OpenTelemetry
- **Automatisering**: Inputdata struktureres og evalueres uden manuel indgriben
- **Åbenhed og genbrug**: Skabeloner og kode baseres på åbne standarder og kan deles
- **Modularitet**: Systemet kan integreres med eksisterende CI/CD, IAM og CMDB-løsninger

## Risici

- **Manglende datakvalitet**: Inputdata kan være ufuldstændige eller upræcise  
  _Afhjælpning_: Brug guided inputskemaer og automatiseret dataintegration
- **Modstand mod automatisering**: Juridiske eller organisatoriske barrierer  
  _Afhjælpning_: Inkludér DPO og ledelse tidligt i designfasen
- **Kompleksitet i regelmodellering**: GDPR er juridisk og kontekstafhængig  
  _Afhjælpning_: Start med generiske regler og udvid med domænespecifikke policies

-----


Noter: 
Traditionel DPIA	Din tilgang
Menneskelig vurdering	Maskinlæsbar input
Juridisk ansvar	Teknisk bevisførelse
Dokumentation i Word/Excel	Audit trail + policy-evalueringer
Reaktiv	Proaktiv og løbende
Tilsynsforventning	Kontinuerlig compliance