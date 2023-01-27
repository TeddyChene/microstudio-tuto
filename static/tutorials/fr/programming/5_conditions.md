# Tutoriel: Conditions

:project Bases de programmation {"language": "python"}

## Conditions

:overlay

:position 30,30,40,40

:navigate projects.code

### Conditions

Les conditions ou *instructions conditionnelles*,
représentent la possibilité pour le programme de prendre des décisions.
Il s'agit de tester une hypothèse et d'effectuer des
opérations différentes selon que le résultat est vrai ou faux.


## Vocabulaire

:navigate projects.code

:position 30,20,50,70

### Vocabulaire

Les instructions conditionnelles se construisent avec les mots-clé ```if``` et ```else```.

|mot-clé|signification|
|-|-|
|```if```|&laquo;si&raquo; ; suivi d'une hypothèse ou *condition*|
|```else```|&laquo;sinon&raquo; ; suivi des instructions à exécuter si la condition est fausse|

## Condition simple

:navigate projects.code

:position 55,20,45,70

:highlight #editor-view

### Condition simple

Dans l'éditeur  de code, définissons la fonction suivante :

```
def test(nombre):
  if nombre < 0:
    print(f"Le nombre {nombre} est strictement négatif")
```

Cette fonction accepte un nombre `nombre` en paramètre. Elle teste *si* (```if```) le nombre est inférieur
à zéro. Si oui, alors l'instruction ```print(f"Le nombre {nombre} est strictement négatif")``` est exécutée.
La condition de l'instruction conditionnelle se termine par `:` et les instructions a exécutée en cas
de condition vraie sont indentées (regroupées dans un *bloc conditionel*).

## Condition simple

:navigate projects.code

:position 55,20,45,45

:highlight #terminal-input-line

### Condition simple

Dans la console, testons notre fonction ! Essayez par exemple :

```
test(10)
test(-5)
test(0)
test(-100)
```

## Condition simple

:navigate projects.code

:position 55,20,45,70

:highlight #editor-view

### Et sinon ?

Le mot clé ```else``` permet d'exécuter une suite d'instructions différentes dans le cas
ou la condition testée par le ```if``` est fausse. Exemple :

```
def test(nombre):
  if nombre < 0:
    print(f"Le nombre {nombre} est strictement négatif")
  else:
    print(f"Le nombre {nombre} est positif")
```

## Condition simple

:navigate projects.code

:position 55,20,45,45

:highlight #terminal-input-line

### Positif ou négatif ?

Dans la console, testons à nouveau quelques valeurs :

```
test(1)
test(-15)
```

## Condition simple

:navigate projects.code

:position 55,20,45,70

:highlight #editor-view

### Et sinon si ?

*Python* propose un dernier mot-clé ```elif``` qui est une contraction de `else`
et `if`. Il signifie littéralement "Et sinon si ?" et permet donc d'enchaîner les tests
pour isoler plus de deux possibilités différentes. Exemple :

```
def test(nombre):
  if nombre < 0:
    print(f"Le nombre {nombre} est strictement négatif")
  elif nombre > 0:
    print(f"Le nombre {nombre} est strictement positif")
  else:
    print("Le nombre est égal à 0")
```

## Condition simple

:navigate projects.code

:position 55,20,45,45

:highlight #terminal-input-line

### 3 possibilités

Notre code est maintenant capable de distinguer 3 cas : nombre strictement négatif, nombre strictement positif
et nombre égal à 0. Testons dans la console !

```
test(1)
test(-15)
test(0)
```

## Condition simple

:navigate projects.code

:position 30,20,50,50

### Attention aux oublis

Lorsque vous écrivez une expression conditionnelle, attention de ne pas oublier
le symbole ```:``` à la fin de chaque condition suivant le ```if``` et chaque ```elif``` et à la fin du `else`.

De même, n'oubliez pas d'indenter les instructions à exécuter dans chaque cas.

## Fin
:position 30,30,40,40

:navigate tutorials

:overlay

Ce tutoriel est terminé. Pour en apprendre plus sur la programmation *Python*, 
vous pouvez maintenant lancer le tutoriel sur les &laquo;Boucles&raquo;.
