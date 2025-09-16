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

---

# 👨‍💻 Applikationsudvikling

| Aktivitet                                 | Rolle                          | Best Practice                                                                 |
|-------------------------------------------|--------------------------------|--------------------------------------------------------------------------------|
|  Nyudvikling af applikationskode           | Specialist-udvikler            | Modularisering og domain-driven design. Brug GitHub Issues og Pull Requests.  |

---

# ⚙️ Klargøring og leverance

| Aktivitet                                         | Rolle                        | Best Practice                                                                 |
|--------------------------------------------------|------------------------------|--------------------------------------------------------------------------------|
|  Udvikling af build-, package- og release-pipelines | CI/CD Engineer / DevOps Specialist | Brug declarative pipelines (f.eks. GitHub Actions). Hold pipelines versioneret og testbare. |
|  Vedligeholdelse af CI/CD og release-processer    | Release Manager              | Automatisér semantisk versionering og changelogs. Brug container-baseret builds for reproducerbarhed. |
|  Automatisk opdatering af afhængigheder    | CI/CD Engineer / DevOps Specialist     | Brug værktøjer som Renovate, Dependabot eller Poetry. Automatisér PRs med CI-tests og review workflows. |


---

# 🧪 Kvalitetssikring

| Aktivitet                                 | Rolle                          | Best Practice                                                                 |
|-------------------------------------------|--------------------------------|--------------------------------------------------------------------------------|
|  Udvikling af teststrategi og testkode     | QA Engineer / Test Automation Specialist | Brug test-first eller test-driven development. Adskil unit, integration og e2e tests. |
|  Vedligeholdelse og review af testkode     | QA Reviewer                    | Brug CI til automatisk testkørsel. Review testdækning og edge cases.         |
|  Triaging af issues og review af pull requests  |  Maintainers         | Brug labels, templates og automatisering. Prioritér og kategorisér issues. Involver relevante reviewers. |
|  Vedligehold og review af applikationskode | Maintainers     | Brug code review workflows og automatiserede linters/test. Adskil review fra udvikling. |


---

# 🛠️ Produktionsdrift

| Aktivitet                                 | Rolle            | Best Practice                                                                 |
|-------------------------------------------|------------------|--------------------------------------------------------------------------------|
|  Klargøring af produktionsmiljøer          | Driftsoperatør   | Brug Infrastructure-as-Code (f.eks. Ansible, Terraform) for konsistens og sporbarhed. |
|  Konfiguration af applikationer og sidecars | DevOps-specialist / Driftsoperatør |  Hold konfiguration versioneret og miljøspecifik. Anvand standard deklarative formater|
|  Udrulning af software til produktion      | Driftsoperatør   | Automatisér med CI/CD pipelines og brug blue/green eller canary deployment-strategier. |
|  Overvågning af systemer og services       | Driftsoperatør   | Brug standard observability-værktøjer (f.eks CNCF OpenTelemetry)   |

---

### 📚 Læs mere

> - 📘 [Linux Foundation – Open Source Guides](https://www.linuxfoundation.org/resources/open-source-guides)  
> - 📘  [Linux Foundation – Participating in Open Source Communities](https://www.linuxfoundation.org/resources/open-source-guides/participating-in-open-source-communities)  
> - 📘  [Open Innovation Projects – Key Roles in Open Source Projects](https://open-innovation-projects.org/blog/the-key-roles-in-open-source-projects-you-should-know-about)  
> - 📘  [Open Source Guides – Leadership & Governance](https://opensource.guide/leadership-and-governance/)  
> - 📘  [Linux Foundation – Improving your open source development impact](https://www.linuxfoundation.org/resources/open-source-guides/improving-your-open-source-developmen)

