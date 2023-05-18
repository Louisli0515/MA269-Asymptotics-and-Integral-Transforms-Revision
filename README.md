# MA269-Asymptotics-and-Integral-Transforms-Revision
My own notes about the MA269 revision, mainly from the notes and example sheets

## Lecture notes

[ma269_lecture_notes.pdf](https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/files/11502774/ma269_lecture_notes.pdf)

First of all, feel free to download the 2022-2023 lecture notes for MA269 Asymptotics and Integral Transforms.

## Formula sheet

[ma269_formula_sheet.pdf](https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/files/11502782/ma269_formula_sheet.pdf)

Second, in this module, we are going to cover a lot of computations, so some expansions and formulas are really useful.

## Example sheets

### Big O notation

* For functions $f(x)$ and $g(x)$, we say that $$f(x) = O(g(x))\quad\text{as}\quad x\to a\quad\Leftrightarrow \left|\frac{f(x)}{g(x)}\right|\text{is bounded as}x\to a.$$
* Or it is equivalent to say $$\exists M,\delta\quad \text{s.t.} \left|\frac{f(x)}{g(x)}\right| < M\quad\forall |x-a| < \delta.$$
* Or it is equivalent to say $$\lim_{x\to a}\sup\left|\frac{f(x)}{g(x)}\right| < \infty.$$
* Think of this as $f$ is ***no bigger than*** order $g$.
* We can also let $a = \pm\infty$.

### Little o notation

* For functions $f(x)$ and $g(x)$, we say that $$f(x) = o(g(x))\quad\text{as}\quad x\to a\quad\Leftrightarrow \left|\frac{f(x)}{g(x)}\right|\to 0\quad\text{as}\quad x\to a.$$
* Think of this as $f$ is ***smaller than*** order $g$.

### Big $\Theta$ notation

* For functions $f(x)$ and $g(x)$, we say that $$f(x) = \Theta(g(x))\quad\text{as}\quad x\to a\Leftrightarrow\quad f(x) = O(g(x))\quad\text{and}\quad g(x) = O(f(x))\quad\text{as}\quad x\to a.$$
* Think of this as $f$ is ***equal to*** order $g$.

### Asymptotic Series

* The function $f(x)$ is said to have an ***asymptotic series*** as $x\to a$, $$f(x)\sim\sum_{j=1}^{N}f_{j}(x)\quad\text{as}\quad x\to a\quad\Leftrightarrow\quad\forall\text{finite} M\leq N,\quad f(x) - \displaystyle\sum_{j=1}^{M}f_{j}(x) = o(f_{M}(x)).$$
* This is equivalent as saying $$\left|\frac{f(x) - \displaystyle\sum_{j=1}^{M}f_{j}(x)}{f_{M}(x)}\right|\to 0\quad\text{as}\quad x\to a.$$
* This means when approximating $f$ by partial sums $\displaystyle\sum_{j=1}^{M}f_{j}(x)$, the error is ***smaller than*** the last included term provided $|x-a|$ is small enough.

### Asymptotic Sequences

* We often write $$f(x)\sim\sum_{n=1}^{N} a_{n}\alpha_{n}(x)\quad\text{as}\quad x\to a,$$ where $\alpha_{n}$ is an ***asymptotic sequence***.
* $\alpha_{n}$ is an ***asymptotic sequence*** if and only if $\alpha_{n+1} = o(\alpha_{n})\quad\text{as}\quad x\to a\quad\text{for all}\quad n.$

#### Uniqueness for the coefficients

* Given an asymptotic sequence $\alpha_{n}(x)$, and an asymptotic series $f(x)\sim\displaystyle\sum_{n=1}^{N} a_{n}\alpha_{n}(x)$ as $x\to a$, then the coefficients $a_{n}$ are ***unique*** since by definition, $$a_{n} = \lim_{x\to a} \frac{f(x)-\displaystyle\sum_{j=1}^{n-1}a_{j}\alpha_{j}(x)}{\alpha_{n}(x)}.$$

#### Non-uniqueness for the asymptotic series

* As $x\to a$, $f(x)$ may have ***different*** asymptotic series. For example as $x\to 0$, $$\tan x\sim x+\frac{1}{3}x^{3}+\frac{2}{15}x^{5}\sim x\cos x+\frac{5}{6}(x\cos x)^{3}+\frac{161}{120}(x\cos x)^{5}\sim \frac{1}{\sqrt{2}}\sinh(\sqrt{2}x)+\frac{1}{10}\left(\frac{1}{\sqrt{2}}\sinh(\sqrt{2}x)\right)^{5}.$$
