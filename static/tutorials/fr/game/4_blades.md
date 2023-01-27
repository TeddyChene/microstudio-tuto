# Tutoriel: Créer des lames

:project Tutoriel: Créer un jeu {"language": "python"}

## Lames

:position 30,30,50,50

:highlight #menuitem-sprites

### Lames

Nous allons maintenant ajouter quelques obstacles que notre héros doit éviter en sautant.
Nous les appellerons les lames (blades en anglais) mais vous pouvez imaginer n'importe quoi
d'autre pourvu que ça ait l'air vraiment dangereux !

Ouvrez l'onglet &laquo;Sprites <i class="fa fa-image"></i>&raquo;, cliquez sur &laquo;Ajouter un sprite <i class="fa fa-plus-circle"></i>&raquo; 
pour créer votre nouveau sprite. Assurez-vous de le renommer &laquo;blade&raquo; pour 
qu'il fonctionne correctement avec le reste de ce tutoriel. Dessinez
votre méchante lame !

## Initialisation des lames

:position 55,60,45,40

### Initialisation des lames

Maintenant que votre sprite &laquo;blade&raquo; est prêt, nous allons créer un ensemble de trois lames avec notre
code, nous allons les afficher et les faire réapparaître loin devant notre héros une fois qu'elles
disparaissent derrière lui.

Nous allons initialiser deux variables globales `blades` et `passed` dans les 
fonctions `init`, `update` et `draw`. On obtient alors les variables globales
du projet ci-dessous : 

```
global position, hero_y, hero_vy, blades, passed
```

## Initialisation des lames

:position 55,60,45,40

### Initialisation des lames

Dans le corps de la fonction ```init```. La première liste, ```blades``` va
contenir la position de nos 3 lames. Le deuxième tableau, ```passed``` sera utilisé pour mémoriser le passage de
notre héros au-dessus d'une lame :

```
  blades = [200, 300, 400]
  passed = [0, 0, 0]
```

## Création du &laquo;comportement&raquo; des lames

:position 55,60,45,40

### Création du &laquo;comportement&raquo; des lames

Pendant que notre héros court sur le mur, les lames vont sembler se déplacer jusqu'à lui puis
disparaître derrière lui. Une fois une lame disparue, nous allons la réutiliser et la faire réapparaître
loin devant le héros, avec une position partiellement aléatoire. Nous utiliserons 
la fonction `random` de la bibliothèque `random` pour obtenir un nombre aléatoire entre 0 et 1.

On ajoute à la première ligne de notre projet l'import de la bibliothèque : 

```
from random import random
```

## Création du &laquo;comportement&raquo; des lames

:position 55,60,45,40

### Création du &laquo;comportement&raquo; des lames

Le code ci-dessous parcourt la liste de lames et fait exactement cela. 
Il doit être inséré dans le corps de la fonction ```update```.

```
  for i in range(len(blades)-1):
    if blades[i] < position - 120:
      blades[i] = position + 280 + random()*200
      passed[i] = 0
```

Lorsque nous faisons réapparaître une lame loin devant le héros, nous remettons aussi à zéro la valeur
dans la liste ```passed```, pour mémoriser que le joueur n'a pas encore franchi cette lame.

## Affichage des lames

:position 55,60,45,40

### Affichage des lames

Nous pouvons maintenant afficher les lames à l'écran. Pour faire cela, ajoutons le code ci-dessous dans le corps
de notre fonction ```draw```.
Ce code parcourt la liste des lames et dessine le sprite &laquo;blade&raquo; à leur position.

```
  for i in range(len(blades)-1):
    screen.drawSprite("blade", blades[i]-position-80, -50, 20)
```

La coordonnée `x` pour dessiner le sprite est calculée comme la différence entre la position de la lame et la variable globale
*position*. Ainsi, lorsque la position de la lame est égale à la position de notre héros, les deux seront dessinés à la même place,
ce qui semble logique.

## Test de collision avec les lames

:position 55,60,45,40

### Test de collision avec les lames

Nous allons maintenant déterminer si le héros entre en collision avec une lame, ou saute par dessus. Pour chaque lame, nous
allons calculer la différence entre la position de la lame et la position du héros. Si la valeur absolue de cette différence
est suffisamment petite, nous pouvons considérer que les deux se touchent. Maintenant, si la position verticale du héros est
suffisamment haute, le héros est en fait en train de sauter et ne touche pas vraiment la lame. 

Voici comment tout cela se traduit en code, à insérer dans la *boucle for* dans le corps de la fonction *update* :

```
    if abs(position-blades[i])<10 then
      if hero_y<10 then
        gameover = 1 // c'est perdu !
      elsif not passed[i] then
        passed[i] = 1
        score += 1
      end
    end
```

## Test de collision avec les lames

:position 55,60,45,40

### Test de collision avec les lames

Dans le code ci-dessus, nous assignons la valeur 1 à une variable ```gameover```  lorsque le héros touche une lame.
Nous allons utiliser cela un peu plus tard pour déterminer que la partie est perdue. Nous incrémentons aussi
une nouvelle variable ```score```, pour compter combien de lames ont été franchies par le joueur avec succès et utiliser
cela comme un score que nous afficherons.

Il faut donc déclarer les variables `score` et `gameover` comme globales dans les fonctions `init`, `update` et `draw`, 
puis les initialiser en leur affectant la valeur 0 dans la fonction `init`.

```
global score, gameover 
```

## Test de collision avec les lames

:position 55,60,45,40

### Test de collision avec les lames

Voici le code complet de la *boucle for* dans la fonction *update* :

```python
  for i in range(len(blades)-1):
    if blades[i] < position - 120:
      blades[i] = position + 280 + random()*200
      passed[i] = 0
    if abs(position-blades[i]) < 10:
      if hero_y < 10:
        gameover = 1  # c'est perdu !
      elif not passed[i]:
        passed[i] = 1
        score += 1
```

## Affichage du score

:position 55,60,45,40

### Affichage du score

Nous enregistrons donc maintenant un score, pourquoi pas l'afficher maintenant ? Ajoutons ceci
au corps de la fonction *draw* :

```
    screen.drawText(score, 120, 80, 20, "#FFF")
```


## Suite

:position 55,15,45,80

### Suite

Voici le code complet tel qu'il devrait être maintenant :

```python
from random import random

def init():
  global position, hero_y, hero_vy, blades, passed
  global score, gameover
  position = 0
  hero_y = 0
  hero_vy = 0
  blades = [200, 300, 400]
  passed = [0, 0, 0]
  score = 0
  gameover = 0

def update():
  global position, hero_y, hero_vy, blades, passed
  global score, gameover
  position = position + 2
  hero_y = max(0, hero_y+hero_vy)
  if touch.touching and hero_y == 0:
    hero_vy = 7
  hero_vy = hero_vy - 0.3
  
  for i in range(len(blades)-1):
    if blades[i] < position - 120:
      blades[i] = position + 280 + random()*200
      passed[i] = 0
    if abs(position-blades[i]) < 10:
      if hero_y < 10:
        gameover = 1  # c'est perdu !
      elif not passed[i]:
        passed[i] = 1
        score += 1

def draw():
  global position, hero_y, hero_vy, blades, passed
  global score, gameover
  screen.fillRect(0, 0, screen.width, screen.height, "rgb(57,0,57)")
  for i in range(-6, 7):
    screen.drawSprite("wall", i*40-position%40, -80, 40)
  for i in range(len(blades)-1):
    screen.drawSprite("blade", blades[i]-position-80, -50, 20)
  screen.drawSprite("hero", -80, -50+hero_y, 20)
  screen.drawText(score, 120, 80, 20, "#FFF")
```


## La suite

:position 30,30,40,40

:navigate tutorials

:overlay

### La suite
Notre jeu est presque terminé ! Dans le tutoriel suivant, nous nous occuperons du cas où la partie
est perdue et verrons comment réinitialiser une nouvelle partie. 

