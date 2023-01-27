# Tutoriel: Objets

:project Bases de programmation {"language": "python"}

## Objets

:overlay

:position 30,20,40,60

:navigate projects.code

### Objets

Les objets en Python peuvent être comparés aux objets dans la vie réelle. Un
objet est une entité qui a un ensemble de propriétés. Il peut être assigné à une
variable, passé en paramètre à une fonction etc.

Les propriétés d'un objet, appelées aussi **attributs** peuvent être considérées comme des sous-variables, des variables
qui sont internes à l'objet.

## Objet

:navigate projects.code

:position 55,20,45,45

:highlight #editor-view

### Créer un objet

La création d'un objet commence avec la définition d'une classe à l'aide du mot-clé ```class```. 
Une première fonction interne à la classe appelée **constructeur** est ensuite donnée pour définir 
les différents attributs de l'objet, elle est nommée `__init__` pour &laquo;initialisation&raquo;.

Une bonne pratique consiste a écrire le nom de la classe avec la première lettre en majuscule.

**Exemple à essayer dans l'éditeur de code:**

```python
class Chaise():
  """Classe Chaise"""

  def __init__(self, nb_pieds, couleur, style):
    """Constructeur de la classe Chaise"""
    self.pieds = nb_pieds
    self.couleur = couleur
    self.style = style
```

**Instruction à écrire dans la console:**

```
> ma_chaise = Chaise(4, "blanche", "bois")
```

Le mot-clé `self` fait référence à l'objet que l'on va créer avec cette classe. Il faut
penser que la classe est un &laquo;moule&raquo; qui nous servira à construire des objets 
de la même famille.

## Accéder aux propriétés de l'objet

:navigate projects.code

:position 55,20,45,45

:highlight #terminal-input-line

### Accéder aux propriétés de l'objet

Une fois que votre objet est créé, vous pouvez accéder à ses propriétés comme suit :

**Instruction à essayer dans la console:**
```
> ma_chaise = Chaise(4, "blanche", "bois")
> ma_chaise.pieds
4
> ma_chaise.style
bois
```

## Assigner des propriétés à un objet

:navigate projects.code

:position 55,20,45,45

:highlight #terminal-input-line

### Assigner des propriétés à un objet


Vous pouvez modifier les propriétés d'un objet ou en définir de nouvelles:

```
> ma_chaise.couleur = "rouge"
> ma_chaise.roues = 5
```

On évitera cependant de créer de nouveaux attributs sans les définir avant dans le constructeur `__init__`.

## Set object properties

:navigate projects.code

:position 55,20,45,45

:highlight #editor-view

### Accéder et modifier les attributs

Une bonne pratique consiste à utiliser des **accesseurs** (ou *getters*) pour accéder aux valeurs
des attributs d'un objet et des **mutateurs** (ou *setters*) pour modifier les valeurs des
attributs d'un objet. 

Les fonctions d'une classe sont appelées des **méthodes**. 

Ajouter les deux méthodes ci-dessous à la classe `Chaise` : 

```python
  # Accesseur
  def get_couleur(self):
    """Renvoie le nombre de pieds de la chaise"""
    return self.couleur
    
  # Mutateur
  def set_couleur(self, nouvelle_couleur):
    """
    Modifie la couleur de la chaise
    Renvoie True si la modification a été effectuée et False sinon
    """
    if type(nouvelle_couleur) == str:
      self.couleur = nouvelle_couleur
      return True
    else:
      return False
```

## Set object properties

:navigate projects.code

:position 55,20,45,45

:highlight #editor-view

### Accéder et modifier les attributs

La classe `Chaise` ressemble alors à ceci : 

```python
class Chaise():
  """Classe Chaise"""

  def __init__(self, nb_pieds, couleur, style):
    """Constructeur de la classe Chaise"""
    self.pieds = nb_pieds
    self.couleur = couleur
    self.style = style

  # Accesseur
  def get_couleur(self):
    """Renvoie le nombre de pieds de la chaise"""
    return self.couleur
    
  # Mutateur
  def set_couleur(self, nouvelle_couleur):
    """
    Modifie la couleur de la chaise
    Renvoie True si la modification a été effectuée et False sinon
    """
    if type(nouvelle_couleur) == str:
      self.couleur = nouvelle_couleur
      return True
    else:
      return False
```

## Set object properties

:navigate projects.code

:position 55,20,45,45

:highlight #terminal-input-line

### Accéder et modifier les attributs

Dans la console, exécutez les instructions ci-dessous : 

```python
> ma_chaise = Chaise(4, "rouge", "bois")
> ma_chaise.get_couleur()
rouge
> print(ma_chaise.set_couleur(3))
False
> print(ma_chaise.set_couleur("bleu"))
True
> ma_chaise.get_couleur()
bleu
```

L'utilisation de *mutateurs* pour modifier la valeur d'un attribut permet de sécuriser le programme.
Une bonne pratique consiste à retourner `True` si la modification a été effectuée et `False` sinon.

Un inconvénient est que cette pratique rallonge considérablement la longueur du programme.

## Types de propriétés

:navigate projects.code

:position 55,20,45,45

:highlight #editor-view

### Types des attributs

Les attributs d'un objet peuvent avoir n'importe quelle type Python : un nombre,
une *chaîne de caractères*, une liste, un dictionnaire, un objet.

Jouons encore avec les objets en créant une nouvelle classe `Piece`:

```python
class Piece():
  """Classe Pièce"""
  def __init__(self, description, surface):
    """Constructeur de la classe Pièce"""
    self.meubles = []
    self.description = description
    self.surface = surface
```

Maintenant nous pouvons créer une relation entre nos deux objets avec les instructions suivantes :

```python
> ma_chambre = Piece("Chambre enfant", 10)
> ma_chaise = Chaise(4, "bleu", "plastique")
> ma_chambre.meubles.append(ma_chaise)
> ma_chambre.meubles
```
Nous venons donc de créer un objet `ma_chambre` et un objet `ma_chaise`. Nous avons ensuite
affecté `ma_chaise` à la liste des `meubles` de `ma_chambre`.

Il aurait cependant été préférable d'utiliser un mutateur pour réaliser cette opération. On
s'assurerait alors que `ma_chaise` est bien un objet de type `Chaise`.

Ajoutez le mutateur `ajoute_chaise` à la classe `Piece`. (solution à la suite)

## Types de propriétés

:navigate projects.code

:position 55,20,45,45

:highlight #editor-view

### Types des attributs

Vous obtenez alors le code suivant pour la classe `Piece` : 

```python
class Piece():
  """Classe Pièce"""
  def __init__(self, description, surface):
    """Constructeur de la classe Pièce"""
    self.meubles = []
    self.description = description
    self.surface = surface
    
  # Méthode
  def ajoute_chaise(self, une_chaise):
    """Ajoute une chaise à la pièce"""
    if isinstance(une_chaise, Chaise):
      self.meubles.append(une_chaise)
      return True
    else:
      return False
```

Les instructions à utiliser sont désormais : 

```python
> ma_chambre = Piece("Chambre enfant", 10)
> ma_chaise = Chaise(4, "bleu", "plastique")
> ma_chambre.ajoute_chaise(ma_chaise)
```

## Fin

:position 30,30,40,40

:navigate tutorials

:overlay

### The end !

Nous avons atteint la fin de cette série sur la programmation. Lorsque vous recherchez
plus de détails, pensez à consulter la documentation de microStudio. Vous pouvez aussi
refaire tel ou tel tutoriel pour vous rafraîchir la mémoire si le besoin s'en fait
ressentir.

Il est temps pour vous de créer votre premier projet microStudio ! Vous pouvez essayer
les autres tutoriels ou visiter la section Exploration pour découvrir d'autres projets et voir comment ils sont codés.
