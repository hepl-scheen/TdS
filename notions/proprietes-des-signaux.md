# Propriétés des signaux

## Valeur moyenne d'un signal

La valeur moyenne d’un signal $x(t)$ périodique est obtenue selon 

:::{grid-item-card} Signal à temps continu
$$\overline{x} = \frac{1}{T} \int_{0}^{T} x(t) \, dt$$
:::

On appelle parfois la valeur moyenne la valeur _DC_ ou l'_offset_. 

## Valeur efficace

La valeur efficace (ou RMS en anglais, Root Mean Square) est une mesure de l’amplitude d’un signal variable. 

La définition est : 

:::{grid-item-card} Signal à temps continu
$$x_{rms} = \sqrt{\frac{1}{T} \int_{0}^{T} x^2(t) \, dt }$$
:::

C’est la racine carrée de la valeur moyenne du signal au carré. 

```{admonition} Remarque
En électricité, la valeur efficace d’un courant ou d'une tension variables au cours du temps correspond à la valeur d'un courant continu ou d'une tension continue qui produirait un échauffement identique dans une résistance. 

Pratique pour calculer la puissance fournie par un signal périodique. Pensez-y !

```{figure} rms.png
---
width: 100%
name: F:proprietes:rms
---

Quand on parle de la tension 220 V à la prise de courant, en réalité, la tension oscille entre -325 V et 325 V. 220 V correspond à sa valeur efficace.

```


```{figure} rms_signaux_utiles.png
---
width: 100%
name: F:proprietes:rms_signaux_utiles
---
Valeurs efficaces de signaux utiles.
```

## Transformation de la variable indépendante

Le signal $x(t)$ dépend de la variable $t$, appelée _variable indépendante_.

* Un changement de signe sur $t$ revient à un retournement de l'axe temporel, donc à une symétrie par rapport à l'origine.
* Un changement d'échelle consiste à multiplier $t$ par une variable $a \in \mathbb{R}^{+*}$.
* Une translation (ou décalage) consiste à ajouter une variable $d\in\mathbb{R}$ à la variable indépendante.

L'animation ci-dessous permet de visualiser ces transformations sur $t$, dans l'exemple d'un signal $x$ tel que

$$
  x(t) =
  \begin{cases}
    t &\text{si}\quad 0 \leq t < 1 \\
    1 &\text{si}\quad 1 \leq t < 2 \\
    0 &\text{sinon}
  \end{cases}
$$


https://vincmazet.github.io/spetsi/dilatation.html


## Périodicité

Un signal $x$ est périodique s'il est constitué d'une infinité de morceaux tous identiques, appelés _périodes_.
Par extension, la période désigne aussi la longueur de cette période.
Un signal non périodique est dit _apériodique_.
Ainsi :
* un signal à temps continu de période $T$ est tel que : $\quad \forall t \quad x(t+T) = x(t)$,
* un signal à temps discret de période $N$ est tel que : $\quad \forall n \quad x[n+N] = x[n]$.

La _fréquence_ d'un signal est l'inverse de sa période.


## Causalité

Un signal $x$ est _causal_ si et seulement s'il est nul pour les temps négatifs :
* pour un signal à temps continu : $\quad \forall t<0 \quad x(t) = 0$,
* pour un signal à temps discret : $\quad \forall n<0 \quad x[n] = 0$.

```{figure} causal.jpg
---
width: 30%
name: F:proprietes:causal
---
...
```

Un signal $x$ est _anti-causal_ si et seulement s'il est nul pour les temps positif :
* pour un signal à temps continu : $\quad \forall t>0 \quad x(t) = 0$,
* pour un signal à temps discret : $\quad \forall n>0 \quad x[n] = 0$.

```{figure} anti-causal.jpg
---
width: 30%
name: F:proprietes:anti-causal
---
...
```

Un signal $x$ est _non-causal_ si et seulement s'il est ni causal, ni anti-causal  :

```{figure} non-causal.jpg
---
width: 30%
name: F:proprietes:non-causal
---
...
```