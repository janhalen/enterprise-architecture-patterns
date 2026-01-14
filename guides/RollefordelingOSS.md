---
layout: default
title: 👥 Rollefordeling i Open Source Software projekter
summary: "Et aktivitetsbaseret rolle- og Aktivitetsoverblik for Open Source Projekter med fokus på genbrugelighed, kvalitet og specialisering."
author: "Jan Maack Kjerbye"
date: "2025-09-16"
parent: Guides
---

{% include header_metadata.html %}

Udkast  
{: .label .label-yellow }

Denne korte guide definerer ansvarsfordelingen i OS2-projekter. For at professionalisere og sikre ejerskab er opgaverne delt mellem specialiserede roller fremfor en generel koordinator. Centralt for modellen er adskillelsen mellem teknisk release-styring, produktmæssig prioritering og uafhængig kode-review (Four eyes principle).

---

# 👨‍💻 Applikationsudvikling

| Aktivitet | Rolle | Best Practice |
|:---|:---|:---|
| **Nyudvikling af applikationskode** | Specialist-udvikler / Applikationsudvikler | Modularisering og domain-driven design. Arbejder i isolerede feature branches ud fra issue-beskrivelser. |
| **Review af applikationskode** | Senior udvikler (Ekstern/Uafhængig) | **Four eyes principle:** Minimum to uafhængige senior-udviklere reviewer kode for at undgå bias før PR sendes til PO/RM. |
| **Design og teknologivalg** | Rådgivende arkitekt | Indkaldes ad hoc til at anvise best practice for applikationens livscyklus og infrastruktur før udviklingen startes. |

---

# ⚙️ Klargøring og leverance

| Aktivitet | Rolle | Best Practice |
|:---|:---|:---|
| **Build-, package- og release-pipelines** | CI/CD Engineer / Automatiseringsudvikler | Brug declarative pipelines (f.eks. GitHub Actions). Udvikler CI/CD på bestilling fra Release Manager. |
| **Vedligeholdelse af release-processer** | Release Manager (RM) | Styrer release-tags og release notes. Har overordnet ansvar for **Branch Protection Rules** og teknisk beskyttelse af `main`. |
| **Automatisk opdatering af afhængigheder** | CI/CD Engineer / RM | Brug værktøjer som Renovate eller Dependabot. RM kan godkende mindre rettelser og automatiske sikkerhedspatches. |
| **Vulnerability Management** | Release Manager (RM) | Ansvarlig for modtagelse af sikkerhedsrapporter (VDP) og uddelegering af udbedring som hastesager til leverandører. |

---

# 🧪 Kvalitetssikring & Community

| Aktivitet | Rolle | Best Practice |
|:---|:---|:---|
| **Teststrategi og testkode** | QA Engineer / Test Automation Specialist | Brug test-first/TDD. Adskil unit, integration og e2e tests. Verifikation sker optimalt via en test-faggruppe. |
| **Funktionsreview og verifikation** | Product Owner (PO) | Endelig godkendelse af tilføjelser ud fra acceptance kriterier og "Definition of Done" (IKKE kode-review). |
| **Kvalificering af behov** | Product Owner & Release Manager | Løbende screening af indkomne issues. PO prioriterer user-stories der leverer værdi, mens RM validerer teknisk modenhed og release-parathed før opgaverne sættes i gang. |
| **Dokumentationsstyring** | Technical Editor (TE) | Reviewer PRs for dokumentationskvalitet. PO/RM merger som udgangspunkt kun, hvis TE har givet "OK". |
| **Community Management** | Community Manager (CM) | Håndterer Code of Conduct, issue-skabeloner og brugeradgang. Sikrer god tone og uddanner i brug af trackeren. |

---

# 🛠️ Produktionsdrift

| Aktivitet | Rolle | Best Practice |
|:---|:---|:---|
| **Klargøring af produktionsmiljøer** | Driftsoperatør | Brug Infrastructure-as-Code (Ansible, Terraform) for konsistens og sporbarhed. |
| **Konfiguration af sidecars/apps** | DevOps-specialist / Driftsoperatør | Hold konfiguration versioneret og miljøspecifik. Anvend standard deklarative formater. |
| **Udrulning til produktion** | Driftsoperatør | Automatisér med CI/CD pipelines og brug blue/green eller canary deployment-strategier. |
| **Overvågning og Observability** | Driftsoperatør | Brug standard observability-værktøjer (f.eks. CNCF OpenTelemetry). |

---

### 📚 Læs mere

> - 📘 [Linux Foundation – Open Source Guides](https://www.linuxfoundation.org/resources/open-source-guides)  
> - 📘 [Open Source Guides – Leadership & Governance](https://opensource.guide/leadership-and-governance/)  
> - 📘 [OS2 – Strategi for Open Source Governance](https://os2.dk)