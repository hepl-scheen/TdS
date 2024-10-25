(C:fourier)=
# Série de Fourier

Tout signal $x(t)$ à temps continu et périodique de période $T$ peut s'écrire comme une combinaison linéaire
de fonctions $\exp\left(j 2\pi k f_{0} t\right)$, qui sont elles-mêmes périodiques de période $T$ :

```{margin}
Cette formule est la série de Fourier inverse.
```

$$
x(t) = \sum_{k=-\infty}^{+\infty} X[k] e^{+j 2 \pi k f_{0} t}
$$

```{margin}
Vous remarquerez que le signal temporel $x$ est noté en minuscule,
alors que le signal fréquentiel $X$ est en majuscule.
```

où $k \in \mathbb{Z}$ est la « fréquence » et $X[k]$ sont des coefficients.
L'ensemble de ces coefficients, noté simplement $X$, est la série de Fourier de $x$ ; c'est aussi un signal.
On montre que les coefficients de la série de Fourier sont définis par :

```{margin}
Cette formule est la série de Fourier.
```

$$
X[k] = \frac{1}{T} \int_T x(t) e^{-j 2 \pi k f_{0} t } dt.
$$

Le terme $k$ est appelé la $k$<sup>e</sup> harmonique.
En particulier, le terme $X[1]$ est la première harmonique, que l'on appelle aussi la « composante fondamentale » ou simplement _fondamentale_.
Le terme $X[0]$ correspond à la moyenne du signal :

$$
X[0] = \frac{1}{T} \int_T x(t) dt.
$$



```{dropdown} Formulation alternative : Forme trigonométrique réelle

Parfois, la série de Fourier de signaux réels est définie comme l'ensemble des coefficients $a_k$ et $b_k$ tels que :

$$
                                  a_0 &= \frac{1}{T} \int_0^T x(t) dt \\
\forall k \in\mathbb{N}^*, \qquad a_k &= \frac{2}{T} \int_0^T x(t) \cos(2 \pi k f_{0} t) dt \\
\forall k \in\mathbb{N}^*, \qquad b_k &= \frac{2}{T} \int_0^T x(t) \sin(2 \pi k f_{0} t) dt
$$

La relation entre ces coefficients $a_k$ et $b_k$ avec l'expression précédente de la série de Fourier est :

$$
\text{si}\, k<0\,:\qquad X[k] &= \frac{a_{-k}+jb_{-k}}{2} \\
\text{si}\, k=0\,:\qquad X[0] &= a_0 \\
\text{si}\, k>0\,:\qquad X[k] &= \frac{a_k-jb_k}{2}
$$

et la formule de la série de Fourier inverse devient :

$$
x(t) = a_0 + \sum_{k=1}^{+\infty} \left( a_k \cos(2 \pi k f_{0} t) + b_k \sin(2 \pi k f_{0} t) \right).
$$

Dans le cadre de ce module, nous n'utiliserons pas les formules faisant intervenir $a_k$ et $b_k$
car elles obligent à effectuer deux fois plus de calculs qu'avec les formules précédentes utilisant $X[k]$.
En effet, la formulation avec l'exponentielle complexe regroupe les termes en cosinus et en sinus.
C'est donc plus simple en complexe ! 😜

La représentation du spectre devient :

![Représentation trigonométrique](rep_trig.jpg)

Ce qui n'est pas spécialement aisé à interpréter. Ce qui explique que nous n'utiliserons pas souvent cette forme.

```


```{dropdown} Formulation alternative : Forme polaire

Il existe une 3e formulation : la forme polaire. La forme polaire de la série de Fourier permet d’obtenir directement l’amplitude et la phase des harmoniques.  

$$
x(t) = a_0 + \sum_{k=1}^{+\infty} \left( \mid A_{n}\mid \cos(2 \pi k f_{0} t + \theta_{n}) \right).
$$

où

$$
\mid A_{n}\mid &= \sqrt{a^2_n + b^2_n} \\
\theta_n &= tan^{-1} \left( \frac{-b_n}{a_n} \right) \\
$$

![spectre des amplitudes](fp_ampl.png)

![spectre des phases](fp_phase.png)

```

```{admonition} Reconstruction
Une fonction périodique est complètement définie par ses coefficients de Fourier et sa période :
* Si on connaît $X[k]$ et $\omega_0$, on peut construire $x(𝑡)$ en travaillant avec la forme complexe.
* Si on connaît $𝑎_𝑣$, $𝑎_𝑛$, $𝑏_𝑛$ et $\omega_0$, on peut construire $x(𝑡)$ en travaillant avec la forme trigonométrique réelle.
* Si on connaît l’amplitude $𝐴_𝑛$ et la phase $\theta_𝑛$, on peut construire $x(𝑡)$ en travaillant avec la forme polaire.
```






## Série de Fourier discrète

De même que pour la série de Fourier, un signal à temps discret et périodique de période $N$
peut s'écrire comme la combinaison linéaire de fonctions $\exp\left(j\frac{2\pi k n}{N}\right)$,
qui sont également périodiques de période $N$ :

```{margin}
Cette formule est la série de Fourier discrète inverse.
```

$$
x[n] = \frac{1}{N} \sum_{k=0}^{N-1} X[k] e^{+j 2 \pi k n / N}
$$

et :

```{margin}
Cette formule est la série de Fourier discrète.
```

$$
X[k] = \sum_{n=0}^{N-1} x[n] e^{-j 2 \pi k n / N}.
$$

**Remarque** &ensp; Un signal $x[n]$ à durée limité (donc non défini en dehors de l'intervalle $\{0,\dots,N-1\}$)
peut être vu comme un signal périodique de période $N$.
Il possède donc une série de Fourier discrète qui s'appelle dans ce cas « transformée de Fourier discrète » (TFD).
Comme les signaux que l'on traite sur ordinateur sont toujours à durée limitée,
alors ce sera cette transformée de Fourier discrète qui sera calculée.
Il existe un algorithme très rapide pour la calculer : l'algorithme [FFT](https://fr.wikipedia.org/wiki/Transformation_de_Fourier_rapide)
(implémenté en Python par exemple dans la fonction `numpy.fft.fft`).

## Valeur RMS

La valeur RMS d’un signal peut être calculée à partir de la série de Fourier. On remplace la fonction $𝑓(𝑡)$ par sa série de Fourier : 

```{figure} rms.png
---
width: 30%
name: F:proprietes:rms
---
```

Par contre, il est généralement plus simple de calculer la valeur RMS à partir de la fonction, plutôt que la série de Fourier. 

## Phénomène de Gibbs

Le phénomène de Gibbs est l'apparition d'oscillations au abords des discontinuités d'un signal,
lorsque celui-ci est reconstruit à partir des coefficients de sa série de Fourier.
On comprend que si la reconstruction n'utilise qu'une partie des coefficients de la série de Fourier,
alors le signal reconstruit sera différent du signal original.
Lorsque le nombre de coefficients augmente, la reconstruction se rapproche du signal,
sauf au discontinuités où il se produit des oscillations qui ne peuvent s'atténuer.

```{figure} gibbs.svg
---
name: F:props-fourier:gibbs
---
Reconstruction d'un créneau à partir de quelques coefficients de sa série de Fourier discrète.
```



