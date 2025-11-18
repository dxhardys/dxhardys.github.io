---
title: "Convention Reporting collaboratif"
institute: "DU Capteur et Technologie Innovante - Projet | Fablab | Paris Saclay"
author: "A. Sofiane"
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
## Convetion de reporting collaboratif

Cette documentation fait partie intégrante du livrable du projet **Serre Connectée**.  
Elle doit refléter un travail de qualité et permettre à toute personne de comprendre clairement ce qui a été réalisé et faciliter la notation.

## Objectifs

- Expliquer **les tâches effectuées** chaque semaine.
- Illustrer le travail avec des **images, graphiques ou schémas** lorsque nécessaire.
- Fournir un suivi clair et structuré du projet.

## Conventions à respecter

1. **Reporting hebdomadaire**  
   - Chaque semaine doit avoir sa propre section ou fichier (`week1.md`, `week2.md`, etc.).  
   - Décrire les objectifs, les tâches réalisées, les difficultés rencontrées et les solutions apportées.

2. **Illustrations médias et schémas**  
   - Toutes les images ou captures d’écran doivent être **fournies, titrée et correctement référencées**.  
   - Les fichiers images doivent être stockés dans un le dossier `/images` avoir un nom significatif au format snake_case.
   - Les schémas de cablâge sont à réaliser avec `Fritzing`.
   - Les exemples et snippet de code seront mis un bloc de code en spécifiant le langage utilisé en utilisant les triple backticks.
     \```\<langage>
     \```

3. **Clarté et lisibilité**  
   - Utiliser des titres, sous-titres et listes à puces pour structurer le contenu.  
   - Rédiger des phrases complètes et compréhensibles.  

4. **Respect du format Markdown Ou Latek pour les formules**  
   - Vérifier la bonne syntaxe Markdown pour que la documentation soit correctement rendue par MkDocs.  
   - Éviter le contenu brut non formaté.
   - Introduire toute formule mathématique au format LateK, celui-ci est pris en charge par Github Pages.

5. **Fichiers**  
   - Les différents fichiers de codes, modèles 3D ou datasheet seront ajouter au projet avec des messages de commit significatif.
