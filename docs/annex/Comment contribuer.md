## Gestion de code et contrôle de version.

Ce rapport collaboratid est construit en utilisant `Github Pages` et un pipeline de deploiment basé sur `Github Actions`, quelque connaissance basique en contrôle de version sont necessaire afin de pouvoir contribuer de manière efficace et collaborative.

### Git 
Git est de loin le système de contrôle de version le plus largement utilisé aujourd'hui. Git est un projet open source avancé, qui est activement maintenu. À l'origine, il a été développé en 2005 par Linus Torvalds, le créateur bien connu du noyau du système d'exploitation Linux. De plus en plus de projets logiciels reposent sur Git pour le contrôle de version, y compris des projets commerciaux et en open source. Les développeurs qui travaillent avec Git sont bien représentés dans le pool de talents disponible, et la solution fonctionne bien sur une vaste gamme de systèmes d'exploitation et d'environnements de développement intégrés (IDE)[¹](https://www.atlassian.com/fr/git/tutorials/what-is-git).

## Github

Github est une Forge ou plateforme en ligne qui permet d'héberger des repository "Git" comme il en existe plusieurs (Gitlab,Gitbucket..), Git et Github peuvent être comparé à une vidéo et Youtube, un repository est une vidéo et Youtube et un hebergeur qui permet d'uploader cette vidéo dans un serveur en ligne comme Github.

Github est de loin la forge la plus utilisé notamment pour les projets opensource.

## Pull Commit et Push

- Une `Pull request` permet de récuperer la dernière version d'un repository, si par exemple celui-ci a été modifier par d'autres collaborateurs, pour récuperer la dernière version du repository on fait une pull request.

- Un `Commit` est un ensemble de modification effectué sur le projet, mis à jour du code, ajout de nouvelles fonctionnalités etc.. Un `Commit` doit représenter une seule modification clair et contenir un message significatif, exemple dans le cadre de ce projet pour le reporting de la semaine on modifie son fichier de la semaine en `markdwon` on ajoute ses images correspondant et on `commit ` le tout avec un message "Add reporting of week 3", le nom des fichiers et les messages de commit se feront par convention en anglais.

- Un `Push` est l'action d'uploader les modification faites localement vers la forge, afin que les autres utilisateurs puissent à leurs tour effectuer une `Pull request` pour récuperer les dernières modifications faites.

## Comment contribuer au reporting.

### Windows

Pour pouvoir contribuer au reporting sur windows on se baseras sur l'intégration GitHub de `VScode` , d'abord télécharger et installer [Git](https://git-scm.com/install/) et [VScode](https://code.visualstudio.com/download). Dans la rubrique extension de VSCode installer `GitHub Pull Requests`.

#### Cloner le dépôt (repository)
Sur `VSCode` tapez `Ctrl + Shift + P` pour ouvrir l'invite de commande puis entrez `git clone <repo-url>`, `<repo-url>` correspond à l'URL https du repository, voir la figure ci-dessous :

<figure style="text-align: center;">
  <img src="/docs/annex/images/repository_clone.png"  width="400">
  <figcaption> Cloner un dépot GitHub</figcaption>
</figure>

Une demande d'authentification à votre compte github peut vous être demandé, renseignez vos coordonées et valider, si vous rencontrer une erreur de type `user.name` et `user.email`, saisissez les commandes suivante dans un terminal `VScode` avec `Ctrl + J`

```shell
git config --global user.name "<votre nom>"
git config --global user.email "<l'eamil associé à votre compte github>"
```


Une fois le repository cloner vous pouvez commencez à modifier les différent fichiers au format `Markdown` naviguez vers le fichier `week` correspondant et commencez à le modifier, vous verrez apparaitres les marques vertes sur les indices de lignes, ces marques verte correspondent à vos modification en cours que vous n'avez pas encore commité, pour valider vos modification et que celle-cis soit visible sur `GitHub Pages` naviguez vers le manu lateral `Version Control` et cliquer sur le `+` correspondant au fichier que vous venez de modifier, celui-ci a été ajouté dans les `Staged Changes` si vous avez terminer toute les modification que vous souhaitiez faire durant votre session de reporting (notez que vous ajouter plusieurs fichiers à la fois, il est également necessaire d'ajouter les images que vous uploader de la même manière) cliquez sur le menu déroulant et choisissez `Commit & Push` l'action de commit regroupe toute vos modifications n'oubliez pas d'ajouter un message significatif de vos modification par convention pas plus d'une ligne et en anglais eg : "Add reporting of week 3", et l'action de `Push` enverras directement vos modification sur le repository distant sur GitHub.

<figure style="text-align: center;">
  <img src="/docs/annex/images/commit_and_push.png"  width="400">
  <figcaption> Commit des modifications </figcaption>
</figure>

Vous pouvez prévisualisez les modifications de votre fichiers en Markdown sur `VSCode` avec `Ctrl + Shift + V` en séléctionnant d'abord le fichier. Un pipeline d'action Github mis en place sur le repository est configuré pour compilé la page github et la redéployer sur `Github Pages` à chaque `Push`, les modifications peuvent prendre quelque minutes avant d'être visible sur la page.


## References

- [*The Git Community Book*](https://shafiul.github.io/gitbook/index.html)
- [Tech Talk: Linus Torvalds on Git (YouTube)](http://www.youtube.com/watch?v=4XpnKHJAok8)
