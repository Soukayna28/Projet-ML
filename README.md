### Classification de texte avec réseaux de neurones sur 20 Newsgroups
### Description du projet :
Ce projet implémente un système de classification de texte utilisant des réseaux de neurones pour catégoriser des articles de presse du dataset 20 Newsgroups en 20 catégories thématiques.

### Structure du projet :
projet-classification-20newsgroups/
├── projetSujet4.ipynb   # Notebook principal
├── README.md                           # Ce fichier

Instructions d'exécution :
Prérequis : 
* Python 3.8+
* Google Colab (recommandé) ou environnement local avec GPU

Exécution du notebook :
1 - Ouvrez le notebook dans Colab ou Jupyter 
2 - Exécutez les cellules dans l'ordre :
Cellule 1 : Import des bibliothèques
Cellule 2 : Chargement et exploration des données
Cellule 3 : Prétraitement du texte
Cellule 4 : Modèles baselines
Cellule 5 : Réseau de neurones initial
Cellule 6 : Recherche d'hyperparamètres
Cellule 7 : Évaluation et comparaison

Jeu de données :
* Source
Nom : 20 Newsgroups
Source : Scikit-learn (fetch_20newsgroups)
Taille : ~18,000 documents
Classes : 20 catégories thématiques
Description : Collection d'articles de forums Usenet répartis en 20 groupes thématiques

Catégories :
Les 20 catégories incluent :
* comp.graphics, comp.os.ms-windows.misc, comp.sys.ibm.pc.hardware, comp.sys.mac.hardware
* comp.windows.x, misc.forsale, rec.autos, rec.motorcycles
* rec.sport.baseball, rec.sport.hockey, sci.crypt, sci.electronics
* sci.med, sci.space, soc.religion.christian, talk.politics.guns
* talk.politics.mideast, talk.politics.misc, talk.religion.misc

Préparation des données :
* Nettoyage : Suppression des en-têtes, pieds de page et citations
* Vectorisation : TF-IDF avec paramètres optimisés
* Réduction dimension : TruncatedSVD (300 composantes)
* Normalisation : StandardScaler
* Split : Train (70%), Validation (10%), Test (20%) avec stratification

Modèles implémentés :
1. Baselines
* Naive Bayes Multinomial : Modèle traditionnel pour texte
* Régression Logistique : Baseline de performance

2. Réseau de neurones
* Architecture : Dense avec Dropout et Batch Normalization
* Couches : 1-2 couches cachées (64-128 neurones)
* Sortie : Softmax (20 classes)
* Optimiseur : Adam avec learning rate adaptatif
* Régularisation : Dropout (20-50%), Early Stopping

Métriques d'évaluation :
* Accuracy (précision globale)
* F1-score (pondéré)
* Matrice de confusion
* Courbes d'apprentissage (loss/accuracy)

Résultats attendus :
* Performance du réseau de neurones : ~75-85% accuracy
* Amélioration par rapport aux baselines : +5-10%

Paramètres reproductibilité :
* Seed fixe : 42
* Validation croisée : 3 folds pour la recherche d'hyperparamètres
* Stratification pour préserver la distribution des classes

Temps d'exécution estimé :
* Google Colab (GPU) : 15-30 minutes
* CPU local : 1-2 heures
* Recherche hyperparamètres : Partie la plus longue (peut être réduite)

Personnalisation possible :
* Modifier max_features dans TF-IDF pour plus/moins de mots
* Ajuster la réduction de dimension (TruncatedSVD)
* Changer l'architecture du réseau de neurones
* Ajouter des embeddings pré-entraînés (Word2Vec, GloVe)

Limitations connues :
* TF-IDF ne capture pas la sémantique profonde
* Réduction dimensionnelle peut perdre de l'information
* Temps d'entraînement élevé pour recherche hyperparamètres
* Mémoire importante pour matrice TF-IDF complète

Contact et références :
* Dataset : Scikit-learn 20 Newsgroups
* Documentation TensorFlow : https://www.tensorflow.org/
* Documentation Scikit-learn : https://scikit-learn.org/

Licence :
Code sous licence MIT - Données originales sous leurs licences respectives
