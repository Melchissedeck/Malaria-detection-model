# Malaria-detection-model

## Introduction
Le paludisme est une maladie infectieuse grave transmise par les moustiques et affectant des millions de personnes chaque année. Le diagnostic repose souvent sur l'examen microscopique des frottis sanguins, une procédure longue et nécessitant une expertise médicale.

L'objectif de ce projet est de développer et entraîner un modèle de **réseau de neurones convolutifs (CNN)** capable de distinguer les **hématies infectées par le paludisme** de celles qui sont saines, afin d'accélérer le diagnostic et d'améliorer sa précision.

---

## 📁 Structure du Projet
Le projet suit les étapes suivantes :

### 1️⃣ **Manipulation des Données**
- **Chargement des images et des labels**.
- **Prétraitement des images** : normalisation des pixels entre 0 et 1.
- **Encodage des labels** (1 : Uninfected, 0 : Parasitized)
- **Augmentation des données** via `ImageDataGenerator` (rotations, zooms, flips...).
- **Visualisation des images** avant et après augmentation.

### 2️⃣ **Entraînement de Trois Modèles CNN**
Nous avons testé trois approches :
- 🔹 **Modèle CNN from scratch** avec `Sequential` de Keras (incluant des couches `Dropout`).
- 🔹 **Fine-tuning du modèle VGG16** pré-entraîné sur ImageNet.
- 🔹 **Fine-tuning du modèle ResNet50** pré-entraîné sur ImageNet.

🔹 **Utilisation de Callbacks :**
- `EarlyStopping` pour stopper l'entraînement si `val_loss` cesse de diminuer.
- `ReduceLROnPlateau` pour ajuster le taux d'apprentissage lorsque la performance stagne.

### 3️⃣ **Évaluation des Modèles**
- **Courbes ROC et calcul de l'AUC** pour mesurer la qualité de classification.
- **Matrice de confusion** pour visualiser les erreurs du modèle.
- **Métriques de performance** : Accuracy, Precision, F1-Score, Recall, Sensibilité, Spécificité (via `sklearn.metrics`).

---

## 🚀 Installation et Exécution
### 🔹 Prérequis
Avant d'exécuter le projet, assurez-vous d'avoir **Python 3.11.2** et les bibliothèques suivantes installées :

**pip install tensorflow==2.18.0 numpy pandas matplotlib seaborn scikit-learn opencv-python Pillow**
###🔹 Exécution du Notebook

Téléchargez le fichier .ipynb.

Ouvrez le notebook dans Google Colab (recommandé pour exécuter sur GPU).

Exécutez les cellules pas à pas pour entraîner les modèles et analyser leurs performances.

---

### 📊 Résultats Principaux

1. 🏆 Le modèle VGG16 a obtenu les meilleures performances avec une précision de 96,18% et un AUC de 98,92%.
![image](https://github.com/user-attachments/assets/a75ab411-9928-4524-86d0-49196214e9b9)
![image](https://github.com/user-attachments/assets/ea079e6b-089d-46ea-b1e8-190276be72ab)

2. Le modèle from_scratch a obtenu une précision de 96,01% et un AUC de 98,79%.
![image](https://github.com/user-attachments/assets/27db20f7-726f-4184-81ac-a170571788da)
![image](https://github.com/user-attachments/assets/6ae2c96f-632a-43f4-ad33-5101e8524a7a)


4. Le modèle ResNet50 a obtenu une précision de 85,20% et un AUC de 92,38%.
![image](https://github.com/user-attachments/assets/57137ac2-7050-4570-8c86-17ee28d219c2)
![image](https://github.com/user-attachments/assets/0cfa9f2d-6124-465b-b16e-0f8b29e94768)

---

### 📜 Remerciements

- Les données proviennent du site officiel des National Institutes of Health (NIH) : https://ceb.nlm.nih.gov/repositories/malaria-datasets/.
- Merci à monsieur Hakim Horairy pour le soutien et l'expertise apportée au cours de la réalisation de ce projet.

---

### 📝 Auteurs
 - **Melchissedeck AFOUDAH**
 - **Mehdi BEN CHEIKH** 
 - **Théo CHANNAROND**
