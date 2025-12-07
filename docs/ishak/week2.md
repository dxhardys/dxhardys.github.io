---
title: "Reporting Semaine du 03/11/2025"
institute: "DU Capteur et Technologie Innovante - Projet | Fablab | Paris Saclay"
author: "B. Ishak"
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
# 🚀 Mise à jour du Projet - Semaine 2

## 🗓️ Bilan de la Semaine

Cette semaine, l'accent a été mis sur la **finalisation de l'architecture** du système et l'intégration des premiers capteurs.

* **Avancée majeure :** Mise en place du schéma de base de données pour la collecte des données de température et d'humidité.
* **Tâches accomplies :**
    * Câblage initial des modules de contrôle.
    * Tests de communication I2C avec le capteur DHT22.
    * Rédaction des premières ébauches du code de lecture des capteurs.

## 🌡️ Section 1 : Intégration du Capteur de Température

Le capteur de température/humidité (DHT22) a été connecté et testé avec succès.

### Schéma de Câblage

Voici le schéma de connexion utilisé sur la carte de contrôle.

[Image du schéma de câblage]

**Code Snippet :** La lecture est effectuée toutes les 30 secondes pour une économie d'énergie.

### Résultat du Test Initial

Les premiers résultats montrent une lecture stable après étalonnage.

[Image du graphique des données initiales]

## 💡 Section 2 : Architecture Logicielle

Le diagramme ci-dessous illustre l'architecture logicielle proposée pour la gestion des données (lecture, stockage, envoi au cloud).

[Image du diagramme d'architecture]

**Points Clés :**
1.  **Module de lecture :** Responsable de l'interrogation périodique des capteurs.
2.  **Module de stockage :** Utilisation d'une mémoire locale (SD Card) comme cache.
3.  **Module de communication :** Envoi des données via MQTT au serveur distant.

## 🚧 Prochaines Étapes (Semaine 3)

* Intégration du module de contrôle des actionneurs (pompe et ventilateur).
* Développement de la logique de contrôle de base (Seuil de température).
* Début de l'interface utilisateur web.