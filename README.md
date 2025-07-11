# Valeo AI Challenge

Repo public servant uniquement à titre de portfolio. Pour plus d'informations, contacter tristanscuillereng@gmail.com

## Descriptif du projet

Challenge IA proposé par l'ENS en partenariat avec Valeo. Objectif : entraîner un modèle capable de : 
* classifier 5 classes de défauts rencontrés dans le cadre d'un processus de production de composants électroniques, avec comme données les images prises en fin de chaîne.
* identifier, le cas échéant, d'éventuels outliers (défaut de la caméra...) afin de rendre le modèle robuste.

## Travail réalisé

Après avoir exploré le dataset `exploratory.ipynb`, nous nous sommes arrêtés sur l'architecture suivante pour répondre au CDC : 
* Fine-tuning d'un RESNET50 avec poids de ImageNet, à 2 couches superficielles.
* Utilisation de la technique de PADIM pour la détection des outliers ([Defard & al, 2018](https://arxiv.org/abs/2011.08785)).

## Contenu du repo

3 notebooks : 
* `exploratory.ipynb` d'exploration du dataset
* `classifier.ipynb` pour l'entraînement du classifier
  * Fonction de perte cross entropy, 5 classe one-hot encodées
  * 1 couche de pooling suivie d'une couche FF. Nombre de neurones présent dans le notebook différent du nombre de neurones finalement utilisé.
  * RESNET50 entièrement gelé
  * entraînement sur Google Colab (pas de GPU à la dispositio de l'équipe).
* `PADIM.ipynb` pour l'entraînement du modèle de PADIM
  * modèle final lourd
  * modèle lent pour réaliser des prédictions : besoin de l'optimiser

## REX

* Excellent projet d'introduction au deep learning, travail sur des données réelles
* Problème classique de classification multi-classes
* Problèmes hardware rencontrés : repli sur des solutions de type cloud-computing (Google Colab...)
* Bonne expérience de gestion de projet :
  * Rédaction d'un CDC
  * Phase de préconception
  * Phase de développement
  * Présentation d'un livrable
  * Gestion d'équipe
