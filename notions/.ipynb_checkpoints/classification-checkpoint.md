# Classification des signaux

## Signaux analogiques et signaux numériques

La plupart des signaux physiques que l'on mesure sont _analogiques_,
c'est-à-dire qu'ils dépendent d'une variable qui prend des valeurs
_continues_
(par exemple, le temps) et qu'eux-mêmes peuvent prendre des valeurs _continues_.
On peut citer comme exemple la tension électrique dans un circuit, un son,
une mesure de température, etc.

À l'inverse, les signaux traités par un ordinateur sont un ensemble de valeurs qui dépendent donc
d'une variable _discrète_,
et de plus les amplitudes du signal sont également discrètes.
Ces signaux sont _numériques_.
On peut citer comme exemple une photographie numérique qui est constituée de pixels
dont les intensités ne peuvent prendre que 256<sup>3</sup> = 16&nbsp;777&nbsp;216 valeurs.

Un signal numérique est à la fois _échantillonné_
(c'est-à-dire qu'il dépend d'une variable discrète) et _quantifié_ (ses amplitudes sont discrètes).
Ainsi, l'_échantillonnage_ consiste à transformer un signal non échantillonné en un signal échantillonné.
De même, la _quantification_ consiste à transformer un signal à valeurs continues
en un signal à valeurs discrètes.
La combinaison de ces deux opérations est appelée _numérisation_.

```{admonition} Remarque
Sur un ordinateur, on ne peut donc traiter que des signaux numériques, et de durée limité,
car une mémoire informatique ne peut stocker qu'un nombre fini de valeurs dont la précision est limitée.
```

Un signal peut également être à valeurs complexes, quelle que soit sa classification.
La représentation complexe est une représentation mathématique bien pratique
car même si les signaux physiques peuvent être exprimés avec des valeurs réelles,
les nombres complexes permettent parfois de manipuler plus simplement les signaux
{ref}`[Prandoni 2008, p. 20] <P:references>`.
C'est le cas par exemple des champs électromagnétiques.

Dans la suite du cours, nous adopterons les conventions de notation suivantes :
* les signaux à temps continu sont notés avec des parenthèses
  et le plus souvent la variable $t\in\mathbb{R}$, par exemple : $x(t)$.
* les signaux à temps discret (échantillonnés) sont notés avec des crochets
  et le plus souvent la variable $n\in\mathbb{Z}$, par exemple : $x[n]$.

## Classification des signaux 

```{figure} classification.png
---
width: 80%
name: F:classification:classification
---
...
```

Un signal _déterministe_ est un signal dont on peut connaître à coup sûr la valeur à chaque instant. Il s'oppose en ce sens aux signaux _aléatoires_ dont on connaît seulement la probabilité de réalisation pour chaque valeur. 

### Signaux périodiques

Un signal est dit périodique si les variations de son amplitude se reproduisent régulièrement au bout d'une période T constante comme sur la figure suivante : 

```{figure} Signal_périodique.png
---
width: 30%
name: F:classification:Signal_périodique
---
...
```

On dira que son motif se répète régulièrement.

Mathématiquement, cela signifie que le signal est représenté par une fonction périodique de période $T$. C'est-à-dire, pour tout $t$ : 

$$f(t + T) = f(t)$$

La fréquence d'un signal périodique est le nombre de périodes par seconde. Elle s'exprime en hertz (Hz). La fréquence en hertz est donc égale à l'inverse de la période exprimée en secondes : 

$$f = 1/T$$

### Signaux quasi-périodiques

Les signaux quasi-périodiques sont produits par la somme ou le produit de signaux sinusoïdaux de périodes dont le rapport n’est pas rationnel.

```{figure} pseudo-aléatoire.png
---
width: 80%
name: F:classification:pseudo-aléatoire
---
...
```

### Signaux pseudo-aléatoire

Ce sont des signaux périodiques dont le comportement rappelle celui des signaux aléatoires.

Il n’est pas possible, à l’aide d’un ordinateur, de générer une suite aléatoire. Il est cependant possible de générer des suites pseudo-aléatoires, qui présentent en pratique, du point de vue de l’utilisateur, les caractéristiques d’un signal aléatoire.

Le terme pseudo-aléatoire est utilisé en mathématiques et en informatique pour désigner une suite de nombres qui s'approche d'un aléa statistiquement parfait. Les procédés algorithmiques utilisés pour la créer et les sources employées font que la suite ne peut être complètement considérée comme aléatoire. 



### Signaux non-périodique

Un signal pour lequel il n’existe aucune valeur de $T$ satisfaisant la condition de périodicité est appelée fonction _apériodique_ ou encore fonction _non-périodique_.

C'est le cas de la fonction porte par exemple.

## D'autres classifications

Il existe d'autres critères de classification des signaux. Voici une liste non-exhaustive dont nous verrons plus loin les significations :

* le caractère spectral : : signaux basse ou haute fréquence, large bande, bande étroite ; signaux blancs ou en 1/f ...

* la dimension des signaux : 1D (ex : le sons), 2D (ex: les images ou micro stéréophonique), 3D (ex : image volumique d'IRM, séquence d’images 2D (la troisième dimension est le temps)), 4D (ex : séquence d’images 3D), XD (ex : réseau de capteurs, réseaux d'antennes).






