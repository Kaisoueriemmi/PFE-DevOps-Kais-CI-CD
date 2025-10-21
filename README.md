# 🚀 Projet de Fin d’Études – Mise en place d’un Workflow CI/CD avec Supervision et Sauvegarde

## 👨‍💻 Auteur
**Kais OUERIEMMI**  
Étudiant en Ingénierie Logicielle et Systèmes d’Information  
🎓 École Polytechnique de Sousse – Tunisie  
🏢 Entreprise d’accueil : **Ulmus (Groupe 3S)**  
📅 Février – Juin 2025  

---

## 🎯 Résumé du projet

Ce projet s’inscrit dans une démarche de transformation DevOps visant à **automatiser l’intégration et le déploiement des applications**, tout en assurant leur **supervision** et leur **sauvegarde automatique**.  
L’objectif principal est de concevoir un **pipeline CI/CD complet**, couvrant toutes les étapes du cycle de vie applicatif :  
du **build** à la **supervision**, en passant par la **qualité du code**, la **sécurité**, et la **sauvegarde des environnements**.

---

## 🧩 Objectifs du projet

### 🎯 Objectif principal
Mettre en place une **chaîne CI/CD complète** pour le déploiement automatisé d’applications, intégrant les dimensions de **qualité**, **sécurité**, **supervision** et **backup**.

### 🧱 Objectifs spécifiques
- Déployer une infrastructure virtuelle sur **Proxmox VE**.  
- Automatiser le provisioning via **Terraform**.  
- Configurer un pipeline **CI/CD** avec **GitLab** et **Jenkins**.  
- Intégrer l’analyse de code (**SonarQube**) et le scan de sécurité (**Trivy**).  
- Gérer les artefacts avec **Nexus Repository**.  
- Déployer sur un cluster **Kubernetes (AWS EC2)**.  
- Superviser avec **Prometheus** et **Grafana**.  
- Centraliser les logs avec la **stack ELK**.  
- Sauvegarder et restaurer les environnements via **Velero + MinIO**.

---

## ⚙️ Architecture globale

L’architecture repose sur une **infrastructure hybride** combinant :
- **Proxmox (local)** pour les services de build et d’intégration (Jenkins, GitLab, SonarQube, Nexus, Portainer).  
- **AWS (cloud)** pour le déploiement des applications Kubernetes et la supervision distante.

### 🖼️ Schéma d’architecture
*(À insérer : `docs/architecture.png`)*

[ Développeur ]
↓
[ GitLab ]
↓
[ Jenkins ]
↓
[ SonarQube ] → [ Trivy ] → [ Nexus ]
↓
[ ArgoCD / Kubernetes ]
↓
[ Prometheus | Grafana | ELK | Velero ]


---

## 🧰 Technologies utilisées

| Domaine | Outil / Technologie | Rôle |
|----------|---------------------|------|
| Virtualisation | Proxmox VE | Hébergement local des services |
| IaC | Terraform | Provisionnement automatique |
| Gestion de code | GitLab | SCM et déclenchement CI |
| CI/CD | Jenkins | Build, test, analyse, déploiement |
| Qualité du code | SonarQube | Analyse et reporting |
| Sécurité | Trivy | Scan de vulnérabilités |
| Artefacts | Nexus | Stockage d’images et dépendances |
| Orchestration | Kubernetes | Déploiement des applications |
| Déploiement continu | ArgoCD, Helm | GitOps et automation |
| Supervision | Prometheus, Grafana | Collecte et visualisation des métriques |
| Logs | ELK Stack | Centralisation et analyse |
| Sauvegarde | Velero + MinIO | Backup & restore |
| Monitoring applicatif | Spring Boot Actuator | Export de métriques vers Prometheus |

---

## 🧠 Méthodologie de travail

Le projet a été mené selon la **méthodologie Agile Scrum**, répartie en **4 sprints** :

| Sprint | Contenu principal |
|--------|------------------|
| Sprint 0 | Analyse des besoins, étude de l’existant |
| Sprint 1 | Mise en place de l’infrastructure (Proxmox + Terraform) |
| Sprint 2 | Mise en place du pipeline CI/CD (GitLab, Jenkins, SonarQube, Nexus, Kubernetes) |
| Sprint 3 | Supervision, visualisation et sauvegarde (Prometheus, Grafana, ELK, Velero) |

---

## 🔁 Pipeline CI/CD

### Étapes principales :
1. **Commit du code source** sur GitLab  
2. **Build** et compilation du projet via Jenkins  
3. **Analyse SonarQube** (qualité du code)  
4. **Scan Trivy** (sécurité des images Docker)  
5. **Publication** de l’image sur **Nexus**  
6. **Déploiement automatique** sur Kubernetes via **ArgoCD/Helm**  
7. **Supervision** (Prometheus, Grafana)  
8. **Sauvegarde automatique** (Velero + MinIO)

---

## 📊 Supervision et observabilité

- **Prometheus** : collecte des métriques depuis les pods, Jenkins, Kubernetes et Spring Boot.  
- **Grafana** : visualisation via des dashboards dynamiques.  
- **ELK** : centralisation et analyse des logs applicatifs et systèmes.  
- **Alertmanager** : gestion des alertes.

---

## 💾 Sauvegarde et restauration

- **Velero** sauvegarde automatiquement les namespaces Kubernetes (base de données, volumes, configurations).  
- **MinIO** sert de stockage compatible S3.  
- **Tests de restauration** validés sur un environnement isolé.

---

## 📈 Résultats et bénéfices

- 🚀 Déploiement automatisé et reproductible  
- 🔍 Contrôle qualité du code en continu  
- 🧱 Supervision complète de l’infrastructure  
- 🛡️ Sauvegarde planifiée et restauration fiable  
- 💡 Réduction du temps de livraison de **70 %**  

---

## 🧾 Structure du dépôt

PFE-DevOps-Kais/
│
├── backend/ # Code source (Java Spring Boot)
├── frontend/ # Interface utilisateur (Angular)
├── jenkins/ # Pipelines Jenkins (Jenkinsfile)
├── kubernetes/ # Manifests YAML
├── terraform/ # Scripts d’infrastructure
├── monitoring/ # Configurations Prometheus/Grafana
├── backup/ # Configs Velero et MinIO
├── docs/ # Documentation et schémas
└── README.md # Documentation principale


---

## 🧰 Installation et utilisation

### 1️⃣ Cloner le projet
```bash
git clone https://github.com/kaisoueriemmi/PFE-DevOps-Kais.git
cd PFE-DevOps-Kais
2️⃣ Déployer l’environnement
docker-compose up -d

