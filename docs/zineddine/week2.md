---
title: "Reporting Semaine du 03/11/2025"
institute: "DU Capteur et Technologie Innovante - Projet | Fablab | Paris Saclay"
author: "L. Zineddine"
date: \today
theme: metropolis
colortheme: orchid
fonttheme: structurebold
toc: true
toc-depth: 2
slide-level: 2
header-includes:
  - \metroset{sectionpage=progressbar}
---
# Méthode de mise en œuvre des corrections 
## 1. Remplacement des trois câbles de sortie par un seul câble et installation d’un bloc de distribution
Afin d’améliorer l’organisation et la sécurité du câblage, la première correction consiste à remplacer les trois câbles de sortie actuels par un seul câble d’alimentation principal.
Ce câble unique, contenant la phase, le neutre et la terre, alimentera directement un bloc de distribution (voir image ci-dessous ).
<figure style="text-align: center;">
  <img src="/zineddine/images/1OcF+FgoEL._AC_UF1000,1000_QL80_.jpg"  
  <figcaption> Connecteur de câble électrique </figcaption>
</figure>
Fonctionnement proposé : 
- Le câble principal sort de la serre et alimente en entrée le bloc de distribution.

- Depuis ce bloc, la distribution électrique sera divisée proprement vers les différents grands consommateurs de la serre :

  - La lampe 100 W (éclairage principal de la serre).

  - Le convertisseur AC 240 V → DC 24 V (100 W), utilisé pour alimenter les différents actionneurs ou modules basse tension.

  - L’adaptateur secteur chargé d’alimenter les cartes logiques (Raspberry Pi, Arduino, etc.).
## 2. Amélioration interne au niveau du câblage du bloc 
À l’intérieur, la distribution sera organisée grâce à trois connecteurs séparés, permettant une séparation nette des circuits et assurant une connexion plus fiable et professionnelle. Cette organisation facilite également la maintenance en cas de panne et garantit un repérage clair de chaque conducteur, ce qui améliore considérablement la lisibilité et la sécurité du câblage.
## 3. Ajout d’un interrupteur extérieur

Pour améliorer encore l’exploitation de la serre et faciliter les interventions, il est recommandé d’ajouter un interrupteur général à l’extérieur de la serre. Cet interrupteur permettra de couper totalement l’alimentation avant toute intervention, garantissant ainsi la sécurité des manipulations internes et réduisant les risques liés au travail sous tension.

## Matériel nécessaire 

Pour réaliser les corrections mentionnées précédemment, le matériel nécessaire concernera principalement la connectique et les éléments de distribution électrique. Cela inclut les câbles, les connecteurs, le bloc de distribution et un interrupteur général pour sécuriser l’alimentation. Les détails précis seront définis une fois le design optimal de l’installation finalisé, afin de garantir une mise en œuvre propre, sécurisée et facilement dépannable. 