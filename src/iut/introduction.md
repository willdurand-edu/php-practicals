Introduction
============

Ce guide d'introduction est écrit en français, mais ne vous y habituez pas trop,
les sujets de TPs sont écrits en anglais.

* [Guide de survie avec Git](#guide-de-survie-avec-git)
* [Guide de survie avec `vi`](#guide-de-survie-avec-vi)

Guide de survie avec Git
------------------------

`git` est un gestionnaire de version distribué massivement utilisé dans le
monde Open Source grâce à [GitHub](http://github.com), mais également chez
Google, Facebook, Yahoo, Amazon, et autres petites sociétés du web.

La [documentation](http://git-scm.com/book) est bien
faite et très progressive. Il est possible de la télécharger en pdf :
[Pro Git PDF](https://github.s3.amazonaws.com/media/progit.en.pdf). Une version
en français existe paraît-il ;-)

Il existe également un [tutoriel
interactif](http://try.github.com/levels/1/challenges/1) de 15 minutes pour
vous familiariser avec `git`. Vous pouvez le suivre lors de la première séance
de TP !

Les commandes principales pour débuter sont :

    $ git init       # initialise un nouveau dépôt dans le répertoire courant
    $ git status     # affiche l'état du répertoire de travail
    $ git add file   # ajoute `file` à la staging area
    $ git commit     # empile la staging area dans le dépôt
                     # vous entrez votre message de commit dans vi
    $ git push       # vous poussez vos changements sur un serveur central,
                     # utile pour travailler en équipe

En image:

![](../images/git.png)

Vous êtes invités à utiliser `git` pour maintenir la cohérence entre votre
environnement personnel et celui de l'IUT.

Vous pouvez héberger vos dépôts publiquement sur [github.com](http://github.com)
ou de manière privée sur [bitbucket.org](http://bitbucket.org).


Guide de survie avec `vi`
------------------------

Sur un serveur, il n'est pas rare de devoir éditer des fichiers. Sans interface
graphique, le nombre d'éditeurs est limité, mais il y aura toujours `vi`.

Voici quelques commandes de bases :

* `i` : passer en mode insertion
* `esc` : passer en mode commande (les commandes commencent par `:`)
* `:w` : écrit le buffer courant
* `:q` : ferme le buffer actif (quitte vi)
* `:wq` : ecrit et ferme le buffer courant
* `:tabnew file` : ouvre file dans un nouveau buffer
* `gt` : passer au buffer suivant
* `gT` : passer au buffer précédent
* `:30` : aller à la ligne 30
* `:s:regex:replacement:` : chercher remplacer
* `dXd` : coupe X lignes
* `yXy` : copie X lignes
* `p` : coller

Un [guide plus complet](http://www.worldtimzone.com/res/vi.html) est disponible
mais le mieux reste de faire le tutoriel. Pour cela ,taper `vimtutor` dans un
terminal.


---

You can jump to: [Practical Work #1](1.md).
