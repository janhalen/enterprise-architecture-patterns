---
layout: default
title: "🌐 Digital Suverænitet – Solution Landscape"
summary: "Et højniveau overblik over en løskoblet, open source-baseret løsning, der understøtter digital suverænitet i praksis."
author: "Jan Maack Kjerbye"
date: "2025-09-09"
tags: [styring, linux, open source, OS2, FleetDM, samarbejde]
status: "Udkast"
parent: "Proposals"
published: true
---

{% include header_metadata.html %}

Udkast
{: .label .label-yellow }


<style>
.value-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
  margin: 2rem 0;
}
.value-card {
  background: #f5f5f5;
  border-left: 4px solid #4caf50;
  padding: 0.75rem;
  border-radius: 6px;
}
.value-card h3 {
  margin-top: 0;
  font-size: 1rem;
  color: #2e7d32;
}
.value-card p {
  font-size: 0.65rem;
  line-height: 1.4;
  margin: 0.5rem 0 0;
}
</style>

<div class="value-grid">
  <div class="value-card">
    <h3>🔐 Kontrol over data</h3>
    <p>Data opbevares og behandles lokalt eller på betroede infrastrukturer. Ingen uautoriseret tredjepartsadgang.</p>
  </div>
  <div class="value-card">
    <h3>🔍 Transparens</h3>
    <p>Kildekode og systemadfærd er synlig og kan verificeres. Ingen skjulte processer eller black boxes.</p>
  </div>
  <div class="value-card">
    <h3>🔗 Interoperabilitet</h3>
    <p>Standardiserede API’er og datamodeller sikrer samspil med andre systemer – både offentlige og private.</p>
  </div>
  <div class="value-card">
    <h3>🧩 Løskobling</h3>
    <p>Løsningen er sammensat af udskiftelige komponenter. Ingen leverandørlåsning. Let at tilpasse og udvide.</p>
  </div>
  <div class="value-card">
    <h3>⚖️ Retten til at vælge</h3>
    <p>Organisationen vælger selv leverandører til hosting, udvikling og vedligehold – uden afhængighed af kommercielle cloud-platforme.</p>
  </div>
  <div class="value-card">
    <h3>📜 Lovlighed og ansvarlighed</h3>
    <p>Automatiseret dokumentation af databehandling og konsekvensanalyse. Beviser for lovlighed – ikke blot tro & love.</p>
  </div>
</div>

---

```mermaid
flowchart TB
 subgraph Clients["👥 Anvender typer"]
        school(["💻 Børn"])
        office(["🖥 Medarbejdere"])
        rpi(["📱 Borgere"])
  end
 subgraph Backend["🧠 Backend Services"]
    direction RL
        nextcloud["🤝 Samarbejdsplatform"]
        canvas["📚 Læringsplatform"]
        signage["📺 Indholdsleverance"]
        groupware["📆 Kommunikation & Ressourcestyring"]
  end
 subgraph Common["⚙️ Fælles Services"]
        integration["🔁 Integrationer"]
        deployment["🔃 Udrulning"]
        observability["👁 Overvågning"]
        auth["🔐 Adgangsstyring"]
        fleet["🛢 Konfigurationsstyring"]
        compliance[" ⚖️ Compliance motor "]
  end
 subgraph Cluster["☁️ Kubernetes Cluster"]
        Backend
        Common
  end
 subgraph DataSources["📂 Datakilder"]
        git["🗃 Versionstyret <br>Kilde Kode"]
        municipal["📇 Fælles Kommunale<br>Data"]
        systems["🔆 Fagsystemer"]
  end
    canvas ~~~ nextcloud
    groupware ~~~ signage
    git --> fleet & deployment
    municipal --> integration
    systems --> integration
    integration --> auth & observability & compliance
    deployment --> Backend
    fleet --> Clients
    Backend <--> integration
    Clients --> Backend

    rpi@{ shape: rounded}
    integration@{ shape: trap-b}
    n1@{ shape: rect}
    git@{ shape: cyl}
    systems@{ shape: procs}
     school:::Client
     office:::Client
     rpi:::Client
     nextcloud:::Service
     canvas:::Service
     signage:::Service
     groupware:::Service
     integration:::Infra
     deployment:::Infra
     observability:::Infra
     auth:::Infra
     fleet:::Infra
     compliance:::Infra
     git:::Data
     municipal:::Data
     systems:::Data
    classDef Client fill:#E3F2FD,stroke:#90CAF9,color:#0D47A1
    classDef Service fill:#FFF3E0,stroke:#FFCC80,color:#BF360C
    classDef Infra fill:#E8F5E9,stroke:#A5D6A7,color:#1B5E20
    classDef Data fill:#DEFFF8,stroke:#46EDC8,color:#378E7A 
    style Backend stroke:none
    style Common stroke:none,fill:powderblue
    style Clients stroke:none
    style Cluster stroke:none
    style DataSources stroke:none
```