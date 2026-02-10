# Pipeline d’Analyse de la Qualité des Données

Pipeline Python permettant de **détecter, prévenir et documenter les problèmes de qualité des données**.  
Le projet met en place des contrôles automatisés et versionnés afin d’intégrer la qualité directement dans le cycle de développement et de livraison des données.

---

## Tech Stack
- Python 3.10+
- pandas
- Great Expectations
- CLI (Command Line Interface)
- CI/CD (quality gates automatiques)

---

## Objectifs

- Détecter et prévenir les problèmes de qualité :
  - erreurs de schéma  
  - valeurs manquantes ou invalides  
  - doublons  
  - incohérences métier  

- Standardiser les contrôles via des **expectations versionnées**
- Automatiser la validation à chaque **lot de données** et à chaque **Pull Request**
- Générer une **documentation de qualité (Data Docs)**
- Alerter automatiquement en cas d’échec (emailing)

---

## Architecture (Vue d’ensemble)

### Ingestion
Lecture des données depuis différentes sources :
- fichiers CSV / Parquet  
- bases de données  
- APIs  

→ Chargement dans un `pandas.DataFrame`

---

### Préparation
Phase de mise en conformité :
- typage des colonnes  
- normalisation des formats  
- enrichissements éventuels  

---

### Validation
Exécution d’un **Checkpoint Great Expectations** :
- suites d’expectations versionnées
- validation automatisée des datasets
- génération des résultats de validation

---

### Reporting
- Génération des **Data Docs (HTML)**  
- Export des métriques de qualité (JSON)  
- Traçabilité des validations

---

### Quality Gate (CI/CD)
Le pipeline agit comme un **contrôle qualité automatisé** :
- le job échoue si les validations échouent  
- blocage possible d’une PR ou d’un déploiement  
- envoi d’alertes automatiques en cas d’erreur

---

## Cas d’usage
- Intégration dans un workflow Data Engineering
- Surveillance de pipelines ETL/ELT
- Industrialisation de la qualité des données

---

## 👨‍💻 Auteur
Robin Crifo
