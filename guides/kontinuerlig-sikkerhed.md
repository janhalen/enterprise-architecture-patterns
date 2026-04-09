---
layout: default
title: 🛡️ Kontinuerlig sikkerhed og vedligehold
parent: Guides

---

# 🛡️ Kontinuerlig sikkerhed og vedligehold
_En simpel automatiseret tilgang til beskyttelse af softwareprojekter_

###### 👤 Jan Maack Kjerbye - Enterprise Arkitekt @ os2.eu

## Fra reaktiv til proaktiv sikkerhed

> Mange organisationer investerer i periodiske, manuelle kodegennemgange, såkaldte "code-reviews". Mens dette er værdifuldt, kan disse statiske øjebliksbilleder efterlade systemer sårbare i mange måneder imellem gennemgangene. Ved at omprioritere det samme budget hen imod kontinuerlig sikkerheds vedligeholdelse kan projekter opnå nær realtidsbeskyttelse og automatisk overholdelse af cybersikkerhedskrav.



    Aktiver den indbyggede (ofte ubrugte) automatiserings funktionalitet i git repositoriet til overholdelse af cybersikkerhedsstandarder

- **Sikkerhedshuller lappes hurtigt**:

     Erstat måneders lange sårbarhedsvinduer med 24/7 overvågning og nær-realtids mitigering

- **Samme investering, kontinuerlig værdi**:

    Opnå kontinuerlig beskyttelse og tag ejerskab over kildekoden ved at ompriotere budgetmidler fra dyre statiske enkeltrapporter etablering af et vedligeholdelses team og høst gevinsterne ved automatisering.

- **Objektive standarder**:

    Håndhæv en neutral teknisk gennemgang der ikke kræver adgang til at kunne auditere eller revidere udviklings leverandørens interne systemer


## Tre Enkle Trin til Implementering

### 1. ORGANISERING
**Opret et neutralt vedligeholdelsesteam**

Engager platform-ingeniører fra en uafhængig tredjepart til at danne et dedikeret såkaldt "maintainer-team" fokuseret på at automatisere sikkerhed og gennemsigtighed i projektets git repositorie.

### 2. PROCESS ETABLERING
**Etabler en sikker gennemgangsproces**

_Sammen med vedligeholdelses teamet:_

Definer klare kriterier for kodegodkendelse, herunder krav om pull request-gennemgange, beståede statuskontroller, rimelige størrelsesgrænser for pull requests samt klare beskrivelseskrav for grundig, effektiv kodegennemgang.

### 3. TEKNISK IMPLEMENTERING
**Aktiver Kontinuerlig Sikkerhedsscanning**

_Lad vedligeholdelsesteamet:_

* Konfigurere kriterierne fra ovenstående punkt som beskyttelsesregler på git repositoriet for at sikre håndhævelse af de aftalte krav.
* Evaluere og implementere passende sikkerhedsscanningsværktøjer ved at aktivere automatiserings funktionaliteten i projektets git repositorie, uafhængigt af softwareleverandørens infrastruktur.

## Fremadrettet

Ved at behandle sikkerhed som en løbende proces frem for en periodisk begivenhed, kan projektet skabe en mere modstandsdygtig softwareforsyningskæde samtidig med at der opretholdes et stærkt tillidsfuldt samarbejde med betroede partnere. Denne udvikling i leverancemodellen imødegår aktuelle cybersikkerhedsudfordringer med dokumenterede, standardiserede praksisser.

---

###### Læs mere:


######  [The OWASP® Foundation - **Free for Open Source Application Security Tools**](https://owasp.org/www-community/Free_for_Open_Source_Application_Security_Tools) 

###### [nist.gov - **Secure Software Development Framework (SSDF) Version 1.1: Recommendations for Mitigating the Risk of Software Vulnerabilities**](https://csrc.nist.gov/pubs/sp/800/218/final)

###### [cisecurity.org **CIS Critical Security Controls v16 - Control 16: Application Software Security**](https://cas.docs.cisecurity.org/en/latest/source/Controls16/)

###### [GitHub.com - **Understanding GitHub Actions**](https://docs.github.com/en/actions/get-started/understand-github-actions)

######  [GitHub.com - **About pull requests**](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

######  [GitHub.com - **About protected branches**](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)

###### [Styrelsen for Samfundssikkerhed - **Trusselsvurdering af cybertruslen mod leverandører**](https://samsik.dk/wp-content/uploads/2025/10/Trusselsvurdering-cybertruslen-mod-leverandoerer-2020.pdf)

######  [sikkerdigital.dk - **Cybersikkerhed i leverandørforhold**](https://www.sikkerdigital.dk/Media/637873353791444653/Cybersikkerhed-i-leverand%C3%B8rforhold-2022.pdf)

###### [Styrelsen for Samfundssikkerhed - **Vejledning til implementering af cybersikkerhedsforanstaltninger**](https://samsik.dk/wp-content/uploads/2025/08/Vejledning-til-implementering-af-cybersikkerhedsforanstaltninger.pdf)