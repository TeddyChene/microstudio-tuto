# Tutoriel: Transformations

:project Tutoriel: Dessiner {"language" : "python"}

## Transparence

:position 55,60,45,40

### Transparence

Vous pouvez définir un niveau de transparence global pour toutes vos opérations
de dessin en utilisant la fonction ```screen.setAlpha```. En utilisant cette fonction,
vous définissez en fait l'opacité à prendre en compte pour vos prochains appels à des
fonctions de dessin. L'opacité peut varier de `0` à `1`, `0` étant la transparence totale et `1`
l'opacité totale. Vous pouvez donc dessiner des formes semi-transparentes comme suit :

```
screen.setAlpha(0.5)
screen.fillRect(0, 0, 50, 50, "rgb(255,255,255)")
screen.fillRect(20, 20, 50, 50, "rgb(255, 0, 0)")
```

## Transparence

:position 55,60,45,40

### Transparence

Après avoir défini un niveau de transparence à travers ```screen.setAlpha```, pensez
à rétablir l'opacité à sa valeur par défaut, sinon la transparence va continuer à
affecter tous vos prochains appels à des fonctions de dessin :

```
screen.setAlpha(0.5)
screen.fillRect(0, 0, 50, 50, "rgb(255, 255, 255)")
screen.setAlpha(1)
screen.fillRect(20, 20, 50, 50, "rgb(255, 0, 0)")
```

## Rotation

:position 55,60,45,40

### Rotation

Vous pouvez définir un angle de rotation avant de dessiner des formes, des sprites, des maps, en utilisant
```screen.setDrawRotation(angle)```. L'angle est exprimé en degrés. Le point d'origine de la rotation
pour chaque appel de dessin que vous ferez sera le centre de votre rectangle, sprite ou map.

```
screen.setDrawRotation(45)
screen.fillRect(0, 0, 100, 100, "rgb(255,255,255)")
```

N'oubliez pas de remettre la rotation à zéro après cela :

```
screen.setDrawRotation(0)
```

## Mise à l'échelle

:position 55,60,45,40

### Facteur d'échelle

Vous pouvez définir un facteur d'échelle, particulièrement avant de dessiner des sprites ou des maps, en utilisant
```screen.setDrawScale(facteur_x,facteur_y)```. Les deux arguments sont le facteur d'échelle pour l'axe x et le facteur
d'échelle pour l'axe y. Cette fonction est notamment utile pour &laquo;retourner&raquo; un sprite et le faire regarder vers la gauche
au lieu de vers la droite. Exemple :

```
screen.setDrawScale(-1, 1)  # L'axe x va être inversé
screen.drawSprite("sprite", 0, 0, 100)
screen.setDrawScale(1, 1)  # Remise au facteur d'échelle normal 1,1
```

## Série terminée

:overlay

:position 30,30,40,60

:navigate tutorials

### Vous avez terminé cette série !

Il est temps pour vous de jouer avec toutes les fonctions de dessin. Donnez-vous l'objectif d'un paysage que
vous souhaiteriez dessiner avec des formes, des sprites ou les deux. Essayer de le développer avec du code. Revenez
sur ces tutoriels quand vous avez besoin de vérifier une fonctionnalité. Utilisez également la documentation qui est
toujours là pour vous aider !
