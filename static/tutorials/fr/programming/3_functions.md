# Tutoriel : Fonctions

:project Bases de programmation {"language": "python"}

## Les fonctions

:overlay

:position 30,30,40,40

:navigate projects.code

### Les fonctions

Une fonction est un sous-programme qui effectue une tâche bien définie et
qui peut retourner un résultat. Les fonctions permettent de mieux structurer un
programme.

Pendant ce tutoriel, n'hésitez pas à recopier les divers exemples dans la console
ou à expérimenter avec les vôtres.

## Appeler une fonction

:navigate projects.code

:position 10,20,40,60

### Appeler une fonction

Pour appeler une fonction (c'est à dire exécuter le sous-programme), on écrit
son identifiant puis une liste de paramètres entre parenthèses. Par exemple,
en Python, la fonction prédéfinie ```max``` retourne le plus grand de deux
nombres :

```
max(12, 17)
```

Il existe beaucoup d'autres fonctions prédéfinies, dont vous trouverez la liste
dans la documentation.

## Appeler une fonction

:navigate projects.code

:position 10,20,40,60

### La fonction print

La fonction ```print``` écrit dans la console ce qu'on lui passe en paramètre.
Elle peut être utile pour vérifier que le programme agit comme prévu et produit
les bons résultats.

Exemple :

```
print(f"Le maximum entre 12 et 17 est {max(12, 17)}")
```

Le `f` devant les guillemets et les accolades autour de `max(12, 17)` permettent de 
transformer le résultat de la fonction `max`, qui est un entier, en une chaîne de caractères. 

Il existe beaucoup d'autres fonctions utiles à connaître. Mais avant tout,
nous allons apprendre à créer nos propres fonctions.

## Créer une fonction

:position 60,10,40,45

:navigate projects.code

:highlight #editor-view

### Définir une fonction

Supprimer les trois fonctions prédéfinies dans l'editeur de code. Puis, écrivez :

```
def moyenne(x, y):
  resultat = (x + y) / 2
  return resultat
```

Ci-dessus, nous utilisons le mot clé `def` pour définir la fonction nommée ```moyenne```. 
Cette fonction, accepte deux paramètres ```x``` et ```y```. Le sous-programme est très simple,
il affecte à `resultat` le résultat du calcul ```(x + y) / 2```, puis le retourne. 

On distingues les instructions de la fonction des instructions globales par leur
indentation. Ces instructions définissent alors un bloc.

## Utiliser notre fonction

:position 60,10,40,45

:navigate projects.code

:highlight #terminal-input-line

### Utiliser notre fonction

Nous pouvons maintenant utiliser notre fonction ```moyenne```. Ecrivez :

```
moyenne(14, 16)
```

ou

```
moyenne(10, 13)
```

## Paramètres

:position 60,10,40,45

:navigate projects.code

:highlight #terminal-input-line

### Valeurs passées en paramètres

Les valeurs passées en paramètre à une fonction peuvent être n'importe quelle *expression*,
c'est à dire un nombre, une variable, un autre appel de fonction. On peut donc tout à fait écrire :

```
moyenne(10+2, 8+5)
```

ou encore :

```
moyenne(moyenne(5, 18), moyenne(11, 20))
```

Mais il est préférable d'utiliser des variables, car le code perd en lisibilité lorsqu'il est
écrit de cette façon.

## Variables locales

:position 60,10,40,45

:navigate projects.code

:highlight #editor-view

### Variable locales

Une fonction peur recourir à des variables locales. Comme leur nom l'indique, ces variables n'existent
que dans le contexte de la fonction où elles sont définies. On dit que leur *visibilité*, ou *portée*
est limitée au corps de la fonction.

Écrivez dans l'editeur de code la fonction ci-dessous :

```python
def somme_carres(a, b):
  somme = 0
  somme = somme + a * a
  somme = somme + b * b
  return somme
```

## Variables locales

:position 60,10,40,45

:navigate projects.code

:highlight #terminal-input-line

### Variable locales

Notre fonction ```somme_carres``` fait la somme des carrés de ses deux paramètres. 

Écrivez dans la ligne de commande de la console:

```
somme_carres(3, 4)
```

Le résultat retourné par la fonction s'affiche. Maintenant écrivez dans la ligne de commande de la console
la variable ```somme``` :

```
NameError: name 'somme' is not defined
```

Etant sortis du contexte d'exécution de la fonction, la variable locale ```somme``` n'est plus
définie. Elle n'existe pas dans le *contexte global*.

## Variables globales

:position 60,10,40,45

:navigate projects.code

:highlight #editor-view

### Variable globales

Dans l'editeur de code, modifiez la fonction `somme_carre` en y ajoutant l'instruction `global somme` :

```python
def somme_carres(a, b):
  global somme
  somme = 0
  somme = somme + a * a
  somme = somme + b * b
  return somme
```

Dans la ligne de commande de la console, écrivez : 

```
somme_carres(3, 4)
```

Puis, vérifiez que `somme` est bien définie et renvoie bien une valeur.

## Fin
:position 30,30,40,50

:navigate tutorials

:overlay

### Les fonctions

Nous avons déjà appris l'essentiel sur les fonctions ! Nous allons maintenant aborder
dans la suite de ce parcours :

* Comment créer et utiliser des listes
* Comment faire des choix avec les conditions ```if```
* Comment répéter des tâches avec les boucles ```for``` et ```while```
