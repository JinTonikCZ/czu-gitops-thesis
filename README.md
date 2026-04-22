# Implementace GitOps pro správu cloudové infrastruktury

Tento repozitář slouží jako veřejná technická prezentace diplomové práce zaměřené na implementaci GitOps přístupu pro správu cloudové infrastruktury s využitím Kubernetes a Argo CD.

## O práci

Diplomová práce se zabývá principy GitOps, jejich porovnáním s tradiční správou infrastruktury a praktickým ověřením nasazení v Kubernetes prostředí.  
Hlavním cílem je ukázat, jak lze pomocí deklarativního přístupu, Git repozitáře a automatické synchronizace řídit infrastrukturu moderním a auditovatelným způsobem.

## Hlavní cíle

- analyzovat principy GitOps
- porovnat GitOps s tradiční správou infrastruktury
- popsat roli nástrojů jako Argo CD, Flux, Helm a Terraform
- navrhnout postup zavedení GitOps do organizace
- prakticky ověřit synchronizaci změn a self-healing v Kubernetes

## Použité technologie

- Kubernetes
- Argo CD
- Helm
- Git / GitHub
- YAML manifesty
- MicroK8s / testovací cluster

## Struktura repozitáře

- `thesis/` – finální verze diplomové práce a abstrakt
- `docs/` – technická dokumentace a shrnutí klíčových částí práce
- `diagrams/` – architektonická schémata, GitOps workflow a synchronizační diagramy
- `screenshots/` – screenshoty z praktické demonstrace
- `references/` – odkazy na související zdroje a materiály

## Praktická část

Praktická část práce demonstruje GitOps workflow v Kubernetes prostředí pomocí Argo CD.

Byly ověřeny zejména tyto scénáře:

1. Git jako **single source of truth**
2. Změna konfigurace pomocí commitu do Git repozitáře
3. Detekce změny v Argo CD a přechod do stavu `OutOfSync`
4. Synchronizace aplikace do stavu `Synced / Healthy`
5. Ověření **self-healing** po manuálním zásahu mimo Git

## GitOps workflow

1. Konfigurace aplikace je uložena v Git repozitáři  
2. Argo CD sleduje rozdíl mezi Git a stavem clusteru  
3. Při změně konfigurace je aplikace označena jako `OutOfSync`  
4. Následně dojde k synchronizaci změn do clusteru  
5. Výsledný stav je `Synced / Healthy`  
6. Při driftu konfigurace proběhne automatická náprava

## Výsledky

- úspěšná synchronizace změny počtu replik
- potvrzení reconciliation loop v Argo CD
- automatická obnova požadovaného stavu po manuálním zásahu
- potvrzení vhodnosti GitOps pro správu cloudové infrastruktury

## Praktický demo repozitář

Praktická implementace GitOps scénáře je dostupná také zde:

[`gitops-demo`](https://github.com/JinTonikCZ/gitops-demo)

## Autor

**Pavel Dikan**  
Česká zemědělská univerzita v Praze  
Obor Informatika

## Poznámka

Tento repozitář slouží jako technický showcase diplomové práce a demonstračního GitOps řešení pro správu infrastruktury.
