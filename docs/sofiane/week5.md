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

## Assemblage du premier prototype

Cette semaine nous avons réussi a assembler le premier prototype de la serre décrit et modéliser les semaines précédentes

### Impressions des pièces 

L'impression des différentes pièces s'est déroulé sans accroc majeure si ce n'est quelques échecs d'impressions par moments, difficile de savoir pour quel raisons une impression échoue aprés discussion avec les responsables on peut supposer
- Vibrations trop importantes par moments, l'armoire surlaquelle reposent les imprimantes n'étant pas 100% stables des vibrations peuvent perturber l'impression cela est d'autant plus vrai lorsque plusieurs imprimantes fonctionnent en même temps.
- Temperature faible, le PETG utilisé nos pièce fond a temperature de 230°C le plateau d'impression quant à lui necessite d'être chauffé à 80°C, on peut supposer qu'avec la temperature ambiantes du fablab en ces jours de Novembre rend le maintient de ces temperatures plus difficile et energivore pour la Prusa MK4S, il suffit que le temperature de la buse ne soit plus assez elevé quelques instant pour obstruer celle-ci et créer des grumeaux qui font échouer l'impression.

Les échecs d'impressions ne sont pas problématique lorsqu'il interviennt assez tôt dans le processus et qu'on le repere immédiatement, c'est plus génant lorsque'ils interviennent à 50% ou lorsques nous avons deja quitter le Fablab, d'ou l'interet de rester et s'assurer que l'impression à démarrer convenablement avant de quitter les lieux.

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="/sofiane/images/print_fail_1.jpg" style="width: 30%;">
  <img src="/sofiane/images/print_fail_2.jpg" style="width: 30%;">
  <figcaption> Echecs d'impression - Bottom corner piece </figcaption>
</div>

### Mesurer deux fois Imprimer une fois

Certaines pièces se sont averer être mal alligné ou trop difficile à emboiter, notamment les charnières malgré le faite d'avoir tester l'assemblage de toutes les pièces entre elles sur `Fusion360` dans la pratique l'impression reste assez grossière sur les partie fines et donc cela engendre quelques problèmes.
- Les charnières ne s'emboitent pas, necessité d'élargir les troue.
- Les pièces `top_corner` et `door_corner` ont un aspect trés rugeux sur les montants imprimer à la verticale comparé à ceux imprimer à l'horizontal, les montant verticales s'emboitent bien plus facilement avec le tube en pvc que ceux à l'horizontale, encore un effet que nous n'avions pas prévue (je doute qu'on aurait pu prévoir cette effet), cela n'est pas extrement problématique mais rend l'assemblage un plus diffile il faut forcer d'avantage pour emboiter les tubes verticaux. Une possible solution serait de découper les pièces `top_corner` et `door_corner` en une base et ses montant qui seront toujours imprimé verticalement puis viendrony se connecter à leur bases. 


### Résultat Finale du prototype

Ce premier prototype est prometteur, les blocs inférieur et supérieure sont pour le moment en cartons 