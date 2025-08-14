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
Et fælles projekt for moderne dataworkflow-arkitektur, der understøtter **data-integrationer** på tværs af offentlige systemer. Målet er at skabe en **modulær, genbrugelig og vedligeholdelsesvenlig** løsning.

- Forslag om at **splitte kode ud fra eksisterende løsninger** og gøre dem mere genbrugelige.
- Fokus på **konfiguration som kode** og **miljøvariabler** for nem deployment.
- Ønske om at gøre det nemt at **komme i gang** med fælles komponenter.

---

## 🏗️ Arkitekturprincipper
- **Open Source**: Transparens og fælles ejerskab.
- **Modularitet**: Komponenter kan udskiftes og tilpasses.
- **Standardisering**: Bruger velkendte protokoller og formater.
- **Automatisering**: Fokus på CI/CD og konfigurationsstyring.

---

## 🔧 Teknisk Struktur
- Projektet er p.t. bygget op i en **sandbox** for eksperimenter og samarbejde.
- Der er fokus på **dataflow** og **integration**, men selve koden er endnu minimal.
- Diagrammer og dokumentation er under opbygning – mulighed for at bidrage!

---

## 💡 Værdi for Udviklingspartnere
- Fælles governance og mulighed for at påvirke retningen
- Modularitet gør det muligt at bruge egne komponenter og ikke være låst til bestemte udviklingssprog
- Fælles vedligehold reducerer drift og fejlretning
- Åbne bidrag med features og fixes kan mindske ressourcepresset
- Håndhævelse af standardiserede templates og dokumentation sikrer hurtig onboarding og mitigerer den øgede kompleksitet
- Fælles financiering via OS² fællesskabet frigører udgifter til fælles infrastruktur fra projekternes egne budgetter
- Udviklere kan fokusere på at skabe forretningsværdi i stedet for at bruge tid på at genopfinde og vedligeholde specialudviklet infrastrukturkode.
- Udvikling på tværs af projekter kan trækkes ud af siloer og genanvendes bredt med betydelige kvalitetsforbedringer og mindre mental load på enkeltudviklere.
- Genbrug af infrastrukturkode på tværs af projekter reducerer silo-tænkning, forbedrer kvaliteten og mindsker den mentale belastning for individuelle udviklere.


🔗 https://github.com/os2sandbox/connector