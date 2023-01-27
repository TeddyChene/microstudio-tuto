# Tutoriel: Créer un mur

:project Tutoriel: Créer un jeu {"language": "python"}

## Mur

:position 55,60,45,40

:highlight #menuitem-sprites

:overlay

### Mur

Notre héros va courir sur un mur, ou une plateforme ou une route... appelons cela un mur. Nous
allons créer ce mur en créant un morceau de mur sous la forme d'un sprite et en remplissant une zone
de l'écran en dupliquant ce morceau de mur. Créons un nouveau sprite et appelons-le &laquo;wall&raquo; (mur en anglais).

Ce serait bien si notre sprite a bonne allure une fois dupliqué plusieurs fois. Pour vous aider en cela,
nous vous recommandons d'activer l'option &laquo;Tile&raquo; en bas à droite de l'éditeur de sprite.
Il est temps de dessiner maintenant !

## Affichage du mur

:position 55,60,45,40

:highlight #menuitem-code

### Affichage du mur

Retournons à notre code. Assurons-nous que le programme est en cours d'exécution (cliquez sur le bouton d'exécution <i class="fas fa-play"></i> une nouvelle
fois si nécessaire). Nous allons ajouter les lignes suivantes dans le corps de la fonction ```draw``` :

```
  for i in range(-6, 7):
    screen.drawSprite("wall", i*40, -80, 40)
```

Le code ci-dessus est une boucle ```for```. Elle établit que la fonction ```screen.drawSprite``` sera appelée
plusieurs fois, à chaque fois avec une valeur différente pour la variable ```i``` qui commencera à -6, puis -5, -4 ...
, 3, 4, 5, 6. La coordonnée x de dessin du sprite prendra donc les valeurs -240, puis -200, -160 ... jusqu'à 240. Vous
pouvez constater le résultat dans la fenêtre d'exécution.

## Affichage du mur

:position 55,60,45,40

### Affichage du mur

Le code complet est maintenant le suivant. Notre prochaine mission est d'animer le mur pour créer l'illusion que le héros
est en train de courir dessus.

```
def init():
  pass

def update():
  pass

def draw():
  screen.fillRect(0, 0, screen.width, screen.height, "rgb(57,0,57)")
  for i in range(-6, 7):
    screen.drawSprite("wall", i*40, -80, 40)
  screen.drawSprite("hero", -80, -50, 20)
```

## Animation du mur

:position 55,60,45,40

### Animation du mur

Nous allons introduire une variable globale ```position```. Nous l'utiliserons pour déplacer nos morceaux de mur vers la gauche.
Réécrivons la ligne qui dessine nos morceaux de mur comme suit :

```
    screen.drawSprite("wall", i*40-position, -80, 40)
```

Le mur ne bouge pas encore, parce que nous ne changeons pas la valeur de ```position```.

Il faut définir la variable `position` comme variable globale dans les trois fonctions `init`, `update` et `draw`.
Ajoutez cette ligne comme première instruction de chacune des trois fonctions : 

```python
global position
```

## Animation du mur

:position 55,60,45,40

### Animation du mur

Initialisons la variable `position` à `0` dans la fonction `init` et modifions maintenant la
fonction ```update``` ainsi:

```
def init():
  global position
  position = 0

def update():
  global position
  position = position + 2
```

En faisant cela, nous assurons que, 60 fois par seconde (la fréquence d'appel de la fonction `update`), la valeur de
```position``` va être augmentée de `2`. Notre mur s'est vite déplacé vers la gauche et a disparu complètement. Oups !

## Animation du mur

:position 55,60,45,40

### Animation du mur

Nos morceaux de mur sont espacés de 40 unités. Au lieu des les déplacer vers la gauche selon la valeur de *position*,
nous allons les déplacer de ```position % 40```. ```position % 40``` est le reste de la division de *position* par 40.
Quand nous augmentons position continuellement de 2 en 2, ```position % 40``` prendra les valeurs 0,2,4,6,..., 38 puis
retour à 0,2,4,6 ... 38 et ainsi de suite. Exactement ce dont nous avons besoin. Pas convaincu ? Essayons :

```
  for i in range(-6, 7):
    screen.drawSprite("wall", i*40-position%40, -80, 40)
```

Alors ? Le mur se déplace bien toujours vers la gauche, sans disparaître. L'illusion est parfaite !

## Code

:position 55,30,45,70

### Code

Voici où nous en sommes pour référence :

```
def init():
  global position
  position = 0

def update():
  global position
  position = position + 2

def draw():
  global position
  screen.fillRect(0, 0, screen.width, screen.height, "rgb(57,0,57)")
  for i in range(-6, 7):
    screen.drawSprite("wall", i*40-position%40, -80, 40)
  screen.drawSprite("hero", -80, -50, 20)
```

## La suite

:position 30,30,40,40

:navigate tutorials

:overlay

### La suite
Continuons avec le tutoriel suivant où nous nous ferons sauter notre héros.
