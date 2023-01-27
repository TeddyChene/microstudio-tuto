# Tutoriel: Sprites

:project Tutoriel: Dessiner {"language" : "python"}

## Dessiner des sprites

:position 55,60,45,40

### Dessiner des sprites

Lorsque vous dessinez des sprites dans l'onglet &laquo;Sprites <i class="fa fa-image"></i>&raquo;, vous pouvez leur donner un nom.
Ce nom sera utilisé pour les désigner lorsque vous appelerez ```screen.drawSprite```. Les sprites
sont chargés en arrière-plan au lancement de votre programme, aussi allons nous les dessiner
dans le corps de la fonction ```draw```.

```
def draw():
  screen.drawSprite("icon", 0, 0, 40, 40)
```

Le premier argument est le nom de votre sprite. Chaque projet a un sprite nommé
`"icon"`, qui sert d'icône d'application. Vous pouvez créer d'autres sprites dans
l'onglet &laquo;Sprites <i class="fa fa-image"></i>&raquo; et essayer de les dessiner à l'écran de la même façon.

Le second et le troisième argument sont les coordonnées `(x, y)` où dessiner le sprite.
Le sprite sera centré sur ces coordoonnées. Les deux paramètres suivants donnent
la largeur et la hauteur que prendra votre sprite à l'écran (la hauteur peut être omise).

## Dessiner des sprites animés

:position 55,60,45,40

### Dessiner des sprites animés

Les sprites animés peuvent être créés dans l'onglet Sprites. Lorsque vous éditez un sprite,
ouvrez l'onglet &laquo;Animation&raquo; qui se trouve en bas de la fenêtre. Vous pouvez ajouter des étapes d'animation,
voir un aperçu de l'animation, régler sa vitesse.

Une fois que vous avez créé un sprite animé, vous pouvez le dessiner comme un sprite normal,
depuis le corps de la fonction ```draw``` :

```
def draw():
  screen.clear()
  screen.drawSprite("my_animated_sprite", 0, 0, 100) 
```

## Définir l'étape d'animation

:position 55,60,45,40

### Définir l'étape d'animation

Votre animation va être jouée en boucle continuellement, mais à certain moments vous voudrez peut-être
la réinitialiser à sa première étape. Vous pouvez le faire comme suit :

```
def draw()
  screen.clear()
  sprites["my_animated_sprite"].setFrame(0)
  screen.drawSprite("my_animated_sprite", 0, 0, 100)
```

Cet exemple remet l'animation du sprite `"my_animated_sprite"` à l'étape `0` (qui est la première étape).

## Dessiner une étape spécifique

:position 55,60,45,40

### Dessiner une étape spécifique

Vous pouvez choisir de dessiner une étape spécifique de votre sprite animé. Pour cela, vous pouvez ajouter `.` suivi de
l'indice de l'étape choisie, au nom de votre sprite. Les indices d'étape vont de `0` à `(nombre d'étapes)-1`.

```
def draw()
  screen.clear()
  screen.drawSprite("my_animated_sprite.0", 0, 0, 100)
```

Le code ci-dessus dessine la première étape d'animation du sprite `"my_animated_sprite"`.

## Dessiner des maps

:position 55,60,45,40

### Dessiner des maps

Les maps peuvent être créées dans l'onglet &laquo;Maps <i class="fa fa-map"></i>&raquo;. Une &laquo;map&raquo; (carte) est une grille dont les cases peuvent être remplies avec
des sprites. Cela permet de créer des images d'arrière-plan ou des niveaux en assemblant des sprites ensemble.
Le code suivant va dessiner la map `"map1"`, centrée en `(0, 0)`, avec une largeur de `320` et une hauteur de `200` :

```
def draw()
  screen.clear()
  screen.drawMap("map1",0,0,320,200)
```

# Et ensuite ?

:overlay

:position 30,30,40,40

:navigate tutorials

### Et ensuite ?

Il est temps de continuer vers le prochain tutoriel pour apprendre à utiliser les dégradés de couleurs !
