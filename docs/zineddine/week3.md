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
# Tests et Validation des Capteurs et Actionneurs
## Introduction
Dans le cadre de l’amélioration et de la mise en service de la serre connectée, une phase essentielle consiste à tester l’ensemble des capteurs et actionneurs afin de garantir leur bon fonctionnement avant l’intégration finale dans le système. Ces tests permettent de s’assurer que chaque composant répond correctement aux sollicitations, fournit des données fiables et interagit sans interférences avec les autres éléments de la serre.

L’objectif de cette campagne de tests est donc de valider individuellement chaque capteur et actionneur, puis de vérifier leur fonctionnement combiné. Cette démarche contribue à sécuriser l’installation, à anticiper les problèmes potentiels et à garantir une exploitation optimale une fois la serre complètement opérationnelle.
## Plan de Test – Capteurs, Actionneurs et Boucles de Régulation
Ce plan présente l’ordre dans lequel les différents capteurs, actionneurs et systèmes de régulation seront testés. L’objectif est de vérifier leur bon fonctionnement un par un, d’identifier d’éventuels problèmes et d’apporter ensuite les améliorations nécessaires au code et à l’intégration globale du système
### 1. Test du capteur de niveau d’eau
Statut : déjà testé – fonctionnement validé.
Objectif : confirmer la détection correcte du niveau d'eau dans le reservoir et son intégration.
### 2. Test des actionneurs : ventilateur et module Peltier
Objectif :

Vérifier l’activation via relais.

Contrôler la stabilité du ventilateur.

Vérifier la capacité du Peltier à refroidir.
### 3. Test de la boucle de contrôle de température
3. Test de la boucle de contrôle de température


Objectif :

Lire correctement les valeurs du capteur de température.

Vérifier la commande des actionneurs ((Electric Heating Pad)) selon les seuils fixés.

Identifier les améliorations à apporter à l’algorithme de contrôle
### 5. Test du capteur d’humidité et contrôle de l’arrosage (pompe)

Objectif :

Valider la mesure d’humidité ambiante ou de sol (selon modèle).

Vérifier l’activation correcte de la pompe en fonction des seuils définis.

Identifier les améliorations nécessaires pour éviter les déclenchements intempestifs.
### 6. Test du capteur de niveau d’oxygène

Objectif :

Vérifier la mesure O₂ dans la serre.

Tester la sensibilité du capteur à une augmentation/diminution locale.

Assurer la stabilité des valeurs remontées.
### 7. Test de la lampe multicolore

Objectif :

Vérifier le fonctionnement complet de la lampe multicolore.

S’assurer que la lampe répond correctement aux commandes envoyées par la carte logique (Raspberry Pi / Arduino).

Identifier d’éventuels ajustements nécessaires dans  le câblage.