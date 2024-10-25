(C:fourier)=
# Transformée de Fourier

On peut considérer qu'un signal apériodique est le cas limite d'un signal périodique de période infinie.
Dans ce cas, la série de Fourier tend vers la transformée de Fourier :

```{margin}
Cette formule est la transformée de Fourier.
```

$$
X(f) = \int_{-\infty}^{+\infty} x(t) e^{-j 2 \pi f t} dt
$$

où $f\in\mathbb{R}$ est la fréquence.
De même qu'avec la série de Fourier, le signal temporel $x$ peut être reconstruit à partir de $X$ :

```{margin}
Cette formule est la transformée de Fourier inverse.
```

$$
x(t) = \int_{-\infty}^{+\infty} X(f) e^{+j 2 \pi f t} df.
$$

On peut remarquer que le spectre d'une transformée de Fourier est une représentation continue de la fréquence du signal à l'inverse du spectre d'une série de Fourier qui est une représentation discrète de la fréquence du signal (peut prendre des valeurs uniquement à la fréquence fondamentale et à ses multiples).

## Représentation

On l'a vu, les transformations de Fourier $X$ du signal $x$ sont des signaux.
En raison de l'exponentielle complexe dans les formules ci-dessus, $X$ est souvent complexe.
Pour représenter $X$, il faudrait donc se placer dans un espace en trois dimensions dont les axes seraient
la fréquence ($f$ ou $k$), la partie réelle de $X$ et la partie imaginaire de $X$.
Vous conviendrez que ce n'est pas commode de représenter un signal à valeurs complexes sur une feuille ou un écran...

Pour cette raison, les transformations de Fourier sont représentées à l'aide de deux graphiques :
- le premier représente le module de $X$ en fonction de la fréquence,
- le second représente l'argument de $X$ en fonction de la fréquence.

L'ensemble de ces deux graphiques s'appelle le « spectre ».

```{figure} spectre.svg
---
name: F:fourier:exemple
---
Spectre de la transformée de Fourier de $3\,\mathrm{rect}(t+1/4)$.
```

On peut être surpris que le spectre présente des fréquences « négatives » (à gauche de l'axe des ordonnées).
En fait, il ne s'agit pas de fréquences négatives (cela n'a pas de sens),
mais d'exponentielles complexes tournant en sens opposé aux exponentielles complexes de la partie à droite de l'axe des ordonnées.

```{figure} negative-freqs.png
---
height: 250px
name: F:fourier:freqs-neg
---
Illustration des exponentielles complexes associées à l'axe des fréquences d'un spectre.
```

## Récapitulatif

Quelle que soit la transformation, on peut donc résumer ainsi les différentes notations utilisées :

<table>
<thead>
  <tr>
      <td><ul><li>Domaine :</li></ul></td><td>&emsp;</td>
    <td>temporel</td>
    <td><span class="math notranslate nohighlight">\(\quad\xrightarrow{\;\mathcal{F}\;}\quad\)</span></td>
    <td>fréquentiel</td>
  </tr>
</thead>
<tbody>
  <tr>
    <td><ul><li>Signal :</li></ul></td><td>&emsp;</td>
    <td><span class="math notranslate nohighlight">\(x\)</span></td>
    <td><span class="math notranslate nohighlight">\(\quad\xrightarrow{\;\mathcal{F}\;}\quad\)</span></td>
    <td><span class="math notranslate nohighlight">\(X\)</span></td>
  </tr>
  <tr>
    <td><ul><li>Variable :</li></ul></td><td>&emsp;</td>
    <td><span class="math notranslate nohighlight">\(t\)</span> ou <span class="math notranslate nohighlight">\(n\)</span></td>
    <td><span class="math notranslate nohighlight">\(\quad\xrightarrow{\;\mathcal{F}\;}\quad\)</span></td>
    <td><span class="math notranslate nohighlight">\(f\)</span> ou <span class="math notranslate nohighlight">\(k\)</span></td>
  </tr>
  <tr>
    <td><ul><li>Exemple d'unité :</li></ul></td><td>&emsp;</td>
    <td>seconde (s)</td>
    <td><span class="math notranslate nohighlight">\(\quad\xrightarrow{\;\mathcal{F}\;}\quad\)</span></td>
    <td>s<sup>–1</sup> = hertz (Hz)</td>
  </tr>
</tbody>
</table>
<br />

Par ailleurs, on remarque que le passage du domaine temporel au domaine fréquentiel utilise une exponentielle du type $e^{-\theta}$
alors que l'inverse utilise $e^{+\theta}$ où :
* $\theta = j 2 \pi k t / T$ pour la SF,
* $\theta = j 2 \pi f t    $ pour la TF,
* $\theta = j 2 \pi k n / N$ pour la SFD (ou TFD).

On retrouve donc toujours le même schéma pour $\theta$ :

$$
\theta = j 2 \pi \times \text{fréquence} \times \text{temps} \times \text{période éventuelle}
$$

```{warning}
$t$ et $f$ sont les _variables_ de temps et de fréquence, respectivement.
En revanche, $T$ et son inverse $F=1/T$ sont des _constantes_ représentant la période et la fréquence d'un signal, respectivement.
Ne confondez pas la fréquence $f$ qui est une variable dont dépend $X$
et la fréquence $F$ qui est une constante représentant la fréquence d'un signal périodique $x$ !

```

