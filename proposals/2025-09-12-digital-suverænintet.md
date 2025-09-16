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

## Strategiske mål

{% raw %}
<style>
.value-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
  margin: 2rem 0;
}

.value-card {
  display: flex;
  flex-direction: column;
  justify-content: center; /* vertikal centrering */
  align-items: center;     /* horisontal centrering */
  text-align: center;
  background: #e8f5e9;
  border-left: 4px solid #4caf50;
  padding: 1rem;
  border-radius: 6px;
  min-height: 180px; /* sikrer ens højde */
  transition: all 0.2s ease-in-out;
}

.value-card:hover {
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  transform: translateY(-2px);
}

.value-card h3 {
  margin: 1;
  font-size: 0.70rem;
  color: #2e7d32;
}

.value-card p {
  font-size: 0.55rem;
  line-height: 1.6;
  margin: 0.5rem 0 0;
  max-width: 90%;
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
{% endraw %}


---
## Løsningslandskab

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
        groupware["📆 Kommunikation <br>& Ressourcestyring"]
        meetchat["🧑‍💻 Virtuelle møder"] 
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
    git@{ shape: cyl}
    systems@{ shape: procs}
     school:::Client
     office:::Client
     rpi:::Client
     nextcloud:::Service
     canvas:::Service
     signage:::Service
     groupware:::Service
     meetchat:::Service
     integration:::Service
     deployment:::Service
     observability:::Service
     auth:::Service
     fleet:::Service
     compliance:::Service
     git:::Data
     municipal:::Data
     systems:::Data


classDef Client fill:PowderBlue,stroke:LightSteelBlue,color:DarkSlateGray
classDef Service fill:PaleGoldenRod,stroke:gold,color:DarkSlateGray
classDef Data fill:PowderBlue,stroke:LightSteelBlue,color:DarkSlateGray

style Backend stroke:none,fill:MintCream
style Common stroke:none,fill:Mintcream
style Clients stroke:none,fill:MintCream
style Cluster stroke:none,fill:WhiteSmoke
style DataSources stroke:none,fill:MintCream 

```

## Applikationer

{% raw %}
<style>

/* Header styling */
.table-wrapper thead th {
  background-color: #f1f8e9;
  color: #2e7d32;
  padding: 0.75rem;
  border: 1px solid #ddd;
  text-align: left;
}

/* Cell styling */
.table-wrapper td {
  padding: 0.75rem;
  border: 1px solid #ddd;
  vertical-align: top;
}

</style>
{% endraw %}

| Kategori i diagram              | Funktion                                | Type (teknisk)                             | Anbefalet komponent                          | Runners-up                                      |
|--------------------------------|-----------------------------------------|--------------------------------------------|----------------------------------------------|-------------------------------------------------|
| Kommunikation & Ressourcestyring | Email, Kalender, Kontakter              | Groupware backend (SMTP, IMAP, CalDAV, CardDAV) + webklient | [Grommunio (Gromox + Web)](https://grommunio.com/features/) | OpenXchange <small>(OpenDesk)</small>                         |
| Virtuelle møder                | Videomøder                              | WebRTC-server og webklient                 | [Jitsi Meet](https://jitsi.org/jitsi-meet/)  | Nextcloud Talk                                  |
| Samarbejdsplatform             | Dokumentredigering (tekst, regneark, præsentationer)                   | Online kontorpakke  | [Collabora Online <small>(OpenDesk)</small>](https://www.collaboraonline.com/) | La Suite Numérique, CryptPad                 |
| Samarbejdsplatform             | Dokumentdeling                         | WebDAV-server og webklient                 | [Nextcloud <small>(OpenDesk)</small>](https://nextcloud.com/features/)  | OwnCloud                                        |
| Læringsplatform                | Undervisning                            | Learning Management System (LMS) server og webklient | [Canvas LMS](https://www.instructure.com/canvas) | Moodle, Open edX                                |
| Kommunikation                  | Korte beskeder                          | Realtime messaging server og webklient     | [Zulip](https://zulip.com/features/)          | Matrix + Element <small>(OpenDesk)</small>                    |
