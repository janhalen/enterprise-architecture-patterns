---
layout: default
title: "Referencearkitektur for dansk skoleløsning"
author: "Jan Maack Kjerbye"
date: "18-08-2025"
status: "Udkast" 
parent: "Proposals"
published: false # [Skal siden vises på sitet? false = nej]
---

# Referencearkitektur for dansk open source skoleløsning

📆 _Last updated: {{ site.time | date: '%B %d, %Y' }}_

Udkast  
{: .label .label-yellow }

## Baggrund

For at understøtte strategiske beslutninger og sikre en skalerbar, vedligeholdelsesvenlig løsning, er det afgørende at etablere en referencearkitektur (herfter "RA") med klare anbefalinger til teknologivalg.

Den hidtidige tilgang, hvor teknologivalg er blevet undladt i arkitekturen, har skabt usikkerhed og manglende retning. Uden en tydelig italesættelse risikerer projektet at blive præget af forvirring og strategisk misrepræsentation – med potentielle konsekvenser for både fremdrift og forankring.

## Formål og forventet effekt

Denne indsats har til formål at etablere en strategisk funderet RA, der skaber klarhed omkring teknologivalg.

De ønskede effekter af indsatsen omfatter:

- **Styrket beslutningsgrundlag** gennem tydelige teknologiske anbefalinger  
- **Reduceret strategisk usikkerhed** ved at italesætte og afgrænse arkitekturens teknologiske rammer  
- **Øget alignment** mellem aktører
- **Bedre kvalitet og konsistens** i løsninger på tværs af deltagende myndigheder
- **Hurtig onboarding** af samarbejdspartnere via en fælles arkitekturmæssig referenceramme


## Strategisk kontekst

Den RA, der præsenteres her, er bygget oven på principper og komponenter fra Cloud Native Computing Foundation (CNCF). CNCF udgør den globale standard for Kubernetes-baseret infrastruktur.

Med CNCF som grundlag leverer store offentlige myndigheder kritisk NIS2, ISO-27001 og GDPR compliant infrastruktur til alt fra patientjournaler ved de svenske sundhedsmyndigheder til styring af software udrulning til F-16 kampfly og flådefartøjer ved U.S. Department of Defense.

Læs mere: cncf.io/case-studies/

## Strategisk kontekst

Den referencearkitektur, der præsenteres her, er bygget oven på principper og komponenter fra Cloud Native Computing Foundation (CNCF), som udgør den globale standard for Kubernetes-baseret infrastruktur.

Med CNCF som fundament leverer store offentlige myndigheder kritisk, NIS2-, ISO-27001- og GDPR-compliant infrastruktur: lige fra de svenske sundhedsmyndigheders patientjournaler, til U.S. Department of Defense til sikring af softwareudrulning på F-16 kampfly og flådefartøjer.

Læs mere: [cncf.io/case-studies](https://www.cncf.io/case-studies/dod/)

Med andre ord, det er en bredt anvendt og genbrugelig RA med et stærkt strategisk fit til et projekt som os2skole.

## Komponenter

### Infrastruktur

| Funktion                | Valgt komponent                          | Runners-up                                      |
|-------------------------|-------------------------------------------|-------------------------------------------------|
| Observability           | Prometheus, Grafana, Loki, OpenTelemetry | Thanos, Jaeger, Tempo                           |
| Security & Compliance   | OPA, Falco, Kyverno                      | KubeArmor, AppArmor, Gatekeeper                 |
| Identity Provider       | Authentik           | Keycloak, Zitadel, Nubus           
| Netværk                 | Cilium                                   | Calico, Weave Net                               |
| Storage                 | Longhorn                                 | Rook, OpenEBS                                   |
| Secrets & Config        | External Secrets Operator                | Sealed Secrets, Vault, SOPS                     |
| Service Discovery       | CoreDNS                                  | Consul                                          |
| Policy Enforcement      | Kyverno, OPA                             | Gatekeeper, Kubewarden                          |
| Runtime Security        | Falco                                    | KubeArmor, Sysdig Falco Enterprise              |
| Identity (Workload)     | SPIFFE/SPIRE                             | cert-manager, Istio SDS                         |

### Leverance

| Funktion                | Valgt komponent                          | Runners-up                                      |
|-------------------------|-------------------------------------------|-------------------------------------------------|
| GitOps                  | ArgoCD                                   | Flux, Jenkins X                                 |
| CI/CD                   | GitHub Actions                                   | Tekton, GitLab CI              |
| Packaging & Deployment  | Helm, Kustomize                          | Skaffold, Carvel, CNAB                          |
| Ingress Controller      | Traefik                                  | Contour, NGINX Ingress, HAProxy Ingress         |

