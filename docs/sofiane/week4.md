---
title: "Reporting Semaine du 03/11/2025"
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

## Deploiment GitHub Pages 

La première solution de reporting était basé sur Gitbook proposition payante aprés 14 jours d'essai gratuit, Gitbook offrait une solution "plug and play" avec un certain niveau d'abstraction pour faciliter la rédactions à ses utilisateurs, ne voulant pas s'enfermer dans une proposition payante et au contraire voulant réaliser le maximum de choses par nous-même pour ce projet.

Il était necessaire de déployer notre propre solution de reporting, un framework populaire est l'utilisation de `Mkdocs` et des `action` et Pipeline github basé sur `GithubPages` pour héberger notre propre plateforme de reporting via un pipeline d'intégration continue et developpement continue (CI/CD) nous avons pris le temps de crée une manière robuste et efficace de contribuer au reporting en respectant les bonne pratiques du génie logicielle (Versionnage, CI/CD...), en plus d'établir une convention pour la participation au projet et au reporting trouvable en annexe.

Le [dépot Github](https://github.com/dxhardys/dxhardys.github.io) avec les sources et le pipeline.

Cette documentation s'accompagne d'un guide pour être rapidement opérationnel pour le reporting notamment pour les membres du groupe n'ayant jamais utiliser les outils de versionnage auparant, ce guide est disponible en annexe.

## Suite Modélisation

La semaine dernière nous avons écarter l'idée d'imprimer nos propre pièces tubulaire filleté car trop lent et la qualité du filetage laisse à désirer il est extrement difficile de connecter les pièces entres elles et de les spéparer, nous avons échanger à ce sujet avec les encadrants qui nous ont suggerer d'utiliser des tubes en PVC qui trainait dans le Fablab, nous disponsons d'environs 3 mètres de tubes de 25 mm de diamètre externe et 22 mm  de diamètre interne.

<figure style="text-align: center;">
  <img src="/sofiane/images/pvc_tube.jpg"  width="400">
  <figcaption> Tube PVC - 30 cm </figcaption>
</figure>


Nous avons donc adapter nos pièces précedemment modéliser pour s'adapter à ces dimensions avec cette fois une méthode d'assemblage basé sur le clipssage des pièces entres elles et non plus le vissage, nous avons également poursuivie la modélisation en ajoutant une porte avec charnière afin d'acceder à l'interieur de la serre.

<figure style="text-align: center;">
  <img src="/sofiane/images/door_model.jpg"  width="400">
  <figcaption> Assemblage Porte </figcaption>
</figure>

Cette porte utilise 2 connecteurs simple coté exterieure et 2 connecteurs avec charnière mâle coté interieure qui viendront s'emboiter avec des charnière femelle sur l'un des montant de l'armature de la serre 

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="/sofiane/images/door_hinge_top.png" style="width: 30%;">
  <img src="/sofiane/images/door_hinge_bottom.png" style="width: 30%;">
  <img src="/sofiane/images/hinge.png" style="width: 30%;">
  <figcaption> Charnières et connecteurs portes </figcaption>
</div>


Une vision plus globale de la porte connecter à l'armature est visible ci-dessous, un verrou pourra être ajouté par la suite pour sécuriser la porte.


<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="/sofiane/images/body_and_door.png"  width="400">
  <img src="/sofiane/images/hinge_link.png"  width="400">
  <figcaption> Assemblage Porte et corps </figcaption>
</div>


## Expérience Plante N°1

Une première expérience avec la plante est de la mettre dans un environnement complètement obscure pour voir l'impacte sur son développement, pour ça on prend une pouce de plante arraigné qu'on met dans un petit pot avec du terrot et met ce pot dans une boite en carton fermé et isolé de toute lumières extérieure 


<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="/sofiane/images/plante_experience_1_observation_0.png"  width="400">
  <img src="/sofiane/images/plante_experience_2_observation_0.png"  width="400">
  <figcaption> Setup Plante dans l'obscurité </figcaption>
</div>


