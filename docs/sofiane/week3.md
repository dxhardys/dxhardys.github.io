---
title: "Reporting Semaine du 17/11/2025"
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


Modéliser un premier prototype sur Fusion360, en parcourant les designs de serres custom sur internet nous avons esquissé un premier concepte à base de pièces tubulaire formant une armature réctangulaire avec sur la partie inférieur un compartiment pour déposer du terrot et y planter notre plante, et une partie supérieure qui viendras se poser sur l'armature qui elle contiendra la connectique (cartes embarquée, cablage alimentation etc..)

La figure ci-dessous décrit l'idée derrière ce premier prototype, d'autres élements viendront s'ajouter se retirer au fil des évolution du design, mais cela fournit déja une bonne vue globale. 


<figure style="text-align: center;">
  <img src="/sofiane/images/prototype1.png"  width="800">
  <figcaption> Design V1.0 Serre - Fusion360 </figcaption>
</figure>

Plusieurs pièces composent l'armature de la serre (la partie centrale), des connecteurs inférieurs qui viendront se fixer sur le compartiment dédiée à la plante avec des visses et sur lesquelles les tubes viendront se connecter. Des connecteurs supérieurs sur lequels la encore les pièces tubulaire viendront se connecter sur 3 axes différents et sur lequel le compartiment supérieure viendras se poser.


<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="/sofiane/images/bottom_corner_piece.png" style="width: 30%;">
  <img src="/sofiane/images/top_corner_piece.png" style="width: 30%;">
  <img src="/sofiane/images/tube_threaded.png" style="width: 30%;">
  <figcaption> Modèles 3D Pièces de base </figcaption>
</div>


Nous allons d'abord tester la faisabilité d'imprimer nous même et de visser les pièces tubulaire entre elles pour ça nous allons imprimer deux exemplaire de notre tube et essayer de les visser entre elles, pour les dimensions choisie l'impression est assez lente (~2h) il aurait été plus judicieux de revoir les dimensions à la baisse pour cette phase de prototypage afin d'obtenir les inforations qu'on désirent plus rapidement cela sera retenue pour la suite du prototypage.

<figure style="text-align: center;">
  <img src="/sofiane/images/impression_tube_threaded.jpg"  width="400">
  <figcaption> Pièce Tubulaire 10cm </figcaption>
</figure>

Le résultats de l'impression plutôt bon à première vu la solidité est trés bonne avec des parois de 2mm d'épaisseurs on ne s'attends pas à des problèmes de solidité de la structure par la suite, le filetage en revanche est assez grossier est granuleux et necessite d'étre poncé mais si l'on doit poncer le filetage de chaque pièce cela sera chronophage, le vissage s'avère extrement difficile il faut forcer sur les deux pièces pour réussir à les visser ça bloque régulièrement et passer un certain point il n'est juste plus possible de les séparer, cette solution n'est pas idéale.


<figure style="text-align: center;">
  <img src="/sofiane/images/connected_tubes.jpg"  width="400">
  <figcaption> Deux pièces vissés entre elles </figcaption>
</figure>

Imprimer nos propres tube filleté ne semble pas être une bonne idée, il faudrait soit penser a une manière de connecter les tubes plus simple (clippage) ou utiliser des tubes standard en PVC trouvable dans le commerce ou au Fablab cela nous économiseras du temps d'impression.