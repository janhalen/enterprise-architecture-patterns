---
layout: default
title: 👥 Aktiviteter & roller i OS2-projekter
summary: "En standardiseret aktivitets og rollebeskrivelse for OS2-projekter baseret på internationale Open Source best practices."
author: "Jan Maack Kjerbye"
date: "2025-09-16"
parent: Guides
---

{% include header_metadata.html %}

Udkast  
{: .label .label-yellow }

Denne korte guide definerer ansvarsfordelingen i OS2-projekter. For at professionalisere og sikre ejerskab er opgaverne delt mellem specialiserede roller fremfor en generel koordinator. Centralt for modellen er adskillelsen mellem teknisk release-styring, produktmæssig prioritering og uafhængig kode-review (Four eyes principle). 

## 🖼️ Projektrammer og Leverancestyring

| AKTIVITET | ROLLE | BEST PRACTICE |
| :--- | :--- | :--- |
| **Leverancestyring & Værdi** | Program Lead & Product Owner (PO) | • Ejer "Hvad" og "Hvorfor" (vision og prioritering).<br>• Godkender leverancer ift. forretningsværdi.<br>• Håndterer politiske interessenter og strategisk retning. |
| **Strategi & Standarder** | Rådgivende Enterprise Arkitekt | • Afklarer ophæng til strategiske mål.<br>• Sikrer overensstemmelse med nationale og internationale standarder.<br>• Kvalitetssikrer leverancer op imod arkitektur krav og principper. |
| **Operationel Drift & Support** | Projektsekretær | • Frigør PO ved at eje "Hvordan" og "Hvornår" (logistik).<br>• Facilitering af møder, referater og opfølgning på action-items.<br>• Onboarding af medlemmer og styring af adgangsrettigheder i systemer.<br>• Sikker dokumenthåndtering, arkivering og versionsstyring. |

### 📋 Projekt & Community forvaltning

| AKTIVITET | ROLLE | BEST PRACTICE |
| :--- | :--- | :--- |
| **Behovsmodning & Backlog** | PO & Release Manager | • Screening af indkomne issues.<br>• PO skriver User Stories; RM validerer teknisk modenhed før udvikling besluttes.<br>• Ved uklarhed og forståelsesgab konsulteres arkitekten. |
| **Funktionsverifikation** | Product Owner (PO) | • Slutgodkendelse af features baseret på Acceptance Criteria.<br>• Fokus på om løsningen løser brugerens behov. |
| **Design og teknologivalg** | Rådgivende arkitekt | • Anviser best practices før udviklingen startes.<br>• Rådgiver om teknologivalg og standarder. |
| **Community Management** | Community Manager | • Håndterer Code of Conduct, issue-skabeloner og brugeradgange til issue-trackers.<br>• Sikrer god tone og uddanner i brug af issue-trackeren. |

## ⛓️ Applikationsudvikling

| AKTIVITET | ROLLE | BEST PRACTICE |
|:---|:---|:---|
| **Nyudvikling af applikationskode** | Specialist-udvikler / Applikationsudvikler | - Modularisering og domain-driven design.<br>- Arbejder i isolerede feature branches ud fra issue-beskrivelser.<br> - |
| **Review af applikationskode** | Senior udvikler | - Reviewer kode i PRs<br>- Arbejder med Four-Eyes principle for øget transparens og kvalitet.<br>- Er |


## ⚙️ Klargøring og leverance

| Aktivitet | Rolle | Best Practice |
|:---|:---|:---|
| **Build-, package- og release-pipelines** | CI/CD Engineer / Automatiseringsudvikler | Brug declarative pipelines (f.eks. GitHub Actions). Udvikler CI/CD på bestilling fra Release Manager. |
| **Vedligeholdelse af release-processer** | Release Manager (RM) | Styrer release-tags og release notes. Har overordnet ansvar for **Branch Protection Rules** og teknisk beskyttelse af `main`. |
| **Automatisk opdatering af afhængigheder** | CI/CD Engineer / RM | Brug værktøjer som Renovate eller Dependabot. RM kan godkende mindre rettelser og automatiske sikkerhedspatches. |
| **Vulnerability Management** | Release Manager (RM) | Ansvarlig for modtagelse af sikkerhedsrapporter (VDP) og uddelegering af udbedring som hastesager til leverandører. |

## 🧪 Kvalitetssikring

| Aktivitet | Rolle | Best Practice |
|:---|:---|:---|
| **Teststrategi og testkode** | QA Engineer / Test Automation Specialist | Brug test-first/TDD. Adskil unit, integration og e2e tests. Verifikation sker optimalt via en test-faggruppe. |
| **Dokumentationsstyring** | Technical Editor (TE) | Reviewer PRs for dokumentationskvalitet. PO/RM merger som udgangspunkt kun, hvis TE har givet "OK". |


## 🛠️ Produktionsdrift

| Aktivitet | Rolle | Best Practice |
|:---|:---|:---|
| **Klargøring af produktionsmiljøer** | Driftsoperatør | Brug Infrastructure-as-Code (Ansible, Terraform) for konsistens og sporbarhed. |
| **Konfiguration af sidecars/apps** | DevOps-specialist / Driftsoperatør | Hold konfiguration versioneret og miljøspecifik. Anvend standard deklarative formater. |
| **Udrulning til produktion** | Driftsoperatør | Automatisér med CI/CD pipelines og brug blue/green eller canary deployment-strategier. |
| **Overvågning og Observability** | Driftsoperatør | Brug standard observability-værktøjer (f.eks. CNCF OpenTelemetry). |


### 📚 Læs mere

> - 📘 [Linux Foundation – Open Source Guides](https://www.linuxfoundation.org/resources/open-source-guides)  
> - 📘 [Open Source Guides – Leadership & Governance](https://opensource.guide/leadership-and-governance/)  
> - 📘 [OS2 – Strategi for Open Source Governance](https://os2.dk)

---

## Integration af Kapabiliteter i OS2 Projekter

| AKTIVITET                          | ROLLE                     | BEST PRACTICE                                                    | RELATERET KAPACITET            |
|-------------------------------------|---------------------------|----------------------------------------------------------------|----------------------------------|
| **Behovsmodning & Backlog**         | PO & Release Manager      | Screening af indkomne issues; skriving af User Stories.           | Håndtering af problemer og pull requests |
| **Community Management**             | Community Manager         | Håndterer Code of Conduct, issue-skabeloner og brugeradgang.    | Community Management              |
| **Dokumentationsstyring**           | Technical Editor (TE)     | Reviewer PRs for dokumentationskvalitet.                         | Dokumentationsovervågning        |
| **Vulnerability Management**         | Release Manager (RM)      | Ansvarlig for modtagelse af sikkerhedsrapporter.                  | Automatisk Sikkerhedsovervågning |
| **Operationel Drift & Support**     | Projektsekretær           | Facilitering af møder, opfølgning på action-items.               | Kommunikation og feedback kanaler |
