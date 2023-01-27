# Tutoriel: Boucles

:project Bases de programmation {"language": "python"}

## Boucles

:overlay

:position 30,30,40,40

:navigate projects.code

### Les boucles

Les boucles permettent de répéter les mêmes instructions un grand
nombre de fois. Elles sont utiles par exemple pour effectuer un traitement
sur tous les éléments d'une liste, ou pour répéter un travail jusqu'à ce
qu'une condition particulière soit remplie.

## Boucle ```for```

:navigate projects.code

:position 55,15,45,40

:highlight #editor-view

### Boucle ```for```

Le mot-clé ```for``` permet de créer une boucle avec une variable dont la valeur
va changer à chaque répétition de la boucle. 

Dans l'editeur de code, écrivez :

```
def boucle_pour():
  for i in range(10):
    print(i)
```

Puis exécuter cette fonction dans la console : 

```
> boucle_pour()
```

Dans la boucle ci-dessus, la variable `i` va prendre successivement les valeurs
`0`, `1`, `3` ... jusqu'à `9`. Pour chacune de ces valeurs, la fonction ```print(i)``` sera
appelée. Il y aura alors `10` répétition de l'instruction `print(i)`. Les instructions a répéter
dans cette boucle sont indentées (regroupées dans un bloc)

## Boucle ```for```

:navigate projects.code

:position 55,15,45,40

:highlight #editor-view

### Boucle ```for```

La fonction ```range``` peut prendre jusqu'à trois paramètres: le `début`, la `fin` (cette 
valeur est exclue) et l'`incrément` utilisé pour chaque itération
(c'est à dire le &laquo;pas&raquo; ou de combien la variable `i` doit être augmentée à chaque itération)
.

Dans l'editeur de code, modifiez votre fonction `boucle_pour` ainsi :

```
def boucle_pour():
  for i in range(1, 10, 2):
    print(i)
```

Puis exécuter cette fonction dans la console : 

```
> boucle_pour()
```

Vous pouvez aussi essayer d'autres valeurs.

## Boucle ```for```

:navigate projects.code

:position 55,15,45,40

:highlight #editor-view

### Boucle ```for```

Voici comment faire un compte à rebours en bonne et due forme !

Dans l'editeur de code, modifiez votre fonction `boucle_pour` ainsi :

```
def boucle_pour():
  for i in range(10, 0, -1):
    print(i)
```

Puis exécuter cette fonction dans la console : 

```
> boucle_pour()
```

Vous pouvez aussi essayer d'autres valeurs.

## Itération sur une liste

:navigate projects.code

:position 55,15,45,40

:highlight #editor-view

### Itération sur une liste

Voici comment effectuer un traitement répété sur tous les éléments d'une liste avec
```for``` suivi du mot-clé ```in```.

Dans l'editeur de code, modifiez votre fonction `boucle_pour` ainsi :

```
def boucle_pour():
  liste = ["chien","chat","souris"]
  for animal in liste:
    print(animal)
```

Puis exécuter cette fonction dans la console : 

```
> boucle_pour()
```

On parle alors de faire une *itération* sur la liste.

## Tant que

:navigate projects.code

:position 55,15,45,40

:highlight #editor-view

### Répéter tant que (...)

L'instruction ```while``` permet de répéter une séquence d'opérations tant qu'une
condition reste vraie. Exemple :

Dans l'editeur de code, écrivez :

```python
def boucle_tantque():
  i = 1
  while i < 1000:
    print(i)
    i = i * 2
```

Puis exécuter cette fonction dans la console : 

```
> boucle_tantque()
```

Les opérations de la boucle ci-dessus seront répétées tant que la variable `i` reste
inférieure à `1000`. Dès que la condition n'est plus remplie, l'exécution sort de la boucle
et exécute la suite du programme.


## Attention

:navigate projects.code

:position 55,15,45,40

### Précautions

Lorsque vous écrivez une boucle ```for``` ou ```while``` n'oubliez pas de terminer l'instruction
par `:` et d'indenter le bloc d'instructions à répéter. 

Posez-vous aussi la question de la condition d'arrêt :
est-ce que ma boucle va bien s'arrêter ? Attention de ne pas créer de boucle perpétuelle,
comme celle ci-dessous :

```
def boucle_infini():
  i = 1
  while i < 1000:
    print(i)
```

Dans l'exemple ci-dessus, la boucle ne s'arrêtera jamais, puisque rien ne fait
changer la valeur de `i` dans le corps de la boucle. N'exécutez pas cette fonction car 
le navigateur web risque de ne plus répondre. Vous serez alors contraint de fermer la page.

## Fin
:position 30,30,40,40

:navigate tutorials

:overlay

Ce tutoriel est terminé. Pour en apprendre plus sur la programmation *Python*, 
vous pouvez maintenant lancer le tutoriel sur les &laquo;Objets&raquo;.
