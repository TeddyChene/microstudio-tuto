# Tutoriel: Bases de programmation

:project Bases de programmation {"language": "python"}

<!-- Introduction / premiers pas -->
<!-- Variables -->
<!-- Fonctions -->
<!-- Listes -->
<!-- Conditions -->
<!-- Boucles -->
<!-- Objets -->
<!-- Fonctions prédéfinies -->
<!-- Structure d'un programme microStudio -->

<!-- Programmation avancée : fonctions récursives -->
<!-- Programmation avancée : fonctions membres d'un objet -->
<!-- Programmation avancée : contexte local, global, objet -->


## Introduction

:overlay

:position 30,30,40,40

:navigate projects.code

### Programmation

Dans cette série de tutoriels, nous allons découvrir la programmation
avec **Python**.

Cliquez sur le bouton suivant pour continuer :

:navigate projects.code

:highlight #tutorial-window .navigation .next

## Console

:navigate projects.code

:position 10,20,40,80

### Console

Pour découvrir la programmation, nous allons jouer avec
la console de microStudio. La console permet de discuter avec l'ordinateur
en tapant du texte (du code) et en lisant ses réponses.

:highlight #terminal

## Entrée console

:navigate projects.code

Pour commencer à programmer, cliquez sur la zone d'entrée de texte
de la console.

:highlight #terminal-input-line

:auto

## Tapez un mot

:navigate projects.code

### Tapez un mot

Saisissez un mot au clavier, par exemple :

```
salut
```

Puis validez en tapant sur la touche [Entrée] ou [⏎]

:auto #terminal-input

## Réponse

:navigate projects.code

Si vous avez tapé ```salut```, Python vous a répondu ```NameError: name 'salut' is not defined```.

Ne soyez pas contrarié, il n'a pas voulu être impoli ! Un ordinateur a en
fait très peu d'intelligence. Il est capable de travailler dur, mais il
faut lui dire exactement ce qu'on attend de lui.

La programmation consiste
à expliquer à l'ordinateur ce qu'il doit faire, en utilisant un langage
qu'il comprend.

## Réponse 2

:navigate projects.code

Si l'ordinateur a répondu ```NameError: name 'salut' is not defined```, c'est qu'il ne connaît pas ```salut``` ! Il
a pourtant cherché dans sa mémoire une *variable* qui s'appellerait ainsi et n'a
rien trouvé.

Il a donc répondu ```NameError: name 'salut' is not defined``` qui pour lui signifie aussi rien, pas trouvé,
inconnu au bataillon. Essayons donc de l'instruire un peu, tapez :

```
salut = 5
```

:auto #terminal-input

## Assigner une variable

:navigate projects.code

En validant cette ligne, nous avons *assigné* ou *affecté* la valeur `5` à la *variable* ```salut```.
L'ordinateur a créé une case dans sa mémoire, étiquetée &laquo;salut&raquo; et dans laquelle
il a stocké la valeur `5`.

Si maintenant nous l'interrogeons à nouveau :

```
salut
```

L'ordinateur répond `5` ! On dirait qu'il a enfin appris quelque chose.

## Calculer

:navigate projects.code

Mais sait-il au moins compter ? Essayons :

```
1+1
```

Impressionnant non ? Allez encore :

```
salut*2
```

OK là ça devient très fort, on dirait qu'il peut utiliser sa mémoire et calculer
simultanément.
Nous pouvons certainement en tirer quelque chose. Il est temps de passer au
tutoriel suivant pour en apprendre plus sur les variables.

## Fin
:position 30,30,40,40

:navigate tutorials

:overlay

Ce tutoriel est terminé. Pour en apprendre plus sur la programmation *Python*, 
vous pouvez maintenant lancer le tutoriel sur les &laquo;Variables&raquo;.
