# IBM x DeVinci Hackathon 2025 - Fraud Detection Track 🏦

[![IBM watsonx](https://img.shields.io/badge/IBM-watsonx.ai-blue)](https://www.ibm.com/watsonx)
[![Python](https://img.shields.io/badge/Python-3.x-green)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/ML-Classification-orange)](https://scikit-learn.org/)

## 🎯 À propos du projet

Ce dépôt contient le projet développé par l'**Équipe 10** lors du hackathon IBM x DeVinci **"Finance Track"** organisé du **5 au 7 novembre 2025** aux **Terrasses Campus**. 156 étudiants de 5e année DIA (Data Intelligence & AI) ont participé à cet événement intensif de 3 jours, répartis en 26 équipes de 6 personnes.

### 🎓 Équipe 10 - Finance Track

- **Antoine Richard** - Data Science & IA
- **Charles Perier** - Data Science & IA
- **Thomas Valesi** - Data Science & IA
- **Chloé De Wilde** - Data Science & IA
- **Nour Affes** - Data Science & IA
- **Romain Paupe** - Data Science & IA

## 📋 Contexte & Objectif

### Le Défi

Les institutions financières font face à des tentatives de fraude de plus en plus sophistiquées sur les cartes bancaires et les paiements en ligne. La détection rapide et précise de ces fraudes est critique pour protéger les clients et maintenir la confiance.

### L'Objectif du Track Finance

Développer un **modèle de Machine Learning de classification** capable de prédire si une transaction est frauduleuse (1) ou non (0).

Les trois éléments clés du défi :

1. **Concevoir et entraîner** un modèle ML performant capable de généraliser à de nouveaux clients
2. **Générer un fichier de soumission** au format requis contenant `transaction_id` et `fraud_prediction` pour l'ensemble d'évaluation
3. **Créer un dashboard visuel** pour visualiser les résultats et insights

### 🎯 Défis Techniques

- **Classe déséquilibrée** : les fraudes sont très minoritaires dans les données
- **Données manquantes** : gestion appropriée des valeurs manquantes
- **Validation temporelle** : respect de l'ordre chronologique (données de 2016–2018)
- **Généralisation à de nouveaux clients** : contrainte majeure du dataset
  - Les clients frauduleux du set d'entraînement sont **différents** de ceux du set d'évaluation (cold start)
  - Le modèle doit généraliser à des patterns de fraude sur des clients jamais vus

## 📊 Dataset

### Volume et Format

- **Nombre de transactions** : ~210,000 transactions (années 2016–2018)
- **Format** : CSV
- **Source** : `hackathon_data.zip`

### Fichiers Fournis

| Fichier | Description | Utilisation |
|---------|-------------|------------|
| `transactions_train.csv` | Transactions d'entraînement avec features | Entraînement |
| `train_fraud_labels.json` | Labels (fraude/non-fraude) | Entraînement |
| `cards_data.csv` | Informations sur les cartes bancaires | Feature engineering |
| `users_data.csv` | Données de profil utilisateur | Feature engineering |
| `mcc_codes.json` | Codes MCC (catégories marchands) | Enrichissement données |
| `evaluation_features.csv` | Transactions d'évaluation (pas de labels) | **Prédiction uniquement** ⚠️ |

### Description des Données

- **Variables transactionnelles** : montants, dates, marchands (via codes MCC), etc.
- **Enrichissement** : données de cartes et profils utilisateurs
- **Étiquettes** : fournies séparément au format JSON

**⚠️ Contrainte importante** : `evaluation_features.csv` ne doit **jamais** être utilisé pour l'entraînement, uniquement pour les prédictions finales.

## 🛠️ Technologies & Stack

- **IBM watsonx.ai** - Plateforme cloud IA d'IBM
- **Python 3.x** - Langage principal de développement
- **Scikit-learn** - Algorithmes de ML (Random Forest, XGBoost, etc.)
- **Pandas & NumPy** - Manipulation et analyse de données
- **Matplotlib & Seaborn** - Visualisations statistiques
- **Jupyter Notebook** - Environnement de développement

## 🚀 Méthodologie

### 1. **Exploration des Données (EDA)**
- Analyse des distributions, déséquilibre des classes
- Identification des patterns de fraude
- Analyse des corrélations et features importantes
- Visualisation des transactions saines vs frauduleuses

### 2. **Feature Engineering**
- Création de features temporelles (jour, heure, jour de la semaine)
- Agrégations par utilisateur et carte (fréquence, montant moyen, etc.)
- Intégration des données de marchands (MCC)
- Encoding des variables catégoriques
- Normalisation et mise à l'échelle

### 3. **Gestion du Déséquilibre**
- Techniques : SMOTE, Imbalance, SMOTETomek
- Choix de la métrique appropriée (Recall & AUC-ROC plutôt que accuracy)

### 4. **Entraînement des Modèles**
- Test de plusieurs algorithmes :
  - Logistic Regression (baseline)
  - Decision Tree
  - Random Forest
  - XGBoost
  - LightGBM

### 5. **Évaluation & Validation Temporelle**
- Évaluation sur des données holdout (après chronologiquement)
- Métriques : Precision, Recall, F1-score, AUC-ROC
- Analyse de la robustesse sur nouveaux clients

### 6. **Prédictions & Soumission**
- Génération des prédictions sur le set d'évaluation
- Formatage au format requis : `transaction_id`, `fraud_prediction`
- Création du fichier CSV de soumission

## 📊 Livrables Obligatoires

### 1. Repository GitHub
✅ Code source complet et documenté  
✅ Notebooks Jupyter avec explications   
✅ Fichier de prédictions généré  

### 2. Pitch Deck (PDF)
✅ Maximum 15 slides  
✅ Présentation du défi et contexte business  
✅ Approche techniques et méthodologie  
✅ Résultats et performance du modèle  
✅ Impact business et recommandations

### 3. Vidéo de Démo (MP4)
✅ Maximum 5 minutes  
✅ Sans son  
✅ Démonstration du dashboard  
✅ Présentation des insights clés  
✅ Aperçu de l'interface utilisateur

## 🏆 Critères d'Évaluation

La jury évaluera les projets sur :

- **Qualité du pitch** - Clarté et pertinence de la présentation
- **Pertinence business** - Compréhension du contexte et de l'impact
- **Implémentation technique** - Qualité du code et des modèles
- **Travail d'équipe** - Collaboration et répartition des tâches

## 👥 Encadrement & Support

### Expert du Track Finance
- **Nom** : Mehdi Boulaymen
- **Position** : AI Engineer, IBM
- **Email** : Mehdi.Boulaymen@ibm.com

### Support Technique
- Accès à la salle **Expert Room** (Zoom) pour les questions techniques
- Mentors IBM watsonx pour support installations et configurations
- Coaches Kryptosphère pour questions méthodologiques
- **Limite** : 15 minutes par team et par session

## 📚 Formation Watsonx Obligatoire

Avant le hackathon, tous les participants ont complété :

- **IBM watsonx: Technical Essentials** (Certification officielle)
- **Getting Started with Generative AI** (Certification officielle)

## 🚀 Installation et Utilisation

### Prérequis

```bash
python >= 3.8
pip
jupyter notebook
```

## 📝 Timeline du Hackathon

| Date | Jour | Heure | Activité |
|------|------|-------|----------|
| 5 nov | Mercredi | 9:00-9:30 | Introduction Kryptosphère |
| | | 9:30-10:00 | Présentations partenaires & use cases |
| | | 10:00-11:00 | Brainstorming équipes |
| | | 11:00-12:00 | Formation avancée Watsonx |
| | | 13:30-18:00 | Kickoff officiel - Développement |
| 6 nov | Jeudi | 8:15-18:00 | Développement intensif |
| 7 nov | Vendredi | 8:15-11:00 | Finalisation des livrables |
| | | 13:30-16:00 | Présentations devant le jury |
| | | | **Deadline soumission : 11:00** ⏰ |

## 💡 Ressources Utiles

- [IBM watsonx Documentation](https://www.ibm.com/watsonx)
- [Scikit-learn ML Algorithms](https://scikit-learn.org/)
- [Pandas Data Manipulation](https://pandas.pydata.org/)

## 🤝 Contact & Support

**Questions générales** : kryptosphere@devinci.fr  
**Questions du track Finance** : Mehdi.Boulaymen@ibm.com  
**Discord Server** : [Accès via lien partagé]

## 📄 Licence & Confidentialité

Ce projet a été développé dans le cadre du hackathon IBM x DeVinci 2025. Les données fournies sont à usage exclusif pour cette compétition.

---

*Équipe 10 | Track Finance | IBM x DeVinci Hackathon 2025*

**Innovate. Code. Win.** 🚀

---

### Remerciements

Merci à **IBM**, **DeVinci**, **Kryptosphère** et tous les mentors pour cette opportunité exceptionnelle d'apprendre et d'innover sur une problématique réelle de fraude bancaire.



