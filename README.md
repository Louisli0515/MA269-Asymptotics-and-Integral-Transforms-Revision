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

### Asymptotics of Algebraic Equations

Consider $x^{2}+\varepsilon x - 1 = 0$ as $\varepsilon\to 0$. How could we find the error without using the quadratic formula.

#### Method 1: iteration

* Rearranging, $x^{2} = 1-\varepsilon x$, and so $x_{+} = \sqrt{1-\varepsilon x_{+}}$. 
* Try $x_{0} = 1$ and $x_{n+1} = \sqrt{1-\varepsilon x_{n}}$. This gives $$x_{1} = \sqrt{1-\varepsilon x_{0}} = 1-\frac{\varepsilon}{2}- \frac{\varepsilon^{2}}{8} - \frac{\varepsilon^{3}}{16}+...$$ $$x_{2} = \sqrt{1-\varepsilon x_{1}} = 1+\frac{1}{2}\left(-\varepsilon + \frac{\varepsilon^{2}}{2}+\frac{\varepsilon^{3}}{8}+...\right)-\frac{1}{8}\left(-\varepsilon + \frac{\varepsilon^{2}}{2}+\frac{\varepsilon^{3}}{8}+...\right)^{2}-.... = 1-\frac{\varepsilon}{2}+\frac{\varepsilon^{2}}{8}+\frac{\varepsilon^{3}}{4}+...$$ 

* Lots of work, so ***not recommended***.

#### Method 2: successive approximation

* If $\varepsilon = 0$, then $x^{2} - 1 = 0$ and so $x = \pm 1$ and $x_{+} = 1$. If $\varepsilon \ne 0$, then try $x = 1+e_{1}$, where $e_{1}$ is the error in the previous guess, and we hope $e_{1}$ is ***smaller*** than the previous guess of $x = 1$. Then $$0 = (1+e_{1})^{2}+\varepsilon(1+e_{1}) - 1 = 1+2e_{1}+e_{1}^{2} + \varepsilon + \varepsilon e_{1} - 1\approx 2e_{1}+\varepsilon,$$ where we have neglected terms that are ***smaller than*** the ones we have included. 
* This gives $e_{1}\approx -\frac{\varepsilon}{2}$, so we set $x = 1-\varepsilon/2 + e_{2}$, where $e_{2}$ is the next error we hope is ***smaller than*** the previous error $e_{1} = \Theta(\varepsilon)$. Substituting $e_{1} = -\varepsilon/2 + e_{2}$ gives $$0 = 2\left(-\frac{\varepsilon}{2}+e_{2}\right)+\left(-\frac{\varepsilon}{2}+e_{2}\right)^{2}+\varepsilon + \varepsilon\left(-\frac{\varepsilon}{2}+e_{2}\right) = e_{2}^{2}+2e_{2}-\frac{\varepsilon^{2}}{4}\approx 2e_{2}-\frac{\varepsilon^{2}}{4},$$ where we have neglected terms that are ***smaller than*** the ones we have included. 
* This gives $e_{2}\approx \varepsilon^{2}/8$, and so $x = 1-\varepsilon/2 + \varepsilon^{2}/8 + o(\varepsilon^{2})$, provided $e_{3} = o(e_{2}).$

#### Method 3: series expansion

* Guess the series expansion $x_{+} = a_{0}+\varepsilon a_{1}+\varepsilon^{2} a_{2} + \varepsilon^{3} a_{3} + O(\varepsilon^{4})$ and substitute it in: $$\left(a_{0}+\varepsilon a_{1}+\varepsilon^{2} a_{2}+\varepsilon^{3}a_{3} + O(\varepsilon^{4})\right)^{2} + \varepsilon \left(a_{0}+\varepsilon a_{1}+\varepsilon^{2} a_{2} + \varepsilon^{3} a_{3} + O(\varepsilon^{4})\right) - 1 = 0.$$
* Therefore matching coefficients: $$O(\varepsilon^{0}): 0 = a_{0}^{2} - 1\implies a_{0} = 1.$$ $$O(\varepsilon^{1}): 0 = 2a_{0}a_{1} + a_{0} = 2a_{1} + 1\implies a_{1} = -\frac{1}{2}.$$ $$O(\varepsilon^{2}): 0 = 2a_{0}a_{2} + a_{1}^{2} + a_{1} = 2a_{2} + \frac{1}{4}-\frac{1}{2}\implies a_{2} = \frac{1}{8}.$$ $$O(\varepsilon^{3}): 0 = 2a_{1}a_{2} + 2a_{0}a_{3} + a_{2} = -\frac{1}{8} + 2a_{3} + \frac{1}{8}\implies a_{3} = 0.$$
* So $x = 1-\varepsilon/2+\varepsilon^{2}/8+0\varepsilon^{3}+O(\varepsilon^{4})$.
