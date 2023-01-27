# Tutoriel: Texte

:project Tutoriel: Dessiner {"language" : "python"}

## Texte

:position 55,60,45,40

### Dessiner du texte

Vous pouvez dessiner du texte en appelant ```screen.drawText```. Comme cela
nécessite le chargement de polices de caractères en arrière-plan, pour de meilleurs
résultats nous allons implémenter nos exemples dans le corps de la fonction ```draw```:

```
def draw():
  screen.clear()
  screen.drawText("microStudio", 0, 0, 20, "rgb(255,255,255)")
```

Le premier argument est une chaîne de caractères, contenant le texte que nous voulons dessiner.
Les deux paramètres suivants sont les coordonnées `(x, y)`` du point où nous souhaitons afficher le texte.
Le texte sera centré sur ce point. Le quatrième argument est la taille du texte (hauteur des caractères).
Le cinquième argument, optionnel, est la couleur (lorsqu'omise, la dernière couleur active sera réutilisée)

## Police de caractères

:position 55,60,45,40

### Police de caractères

Vous pouvez utiliser différentes polices de caractères en appelant ```screen.setFont```:

```
def draw():
  screen.clear()
  screen.setFont("Awesome")
  screen.drawText("microStudio c'est super !", 0, 0, 20, "rgb(255,255,255)")
```

## Polices de caractères disponibles

:position 55,60,45,40

### Polices de caractères disponibles

microStudio inclut un ensemble de polices de style pixellisé. Pour obtenir la liste complète :

* lorsque votre programme est déjà en train de tourner, testez la variable ```global.fonts``` dans la console. Elle vous donnera la liste complète des polices disponibles.
* essayez cette démo qui présente toutes les polices : https://studio.numpf.xyz/tchene/fonts/

## Liste des polices

:position 30,20,45,70

:navigate tutorials

:overlay

### Liste des polices

Ce tutoriel est terminé ! Nous avons reproduit la liste des polices disponibles aussi ci-dessous.
Vous pouvez entamer le tutoriel suivant qui vous apprendra à dessiner des sprites et des maps.

#### Liste des polices disponibles

AESystematic

Alkhemikal

AlphaBeta

Arpegius

Awesome

BitCell

Blocktopia

Comicoro

Commodore64

DigitalDisco

Edunline

EnchantedSword

EnterCommand

Euxoi

FixedBold

GenericMobileSystem

GrapeSoda

JupiterCrash

Kapel

KiwiSoda

Litebulb8bit

LycheeSoda

MisterPixel

ModernDos

NokiaCellPhone

PearSoda

PixAntiqua

PixChicago

PixelArial

PixelOperator

Pixellari

Pixolde

PlanetaryContact

PressStart2P

RainyHearts

RetroGaming

Revolute

Romulus

Scriptorium

Squarewave

Thixel

Unbalanced

UpheavalPro

VeniceClassic

ZXSpectrum

Zepto
