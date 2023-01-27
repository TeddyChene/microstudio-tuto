# Tutoriel : Listes

:project Bases de programmation {"language": "python"}

## Les listes

:overlay

:position 30,30,40,40

:navigate projects.code

### Les listes

Dans tout langage de programmation, il est utile de pouvoir rassembler des
informations dans des listes. Les listes sont modifiables (on peut ajouter des éléments
et en enlever). Le tutoriel sur les boucles expliquera comment effectuer un traitement
sur tous les éléments d'une liste.

## Définition d'une liste

:navigate projects.code

:position 10,20,40,60

### Création d'une liste

En *Python*, une liste se définit comme suit :

```
nombres_premiers = [1, 3, 5, 7, 11, 13, 17]
animaux = ["chat", "chien", "lapin"]
```

Notez que les crochets pour délimiter la liste et les virgules pour séparer
les éléments de la liste. Les éléments d'une liste peuvent être n'importe quelle
valeur *Python* : nombres, textes, listes (!), objets.

## Liste vide

:navigate projects.code

:position 10,20,40,60

### Liste vide

Une liste vide se définit comme suit :

```
liste = []
# ou
liste = list()
```

## Ajouter un élément

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Ajouter un élément


On peut y ajouter un `element` a une liste avec la fonction ```append```

```
liste.append(element)
```

La fonction ```append``` ajoute les éléments à la fin de la liste.

**Exemple à essayer dans la console:**

```python
> liste = [1, 2, 3, 4]
> liste.append(6)
> print(liste)
[1, 2, 3, 4, 5, 6]
```

## Insérer un élément

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Insérer un élément

On peut insérer un `element` à la position `i` en utilisant la fonction  ```insert```

```
liste.insert(element, i)
```

**Exemple à essayer dans la console :**

```python
> liste = ["a", "b", "d", "e"]
> liste.insert("c", 2)
> print(liste)
["a", "b", "c", d", "e"]
```

La position ou &laquo;**indice**&raquo; des éléments d'une liste sont numérotés à partir de `0`.
Insérer `"c"` à l'indice `2` de `liste` revient donc à insérer cet élément entre `"b"` et `"d"`.

## Longueur d'une liste

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Longueur d'une liste

On peut connaître la longueur d'une liste (le nombre d'éléments) avec la fonction `len`.

```
len(liste)
```

**Exemple à essayer dans la console :**
```python
> liste = ["a", "b", "c", d", "e"]
> print(f"La longueur de la liste est {len(liste)}")
La longueur de la liste est 5
```

## Accès aux éléments de la liste

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Accès aux éléments

Les éléments d'une liste sont numérotés en partant de 0. On peut alors accéder
à chaque élément d'une liste avec l'écriture suivante :

```
liste[0]
liste[1]
```

Si l'indice de la liste n'est pas défini Python retourne l'erreur `IndexError: list index out of range`

**Par exemple à essayer dans la console:**

```
> liste = ["a", "b", "c"]
> liste[3]
IndexError: list index out of range
```

## Modifier un élément

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Modifier un élément

On peut modifier un élément de la liste en le référençant avec son indice.

**Exemple à essayer dans la console:**

```
> liste = [1, 2, 4, 5]
> liste[2] = 3
> print(liste)
[1, 2, 3, 5]
```

Si l'élément n'existe pas encore, Python retourne l'erreur `IndexError: list index out of range`:

**Exemple à essayer dans la console:**
```
> liste = [1, 2, 3, 5]
> liste[4] = 6
IndexError: list index out of range
```

## Connaître l'indice d'un élément

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Indice d'un élément

L'indice d'un élément, c'est à dire son numéro, peut être trouvé avec la fonction ```index``` :

```
liste.index(element)
```

**Exemple à essayer dans la console:**

```python
> liste = ["a", "b", "c", "d"]
> indice_b = liste.index("b")
> print(indice_b)
1
```

## Enlever un élément

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Enlever un élément

On peut enlever un élément de la liste avec la fonction `pop` si on connaît son indice (son numéro) :

```
element_a_enlever = liste.pop(indice)
```

**Exemple à essayer dans la console:**
```python
> liste = ["a", "b", "c", "d"]
> element = liste.pop(2)
> print(liste)
["a", "b", "d"]
> print(element)
c
```

La fonction `pop` renvoie l'élément qu'elle a retiré de la liste. Lorsque `pop` est utilisé 
sans paramètre, elle retire et renvoie le dernier élément de la liste. 

**Exemple à essayer dans la console:**
```python
> liste = ["a", "b", "d"]
> dernier_element = liste.pop()
> print(liste)
["a", "b"]
> print(dernier_element)
d
```

## Enlever un élément

:navigate projects.code

:position 10,20,40,60

:highlight #terminal-input-line

### Enlever un élément

On peut enlever un élément de la liste avec la fonction `remove` si on connaît sa valeur :

```
liste.remove(element)
```

**Exemple à essayer dans la console:**
```python
> liste = ["a", "b", "c", "d"]
> liste.remove("c")
> print(liste)
["a", "b", "d"]
```

La fonction `remove` ne renvoie pas l'élément qu'elle a retiré de la liste. Lorsque l'élément que 
l'on chercher à supprimer de la liste n'existe pas, Python renvoie l'erreur `ValueError`.

**Exemple à essayer dans la console:**
```python
> liste = ["a", "b", "d"]
> liste.remove("e")
ValueError: e is not in list
```

## Listes

:navigate projects.code

:position 10,20,40,60

### Listes

Les listes sont un outil très utile dont vous comprendrez mieux l'intérêt lorsque
nous étudierons les boucles. Il est temps de passer au tutoriel suivant !

## Fin
:position 30,30,40,40

:navigate tutorials

:overlay

Ce tutoriel est terminé. Pour en apprendre plus sur la programmation *Python*, 
vous pouvez maintenant lancer le tutoriel sur les &laquo;Conditions&raquo;.
