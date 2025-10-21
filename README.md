# PFE-DevOps-Kais-CI-CD
# 🚀 Projet de Fin d'Études – Mise en place d’un Workflow CI/CD avec Backup et Monitoring

## 👨‍💻 Réalisé par
**Kais OUERIEMMI**  
Étudiant en Ingénierie Logicielle et Systèmes d’Information  
École Polytechnique de Sousse – Tunisie  
📅 Février – Juin 2025  
🏢 Entreprise d’accueil : **Ulmus (Groupe 3S)**

---

## 🎯 Objectif du projet

L’objectif de ce projet est de **concevoir et implémenter une chaîne DevOps complète (CI/CD)** intégrant :
- L’**intégration continue (CI)** avec Jenkins et GitLab,
- Le **déploiement continu (CD)** vers un cluster Kubernetes,
- L’**analyse de qualité du code** (SonarQube),
- La **gestion des artefacts** (Nexus),
- Le **scan de sécurité** (Trivy),
- La **supervision et la visualisation** (Prometheus, Grafana, ELK),
- La **sauvegarde et la restauration automatiques** (Velero + MinIO).

Ce projet s’inscrit dans une démarche d’**automatisation**, de **sécurisation** et de **fiabilisation** du cycle de vie logiciel.

---

## 🧩 Architecture Globale

L’infrastructure repose sur une **architecture hybride** combinant :
- **Proxmox VE** pour la virtualisation et l’hébergement local des services DevOps (Jenkins, SonarQube, Nexus, GitLab, etc.)
- **AWS EC2** pour l’hébergement du cluster Kubernetes et des services de supervision.

### 🗺️ Schéma simplifié de l’architecture
[ Développeur ]
↓
[ GitLab ]
↓
[ Jenkins CI ]
↓
[ SonarQube ] → [ Nexus ]
↓
[ Kubernetes (AWS) ]
↓
[ Prometheus | Grafana | ELK | Velero ]


---

## ⚙️ Technologies et outils utilisés

| Domaine | Outils / Technologies |
|----------|-----------------------|
| **Virtualisation** | Proxmox VE |
| **Versionning & SCM** | Git, GitLab |
| **CI/CD** | Jenkins, ArgoCD |
| **Conteneurisation** | Docker, Kubernetes |
| **Infrastructure as Code** | Terraform |
| **Analyse de code** | SonarQube |
| **Sécurité** | Trivy |
| **Gestion d’artefacts** | Nexus Repository |
| **Supervision** | Prometheus, Grafana |
| **Logging** | ELK Stack (Elasticsearch, Logstash, Kibana) |
| **Sauvegarde** | Velero + MinIO |
| **Monitoring applicatif** | Spring Boot Actuator |

---

## 📅 Gestion de projet – Méthodologie Scrum

Le projet a été conduit selon la **méthodologie agile Scrum**, découpée en sprints :

| Sprint | Période | Objectifs principaux |
|--------|----------|----------------------|
| **Sprint 0** | Analyse & préparation | Étude de l’existant, définition des besoins, planification |
| **Sprint 1** | Infrastructure | Mise en place de l’environnement Proxmox + Terraform |
| **Sprint 2** | CI/CD | Déploiement et intégration des outils Jenkins, GitLab, SonarQube, Nexus |
| **Sprint 3** | Monitoring & Backup | Configuration de Prometheus, Grafana, ELK, Velero |
| **Sprint 4** | Finalisation | Tests, validation, rédaction du rapport et documentation |

---

## 🔁 Workflow CI/CD

1. **Développeur** pousse le code sur GitLab  
2. **Jenkins** déclenche automatiquement le pipeline CI  
3. **SonarQube** analyse la qualité du code  
4. **Trivy** scanne les vulnérabilités dans les images Docker  
5. **Nexus** stocke les artefacts générés (builds, images)  
6. **Jenkins/ArgoCD** déploie sur le cluster Kubernetes  
7. **Prometheus** collecte les métriques, **Grafana** les affiche  
8. **Velero** effectue des sauvegardes planifiées sur MinIO  
9. **ELK** centralise les logs applicatifs et système

---

## 🧠 Détails techniques

### 🔧 Jenkins
- Intégré avec **GitLab Webhooks**
- Pipelines multibranch automatisés
- Étapes : build → test → analyse → artefact → déploiement

### 📦 Nexus
- Gestion centralisée des artefacts Maven et Docker
- Versionning automatique

### 🔍 SonarQube
- Vérification du **code smell**, **coverage** et **duplications**
- Qualité du code mesurée avant chaque merge

### 🔐 Trivy
- Scan automatique des images Docker dans le pipeline
- Génération de rapports HTML archivés

### ☁️ Kubernetes (AWS)
- Cluster EC2 configuré avec **kubectl + Helm**
- Déploiement automatisé via Jenkins et ArgoCD

### 🧭 Monitoring et Logs
- **Prometheus** : collecte des métriques depuis `/actuator/prometheus`
- **Grafana** : tableaux de bord personnalisés (CPU, mémoire, containers)
- **ELK** : analyse centralisée des logs applicatifs et système

### 💾 Backup & Restore
- **Velero** planifie et exécute les sauvegardes quotidiennes du cluster
- Sauvegardes stockées dans **MinIO** (compatible S3)

---

## 📊 Résultats obtenus

- ✅ Automatisation complète du pipeline CI/CD  
- ✅ Réduction du temps de déploiement de **70 %**  
- ✅ Supervision et alerting centralisés  
- ✅ Sauvegardes automatiques avec restauration testée  
- ✅ Amélioration significative de la **qualité du code**  

---

## 🧾 Structure du projet

PFE-DevOps-Kais-CI-CD/
│
├── backend/ # Application Java (Spring Boot)
├── frontend/ # Application Angular
├── jenkins/ # Pipelines Jenkinsfile
├── k8s/ # Manifests Kubernetes YAML
├── monitoring/ # Configurations Prometheus, Grafana
├── backup/ # Scripts Velero & MinIO
├── terraform/ # Déploiement de l’infrastructure
├── docs/ # Documentation et rapport PDF
└── README.md # Documentation principale



---

## 🧰 Installation et utilisation

### 📥 Cloner le projet
```bash
git clone https://github.com/kaisoueriemmi/PFE-DevOps-Kais-CI-CD.git
cd PFE-DevOps-Kais-CI-CD




