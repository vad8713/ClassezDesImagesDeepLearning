# 🐶 Classez des images à l'aide d'algorithmes de Deep Learning

Détection automatique de la race d'un chien à partir d'une photo, à l'aide d'un modèle de Deep Learning (transfer learning sur ResNet50), dans une optique d'application mobile pour un site de mise en relation avec des refuges.

## 📌 Contexte

Une association propose sur son site web une fonctionnalité permettant aux utilisateurs de télécharger une photo de leur animal, avec en retour des informations sur sa race. L'objectif de ce projet est de développer le moteur de classification d'images qui alimentera cette fonctionnalité, capable de prédire la race d'un chien à partir d'une simple photo.

## 🎯 Objectifs

- Prétraiter un ensemble d'images de chiens (redimensionnement, normalisation, amélioration du contraste).
- Mettre en place des techniques de **data augmentation** (rotation, symétrie, flou gaussien...) pour enrichir le jeu d'entraînement.
- Entraîner un modèle de classification d'images par **transfer learning** à partir du réseau **ResNet50**.
- Construire un programme de prédiction capable de renvoyer le nom de la race à partir d'une nouvelle image.

## 🗂️ Données

Le projet s'appuie sur un jeu d'images de chiens annotées par race (type *Stanford Dogs Dataset*). Les images ne sont pas incluses dans ce dépôt ; elles sont attendues dans un répertoire d'images en entrée des notebooks.

## 📁 Structure du projet

| Fichier | Description |
|---|---|
| `deepLearning_1_notebook.ipynb` | Prétraitement des images (nettoyage, réglage automatique des niveaux) et data augmentation (rotation, flip, flou gaussien). Constitution du jeu de données au format attendu par le CNN. |
| `deepLearning_2_programme.ipynb` | Programme de prédiction : chargement du modèle ResNet50 entraîné et de l'encodeur de labels, puis prédiction de la race sur de nouvelles images. |

## 🧰 Technologies utilisées

- **Python**, **NumPy**, **Pandas**
- **Pillow (PIL)** : traitement et transformation des images
- **TensorFlow / Keras** : construction et entraînement du CNN (transfer learning ResNet50)
- **Scikit-learn** : `train_test_split`, `LabelEncoder` (`preprocessing`)
- **joblib** : sauvegarde/chargement du modèle et de l'encodeur

## 🔍 Démarche

1. **Constitution du jeu de données** : parcours du répertoire d'images, création d'un DataFrame associant chaque image à sa race.
2. **Prétraitement** : réglage automatique des niveaux, redimensionnement, conversion au format attendu par le CNN.
3. **Data augmentation** : génération de variantes d'images (rotation, symétrie, flou) pour limiter le sur-apprentissage.
4. **Entraînement** : transfer learning à partir de ResNet50, suivi des courbes de perte et d'accuracy.
5. **Prédiction** : chargement du modèle entraîné et de l'encodeur de labels pour prédire la race d'un chien à partir d'une nouvelle photo.

## 👤 Auteur

David Depouez — Projet réalisé dans le cadre de la formation Ingénieur Machine Learning (OpenClassrooms, RNCP niv. 7).
