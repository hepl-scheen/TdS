# Énergie et puissance

Par analogie avec l'énergie et la puissance d'un système physique (moteur électronique, mobile en déplacement...),
on définit l'énergie et la puissance d'un signal.
Dans le cas —&nbsp;très courant&nbsp;— où les amplitudes du signal sont sans unité, alors l'énergie et la puissance sont également sans unité.

## Énergie d'un signal

L'énergie d'un signal $x$ est définie par les formules ci-dessous.

::::{grid} 1 1 1 2
:gutter: 3

:::{grid-item-card} Signal à temps continu
$$E = \int_{-\infty}^{+\infty} |x(t)|^2 \, dt$$
:::

:::{grid-item-card} Signal à temps discret
$$E = \sum_{n=-\infty}^{+\infty} |x[n]|^2$$
:::

::::


Ces formules sont équivalentes, heureusement ! L'énergie est en fait l'aire sous la courbe du carré du signal, l'aire sous la courbe étant une intégrale ou une somme. Remarquez également que la notation $\mid\cdot\mid$ correspond au module (le signal pouvant être complexe).

```{admonition} Remarque
Il est souvent plus simple de déterminer l'énergie d'un signal en imaginant l'aire sous la courbe du carré du signal plutôt que de calculer l'intégrale.
```

```{admonition} Remarque
Un signal physiquement réalisable est à énergie finie. Mais en traitement du signal, nous utiliserons souvent des signaux à énergie infinie (comme une sinusoïde non bornée) pour illustrer les principes.
```

## Puissance d'un signal

La puissance d'un signal $x$ périodique correspond à l'énergie sur une période divisée par la durée de cette période.

::::{grid} 1 1 1 2
:gutter: 3

:::{grid-item-card} Signal à temps continu de période $T$
$$P = \frac{1}{T} \int_T |x(t)|^2 \, dt\,$$
:::

:::{grid-item-card} Signal à temps discret de période $N$
$$P = \frac{1}{N}\sum_{n=0}^{N-1} |x[n]|^2$$
:::

::::

où la période $N$ est le plus petit petit nombre d'échantillons qui se répètent (N est toujours un entier).

Pour déterminer la puissance d'un signal apériodique, on considère qu'il s'agit d'un signal périodique de période infinie.
En reprenant les formules de la puissance d'un signal périodique, et en faisant tendre cette période vers l'infini,
on obtient les formules de la puissance d'un signal apériodique.

::::{grid} 1 1 1 2
:gutter: 3

:::{grid-item-card} Signal apériodique à temps continu
$$P = \lim_{T\rightarrow+\infty} \frac{1}{T} \int_{T} |x(t)|^2 \, dt$$
:::

:::{grid-item-card} Signal apériodique à temps discret
$$P = \lim_{N\rightarrow+\infty} \frac{1}{N} \sum_{n=0}^{N-1} |x[n]|^2$$
:::

::::


## Signaux à énergie finie vs. Signaux à puissance finie

Ces deux contraintes sont mutuellement exclusives. 

```{admonition} Signaux à énergie finie >< Signaux à puissance finie
En particulier, un signal à énergie finie a une puissance moyenne nulle alors qu'un signal à puissance finie possède une énergie infinie. 
```

Les signaux déterministes et apériodiques sont à énergie finie alors que les signaux périodiques ou aléatoires ont généralement une puissance finie non nulle (Rappel : nous parlons des signaux temporellement non-tronqués). 

Signalons qu'il s'agit de modélisation et qu'en conséquence, certains signaux n'ont pas de réelle signification physique pour des temps infinis, ce qui n'empêche pas qu'ils puissent être d'une grande aide! 

```{figure} energ_puiss.jpg
---
name: F:fourier:energ_puiss
---
Classification des signaux selon leur énergie/puissance
```