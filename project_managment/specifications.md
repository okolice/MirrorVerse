# MirrorVerse

Élèves : Guillaume Calderon, Mohammed Ali, Eymeric Déchelette

Enseignant : Jérôme Bastien

## Cahier des charges

### Contexte

Ce projet prend la suite d'une demande d'un élève, Quentin COURDERO en troisième année en informatique à Polytech. Il a demandé à son enseignant Jérôme Bastien  de l'aider à écrire un algorithme pour déterminer le trajet d’un rayon lumineux qui vient frapper (ou pas) un miroir plan fini. 

### Objectif

L'objectif de ce projet est d'étudier le comportement d'un rayon lumineux lorsqu'il rencontre des miroirs.

Un rayon lumineux peut avoir deux comportements : il peut se retrouver piégé dans le nid de mirroirs, ou parvenir à sortir du nid de mirroirs.

Sa trajectoire peut suivre un motif ou être chaotique.
On considérera qu'une trajectoire est chaotique si, après n réflexions (n dépendant du cas étudié), on ne constate aucune répétition.

Pour ce faire, on codera un outil simulant le comportement de rayons lumineux lorsqu'ils rencontrent des miroirs.
La simulation devra physiquement être juste, c'est à dire coller au maximum à la réalité.
Elle s'appuiera sur la seconde loi de Snell-Descartes et devra obligatoirement fonctionner en 2 dimensions avec des miroirs plans.
Elle pourra être enrichie avec plus de dimensions et de variété de miroirs.

### Réponse technique

Le simulateur sera développé avec le langage Rust afin d'avoir un maximum d'optimisation et de s'assurer d'un minimum de bugs imprévus.

On utilisera la librairie nAlgebra afin de pouvoir manipuler aisément différentes notions mathématiques telles que les vecteurs, les points, etc.

La simulation disposera d'un outil de visualisation permettant de se déplacer dans le monde virtuel pour constater simplement le résultat de la simulation.

L'outil de visualisation sera développer à l'aide de la librairie wgpu.

### Potentiel difficulté

La première difficulté sera de détecter efficacement l'intersection entre les rayons et les miroirs.

La technologie d'affichage demandera aussi probablement beaucoup de recherche documentaire en raison du fait qu'elle est assez nouvelle pour les réalisateurs du projet.


### Milestones

#### Fonctionnalités v1

- On devra pouvoir éditer facilement l'ensemble des miroirs pour la simulation. Probablement via une simple description en JSON.
- On devra également pouvoir choisir la direction et le point de départ du rayon.
- On devra pouvoir visualiser aisément le trajet du rayon lumineux.
- On devra supporter les miroirs plans.
- La simulation devra au moins fonctionner en 2D.
 La V1 utilisera des bases locales et des symétries plutôt que des angles afin d'anticiper la généralisation en 3D.


#### Fonctionnalités v2

- On devra supporter les types de miroirs :
    + plan
    + circulaire
    + en courbe de Bézier

#### Fonctionnalités v3

- La simulation devra au moins fonctionner en 3D (ou ND).

#### Fonctionnalités v4

- on devra ajouter, selon les besoins, des fonctionnalités d'analyse de la trajectoire du rayon :
    + détection automatique de la sortie de l'ensemble.
    + détection automatique d'une boucle (le rayon passe 2 fois au même endroit)

## Organisation temporelle

```mermaid
gantt
    title le diagramme de Gantt
    dateFormat  DD/MM/YYYY
    tickInterval 14day

    section Version 1
    Réflexion, création du cahier des charges    :done, a1, 01/02/2024, 14d
    Début de la programmation   :milestone, done, m1, after a1,
    Création affichage  :active, after a1, 7d
    Création architecture miroir   :active, after a1, 7d
    Création réflexion basique rayon   :active, a2, after a1, 7d
    Liaison des différentes parties  :a3, after a2, 7d
    Tests d'intégration :a4, after a3, 4d
    fin de la version 1 :milestone, m2, after a4,

    section Version 2
    Amélioration affichage  :after m2, 7d
    Création de nouveau miroir   :after m2, 7d
    Nouvelles réflexions    :a5, after m2, 7d
    Liaison des différentes parties  :a6, after a5, 7d
    Tests d'intégration :a7, after a6, 4d
    fin de la version 2 :milestone, m3, after a7,

    section Version 3
    Généralisation affichage  :after m3, 7d
    Généralisation des miroirs   :after m3, 7d
    Généralisation des réflexions    :a8, after m3, 7d
    Liaison des différentes parties  :a9, after a8, 7d
    Tests d'intégration :a10, after a9, 4d
    fin de la version 3 :milestone, m4, after a10,

    section Version 4
    Adaptation de la structure du programme  :a11, after m4, 7d
    Développement détecteur de récurrence   :after a11, 7d
    Développement du détecteur de sorties    :a12, after a11, 7d
    Liaison des différentes parties  :a13, after a12, 7d
    Tests d'intégration :a14, after a13, 4d
    fin de la version 4 :milestone, m5, after a14,

    section Analyse et rapport
    Essaie de simulation    :a15, after m5, 3d
    Analyse des résultats   :a16, after a15, 4d
    Écriture d'un rapport d'analyse :a17, after a16, 4d
    fin de projet   :milestone, m6, after a17,
```


