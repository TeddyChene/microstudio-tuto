# Tutoriel: Premier projet

:project Tutoriel: Premier projet {"language": "python"}

## Premier projet

:position 30,30,40,60

:overlay

### Premier projet

Votre premier projet est déjà initialisé ! Vous allez créer un personnage et
programmer microStudio pour qu'il s'affiche à l'écran et se déplace avec les
touches de votre clavier.


## Créer un sprite

### Créer un sprite <i class="fa fa-map"></i>

Cliquez sur &laquo;**Sprites** <i class="fa fa-map"></i>&raquo; pour accéder à l'éditeur de sprites.

:highlight #projectview .sidemenu #menuitem-sprites

:auto


## Créer un sprite 2

### Créer un sprite <i class="fa fa-map"></i>

Cliquez sur le bouton &laquo;Ajouter un sprite <i class="fa fa-plus-square"></i>&raquo; pour créer un nouveau sprite. On pourra conserver le nom `sprite` attribué par défaut.

:navigate projects.sprites

:highlight #create-sprite-button

:auto


## Dessiner un sprite

:navigate projects.sprites

:position 0,50,30,40

### Dessinez un personnage <i class="fa fa-map"></i>

Utilisez les outils de dessin à droite de l'écran pour dessiner votre personnage.
Vous pouvez y passer le temps que vous voulez !

Lorsque votre sprite est prêt, passez à l'étape suivante.


## Code 1

### Code <i class="fa fa-code"></i>

Cliquez maintenant sur &laquo;**Code** <i class="fa fa-code"></i>&raquo;, nous allons programmer un peu !

:highlight #projectview .sidemenu #menuitem-code

:auto


## Code

:navigate projects.code

:position 55,20,45,80

### Code <i class="fa fa-code"></i>

Le code de votre projet est prérempli avec la définition de trois fonctions :
```init```, ```update``` et ```draw```. Nous allons travailler sur le contenu
de la fonction ```draw```. Ajoutez la ligne suivante dans le bloc de la fonction
```draw```:

```python
  screen.drawSprite("sprite", 0, 0, 20)
```

Votre code ressemble donc à ceci:

```python
def init():
  pass

def update():
  pass

def draw():
  screen.drawSprite("sprite", 0, 0, 20)
```

## Exécuter

:navigate projects.code

:position 55,55,45,35

### Exécution <i class="fa fas-play"></i>

Allez faisons un essai ! Cliquez sur le bouton play pour lancer votre programme.

:highlight #run-button

:auto

## Exécuter

:navigate projects.code

:position 55,55,45,45

### Exécution <i class="fa fas-play"></i>

Votre personnage s'affiche au milieu de l'écran dans la vue d'exécution. La ligne de code que nous avons ajoutée appelle la fonction ```drawSprite``` (dessiner le sprite) sur l'objet ```screen``` (l'écran). Elle donne en paramètres le nom du sprite à afficher ```"sprite"```, les coordonnées `x` et `y` où l'afficher (`(0, 0)` est le centre de l'écran) et la largeur en pixel de l'affichage (`20`).

Vous pouvez jouer avec ces coordonnées pour changer la position de dessin du sprite. Vous constaterez qu'avec microStudio, les modifications sont instantanément reflétées dans la fenêtre d'exécution.

## Ajouter un fond

:navigate projects.code

### Ajouter une couleur de fond

Au-dessus de notre ligne ```screen.drawSprite("sprite", 0, 0, 20)```, nous allons ajouter la ligne suivante :

```python
  screen.fillRect(0, 0, 400, 400, "#468")
```

Votre code ressemble donc à ceci:

```python
def init():
  pass

def update():
  pass

def draw():
  screen.fillRect(0, 0, 400, 400, "#468")
  screen.drawSprite("sprite", 0, 0, 20)
```

```fillRect``` signifie &laquo;remplir le rectangle&raquo;. Le paramètre ```"#468"``` représente une couleur bleu-gris. Cliquez dessus puis maintenez la touche `CTRL` du clavier enfoncée pour faire apparaître une palette <i class="fa fa-palette"></i> de couleurs. Piochez la couleur qui vous convient le mieux !



## Contrôler le personnage

:navigate projects.code

### Contrôler le personnage

Pour contrôler la position du personnage, nous allons utiliser deux variables globales, ```x``` et ```y```. Modifions comme suit la ligne de code qui affiche le sprite :

```python
  screen.drawSprite("sprite", x, y, 20)
```
Oups ! Votre sprite a disparu... 

En effet, les variables `x` et `y` ne sont pas définies. Nous allons les initialiser à `0` dans la fonction `init` 
et indiquer quelles sont globales dans les trois fonctions avec l'instruction `global x, y`:

```python
def init():
  global x, y
  x = 0
  y = 0
```

Votre code ressemble donc à ceci:

```python
def init():
  global x, y
  x = 0
  y = 0

def update():
  global x, y
  pass

def draw():
  global x, y
  screen.fillRect(0, 0, 400, 400, "#468")
  screen.drawSprite("sprite", x, y, 20)
```

Le personnage s'affichera maintenant aux coordonnées ```x``` et ```y```, qui valent pour l'instant `(0, 0)`.

## Contrôler le personnage

:navigate projects.code

### Contrôler le personnage

Il suffit donc maintenant de modifier les variables ```x``` et ```y``` 
lorsque les touches fléchées du clavier sont enfoncées. 
Afin de détecter une entrée sur un périphérique, on utilise la fonction ci-dessous :

```python
def verifie_entree(peripherique, valeur):
  """
  Renvoie True si peripherique a une valeur non nulle
  False si sa valeur est nulle et None si il n'est pas défini
  """
  if hasattr(peripherique, valeur):  # Si il y a une valeur
    return peripherique[valeur] != 0  # True ou False
  else:  # Sinon, il n'y a pas de valeur
    return None
```

La variable `peripherique` peut être égal à `keyboard`, `mouse`, `touch` ou `gamepad`.  

## Contrôler le personnage

:navigate projects.code

### Contrôler le personnage

Insérez l'instruction conditionnelle suivante dans le bloc de la fonction `update` :

```python
  if verifie_entree(keyboard, "LEFT"):
    x = x - 1
```

Votre code complet ressemble donc à ceci:

```python
def verifie_entree(peripherique, valeur):
  """
  Renvoie True si peripherique a une valeur non nulle
  False si sa valeur est nulle et None si il n'est pas défini
  """
  if hasattr(peripherique, valeur):  # Si il y a une valeur
    return peripherique[valeur] != 0  # True ou False
  else:  # Sinon, il n'y a pas de valeur
    return None

def init():
  global x, y
  x = 0
  y = 0

def update():
  global x, y
  if verifie_entree(keyboard, "LEFT"):
    x = x - 1

def draw():
  global x, y
  screen.fillRect(0, 0, 400, 400, "#468")
  screen.drawSprite("sprite", x, y, 20)
```

## Contrôler le personnage

:navigate projects.code

### Contrôler le personnage

Cliquez dans la fenêtre d'exécution du programme, puis enfoncez la touche &laquo;flèche gauche&raquo; de votre clavier d'ordinateur. Le personnage se déplace vers la gauche !

**Explications**: La ligne que nous avons ajoutée spécifie que si la touche gauche (`"LEFT"`) du clavier (`keyboard`) est enfoncée, alors la valeur de ```x``` doit être diminuée de 1 (```x = x - 1```).

Sachant que &laquo;droite&raquo; se dit `"RIGHT"`, &laquo;haut&raquo; se dit `"UP"` et &laquo;bas&raquo; se dit `"DOWN"`, ajoutez les instructions manquantes 
à votre code pour déplacer votre personnage dans toutes les directions.

(Solution à l'étape suivante)

## Contrôler le personnage

:navigate projects.code

### Contrôler le personnage

Voici le code complet de la fonction ```update``` pour déplacer le personnage dans toutes les directions avec les touches du clavier :

```python
def update():
  global x, y
  if verifie_entree(keyboard, "LEFT"):
    x = x - 1
  if verifie_entree(keyboard, "RIGHT"):
    x = x + 1
  if verifie_entree(keyboard, "UP"):
    y = y + 1
  if verifie_entree(keyboard, "DOWN"):
    y = y - 1
```

## Contrôler le personnage

:navigate projects.code

### Contrôler le personnage

Votre code complet ressemble donc à ceci:

```python
def verifie_entree(peripherique, valeur):
  """
  Renvoie True si peripherique a une valeur non nulle
  False si sa valeur est nulle et None si il n'est pas défini
  """
  if hasattr(peripherique, valeur):  # Si il y a une valeur
    return peripherique[valeur] != 0  # True ou False
  else:  # Sinon, il n'y a pas de valeur
    return None

def init():
  global x, y
  x = 0
  y = 0

def update():
  global x, y
  if verifie_entree(keyboard, "LEFT"):
    x = x - 1
  if verifie_entree(keyboard, "RIGHT"):
    x = x + 1
  if verifie_entree(keyboard, "UP"):
    y = y + 1
  if verifie_entree(keyboard, "DOWN"):
    y = y - 1

def draw():
  global x, y
  screen.fillRect(0, 0, 400, 400, "#468")
  screen.drawSprite("sprite", x, y, 20)
```

## Fin

:navigate tutorials

:overlay

Ce tutoriel est terminé. Pour en apprendre plus sur la programmation sur *microStudio*, vous pouvez maintenant essayer le parcours de tutoriels de programmation.
