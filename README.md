# 🏗️ Projet d’Architecture de Données – Stripe Jedha : Stripe Business Case

## 📘 Présentation générale
Ce projet présente la **conception d’une architecture de données complète pour Stripe**, acteur majeur de la FinTech.  
L’objectif est de **concevoir une infrastructure unifiée, scalable et conforme**, capable d’intégrer et de gérer les systèmes de données **transactionnels (OLTP)**, **analytiques (OLAP)** et **non structurés (NoSQL)**.

Ce dépôt contient exclusivement les **documents techniques et schémas d’architecture** décrivant le fonctionnement global du système, du pipeline de données jusqu’à l’intégration des modèles d’intelligence artificielle.

---

## 🧱 Structure du projet

| Fichier / Dossier | Description |
|--------------------|-------------|
| `1_Comprehensive_Data_Architecture_Diagram.drawio` | Schéma global d’architecture – intégration OLTP, OLAP et NoSQL. + docx |
| `2_ERD_for_OLTP_System.drawio` | Modèle relationnel (ERD) du système transactionnel PostgreSQL. + docx |
| `3_Schema_Design_for_OLAP_System.drawio` | Schéma Snowflake OLAP (tables de faits, dimensions, stratégies d’agrégation). + docx |
| `4_NoSQL_Data_Model.drawio` | Modèle de données MongoDB (collections, indexation, embedding vs referencing). + docx |
| `5_Data_Pipeline_Architecture.docx` | Architecture des pipelines ELT (Airbyte, dbt, Airflow, Snowflake). |
| `6_Security_and_Compliance_Plan.docx` | Plan de sécurité et conformité (RGPD, PCI-DSS, CCPA). |
| `7_ML_Integration_Strategy.drawio` | Stratégie d’intégration du Machine Learning (MLflow, Evidently). + docx |
| `8_SQL_and_NoSQL_Queries.docx` | Exemples de requêtes analytiques et opérationnelles (Snowflake + MongoDB). |
| `LDS_Block_2_Lead.pptx` | Document de présentation du projet. |

---

## 🧩 Résumé de l’architecture

**Composants principaux**
- **OLTP (PostgreSQL – AWS RDS)** → Données transactionnelles (paiements, clients, marchands).  
- **NoSQL (MongoDB Atlas)** → Données semi-structurées : sessions, logs, feedbacks, features ML.  
- **OLAP (Snowflake)** → Entrepôt central pour l’analyse, la BI et les pipelines IA.  

**Workflow ELT**
1. **Airbyte** – Ingestion des données (batch + CDC).  
2. **dbt** – Transformation, tests et modélisation (staging → core → marts).  
3. **Airflow** – Orchestration et planification des pipelines.  
4. **Snowflake** – Stockage analytique et agrégations.  

**Machine Learning**
- Entraînement distribué via **Ray / EKS**, suivi par **MLflow**.  
- Déploiement en **API FastAPI** pour le scoring temps réel.  
- Monitoring avec **Evidently** (drift et performance des modèles).  

---

## 🔐 Sécurité & conformité

- **Chiffrement** : AES-256 (au repos) et TLS 1.2+ (en transit).  
- **Contrôle d’accès (RBAC)** : rôles métiers distincts avec masquage dynamique.  
- **Isolation réseau** : VPC privé AWS (sous-réseaux ingestion / transformation / analyse).  
- **Conformité** : RGPD (Europe), PCI-DSS (paiements), CCPA (États-Unis).  
- **Traçabilité** : audit logs, alertes sécurité, tableaux de bord de conformité.

---

## 📊 Livrables principaux

1. **Schéma global d’architecture des données** (Draw.io)  
2. **Modèles OLTP, OLAP et NoSQL**  
3. **Architecture des pipelines de données (ELT)**  
4. **Plan de sécurité et conformité**  
5. **Stratégie d’intégration du Machine Learning**  
6. **Exemples de requêtes SQL et NoSQL**

Chaque document décrit une brique spécifique de l’architecture et son rôle dans la chaîne de valeur des données.

---

## 🎯 Objectifs pédagogiques

- Concevoir une **architecture de données complète** intégrant OLTP, OLAP et NoSQL.  
- Mettre en œuvre les **bonnes pratiques ELT** (Airbyte, dbt, Airflow).  
- Garantir la **sécurité, la conformité et la gouvernance** dans un contexte FinTech.  
- Démontrer l’intégration du **Machine Learning** dans une infrastructure distribuée et monitorée.

---

## 🧠 Auteur

**Aurélien Chalm**  
🎓 *Certification Lead Data Science & Engineering – Jedha*  
📍 *Projet d’architecture de données – Stripe (FinTech)*  

---

## 📄 Licence

Ce projet est partagé à des fins **pédagogiques et de démonstration**.  
Tous les noms et marques mentionnés (Stripe, Snowflake, MongoDB, etc.) demeurent la propriété de leurs détenteurs respectifs.