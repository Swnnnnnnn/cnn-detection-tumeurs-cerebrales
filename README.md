# Détection de tumeurs cérébrales à partir d’images IRM par réseau de neurones convolutif (CNN)

Ce dépôt présente un projet complet de détection automatique de tumeurs cérébrales à partir d’images IRM.  
L’objectif est de classifier les images en deux catégories : **présence de tumeur (`yes`)** et **absence de tumeur (`no`)**.  
Le modèle repose sur un **réseau de neurones convolutif (CNN)** implémenté avec **TensorFlow / Keras**.

## Objectif
Construire, entraîner et évaluer un modèle de deep learning capable de détecter des tumeurs cérébrales à partir d’un jeu d’images médicales.

## Données
- **Structure du dataset :**
  - `yes/` : images IRM présentant une tumeur  
  - `no/` : images IRM sans tumeur  
- **Prétraitement :**
  - Redimensionnement des images à **128×128 pixels**
  - Normalisation des valeurs de pixels entre 0 et 1  
  - Division des données en ensembles d’entraînement et de test (80/20)
  - **Data augmentation** (rotation, translation, zoom, flip horizontal)

## Modèle
Le modèle est un **CNN séquentiel** comprenant :
- Trois couches convolutionnelles avec 32, 64 et 128 filtres  
- Fonctions d’activation ReLU et LeakyReLU  
- Couches de pooling pour la réduction de dimension  
- Une couche dense de 128 neurones avec Dropout (0.5)  
- Une couche de sortie sigmoid pour la classification binaire  

**Optimiseur :** Adam  
**Fonction de perte :** Binary Crossentropy  
**Métrique :** Accuracy  
**Nombre d’époques :** 30  
**Batch size :** 32  

## Résultats
Le modèle atteint une **précision d’environ 80 %** sur l’ensemble de test.  
L’évaluation est réalisée à l’aide d’un second notebook dédié à la vérification des performances globales.

## Organisation du dépôt
- `creation_modele.ipynb` : entraînement et sauvegarde du modèle  
- `evaluation.ipynb` : chargement du modèle et évaluation sur l’ensemble du dataset  
- `brain_tumor_model.h5` : modèle entraîné sauvegardé  
- `yes/` et `no/` : répertoires contenant un échantillon des images IRM utilisées  

## Améliorations possibles
- Utiliser un modèle pré-entraîné (MobileNetV2, EfficientNet, ResNet50)  
- Étendre le jeu de données et équilibrer les classes  
- Intégrer des métriques supplémentaires (ROC, F1-score, précision/rappel)  
- Développer une interface de prédiction (Flask, Streamlit)

## Compétences mobilisées
- Deep learning et vision par ordinateur  
- TensorFlow / Keras  
- Prétraitement et augmentation d’images  
- Évaluation et sauvegarde de modèles `.h5`  
- Python, NumPy, Matplotlib
