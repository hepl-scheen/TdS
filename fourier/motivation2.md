(C:fourier)=
# Introduction

Joseph Fourier (1768–1830) était professeur à l'École Polytechnique, scientifique pendant la campagne de Napoléon en Égypte,
et préfet de l'Isère.
Il a aussi été membre de l'Académie des sciences et de l'Académie française.

En travaillant sur le phénomène de propagation de la chaleur,
il s'aperçut qu'il était utile de représenter la distribution de température dans les matériaux comme une somme de sinusoïdes :
c'est ce qu'on appelle maintenant une décomposition en série de Fourier.
La série de Fourier, et les autres transformations qui en découlent,
jouent un rôle capital en traitement du signal
car elles permettent de mettre en évidence les fréquences contenues dans un signal.

```{figure} intro_temp.jpg
---
name: F:fourier:intro_temp
---
Enregistrement audio d'une personne parlant dans un micro et un zoom.
```

On remarque qu'avec cette représentation temporelle, nous obtenons peu d'informations quant à la constitution du signal.

```{figure} temp_freq.jpg
---
name: F:fourier:temp_freq
---
Changement de domaine
```

Nous allons voir dans ce chapitre un outil puissant pour représenter un signal, non plus part rapport au temps, mais par rapport au fréquences. Cette représentation va nous informer sur le _spectre_ du signal, et donc sur les _composantes fréquentielles_ le composant.

Par exemple, la figure ci-dessous est le spectre fréquentiel de l'enregistrement audio ci-dessus. Ce spectre est plus riche dans les basses fréquences. Nous pouvons donc prévoir que la personne qui parlait dans le micro a une voix grave.


```{figure} spectre_voix.jpg
---
name: F:fourier:spectre_voix
---
Spectre fréquentiel de l'enregistrement audio.
```

Nous verrons dans les prochains chapitres que :
* Les sinusoïdes sont les signaux les plus faciles à utiliser lors de l’analyse de circuits ou de systèmes. 
* Les sinusoïdes permettent de rapidement calculer la réponse d’un système en régime permanent, sans calculer la réponse transitoire. 
* Si l’entrée à un système est une sinusoïde, la sortie sera aussi une sinusoïde, de même fréquence (l’amplitude et la phase peuvent changer). Les sinusoïdes sont les seuls signaux périodiques à posséder cette propriété. Pour les autres sources périodiques (ex : triangulaire), il faut trouver une autre méthode d’analyse. 
La série de Fourier permet de prendre n’importe quel signal périodique, et le décomposer en une somme de sinusoïdes. 




Lié au série de Fourier, nous verrons ensuite les transformées de Fourier qui sont la généralisation des séries.

Il existe quatre transformations de Fourier, chacune adaptée au type de signal considéré :
- la « série de Fourier » (SF) s'applique aux signaux à temps continu et périodiques,
- la « transformée de Fourier » (TF) s'applique aux signaux à temps continu et apériodiques,
- la « série de Fourier discrète » (SFD) s'applique aux signaux à temps discret et périodiques,
- et la « transformée de Fourier à temps discret » (TFTD) s'applique aux signaux à temps discret et apériodiques.

# Exemple

## La _couleur du son_

L'enregistrement ci-dessous est la même note (_Do_) jouer à la guitare, à la flûte et chanté. Nous pouvons entendre que la note ne sonne pas de la même manière. En musique, on dit que la note n'a pas la même _couleur_.

Regardons l'enveloppe spectrale (la représentation spectrale ou représentation en fréquence) de ces trois "Do".

```{figure} Do.jpg
---
name: F:fourier:Do
---
Représentation spectrale des 3 "Do".
```

On remarque que la première raie (à gauche du spectre) se situe à la même fréquence. Cette raie définit la note, ici le "Do". On appelle cette première note la _fondamentale_ (ou "l'harmonique de rang 1" ou encore "1ere harmonique").

Les autres raies, espacées de manière identique, forment les secondes, troisièmes ... harmoniques. Ces harmoniques donnent le couleur au son (ou le timbre).

## Radio FM

La figure ci-dessous représente la bande spectrale de la radio FM (88 MHz à 108 MHz). Ce spectre a été réalisé à l'aide d'un analyseur de spectre. Chaque radio émet son émission dans un _canal_ qui lui a été alloué. Ce canal est la bande de fréquence qui lui est réservé. Par exemple, la radio "N-JOY" émet autour de 101.8 MHz.

```{figure} FM.jpg
---
name: F:fourier:FM
---
Spectre de la bande FM. Chaque pic représente une radio disponible.
```

## Détection d’anomalie par analyse vibrationnelle

La détection d'anomalies par analyse vibratoire est une technique qui permet de détecter des défauts ou des anomalies dans un système mécanique en analysant ses vibrations.

Les vibrations sont des mouvements oscillatoires d'un système mécanique. Elles peuvent être causées par une variété de facteurs, tels que la rotation d'un arbre, le mouvement d'un piston ou la friction entre des pièces mobiles.

La détection d'anomalies par analyse vibratoire consiste à analyser les vibrations d'un système pour détecter des changements ou des irrégularités qui pourraient indiquer un défaut ou une anomalie.

```{figure} vibration.jpg
---
name: F:fourier:vibration
---
Chaque partie d'un système mécanique induit une vibration à une fréquence qui lui est propre. La variation de ces vibrations ou l'apparition de nouvelles fréquences permet de prédire une anomalie ou une usure dans le système.
```

