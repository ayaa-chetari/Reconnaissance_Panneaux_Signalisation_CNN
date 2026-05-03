#  Traffic Sign Recognition with PyTorch

## Description

Ce projet implémente une méthode d’apprentissage supervisé pour la classification de panneaux de signalisation à partir du dataset **GTSRB (German Traffic Sign Recognition Benchmark)**.

Le modèle utilisé est un réseau de neurones convolutif (CNN) permettant de classer une image parmi 43 classes de panneaux.

---

##  Dataset

Le dataset GTSRB contient :

- Environ 39 000 images
- 43 classes de panneaux
- Images de tailles variables
- Format `.ppm`

###  Utilisation dans ce projet

Pour accélérer les expérimentations nous avons utlisé que 40% du dataset


---

##  Modèle utilisé

Le modèle est un CNN composé de :

- 3 couches de convolution :
  - Conv2d(3 → 32)
  - Conv2d(32 → 64)
  - Conv2d(64 → 128)

- 3 couches de pooling (MaxPool2d)

- 2 couches fully-connected :
  - Linear(128 × 8 × 8 → 256)
  - Linear(256 → 43)

- Activation : ReLU  
- Dropout : 0.5  

---

##  Prétraitement

Les images sont transformées comme suit :

- Redimensionnement : 64 × 64  
- Conversion en tenseur PyTorch  
- Normalisation
  
---

##  Hyperparamètres

- Batch size : 64  
- Nombre d’epochs : 10  
- Optimiseur : Adam  
- Learning rate : 0.001  
- Fonction de perte : CrossEntropyLoss  

---

##  Entraînement

Le modèle est entraîné sur 40 % du dataset total avec :

- 80 % pour l’entraînement  
- 20 % pour la validation  

Les métriques suivies sont :

- Loss  
- Accuracy  

---

## Sauvegarde du modèle

Le modèle est sauvegardé au format : cnn_gtsrb.pth





