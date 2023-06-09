# MA269-Asymptotics-and-Integral-Transforms-Revision
My own notes about the MA269 revision, mainly from the notes and example sheets

- [MA269-Asymptotics-and-Integral-Transforms-Revision](#ma269-asymptotics-and-integral-transforms-revision)
  * [Lecture notes](#lecture-notes)
  * [Formula sheet](#formula-sheet)
  * [Example sheets](#example-sheets)
    + [Big O notation](#big-o-notation)
    + [Little o notation](#little-o-notation)
    + [Big $\Theta$ notation](#big---theta--notation)
    + [Asymptotic Series](#asymptotic-series)
    + [Asymptotic Sequences](#asymptotic-sequences)
      - [Uniqueness for the coefficients](#uniqueness-for-the-coefficients)
      - [Non-uniqueness for the asymptotic series](#non-uniqueness-for-the-asymptotic-series)
    + [Asymptotics of Algebraic Equations](#asymptotics-of-algebraic-equations)
      - [Method 1: iteration](#method-1--iteration)
      - [Method 2: successive approximation](#method-2--successive-approximation)
      - [Method 3: series expansion](#method-3--series-expansion)
    + [Singular perturbations](#singular-perturbations)
    + [The Exponential Integral](#the-exponential-integral)
      - [First attempt: Taylor expansion](#first-attempt--taylor-expansion)
      - [Second attempt: Split the integral](#second-attempt--split-the-integral)
    + [Watson's Lemma](#watson-s-lemma)
      - [Watson's Lemma Theorem](#watson-s-lemma-theorem)
      - [Watson's Lemma General Form](#watson-s-lemma-general-form)
    + [Laplace's Method](#laplace-s-method)
      - [Laplace's Method Theorem](#laplace-s-method-theorem)
      - [Stirling's Formula](#stirling-s-formula)
    + [The Method of Stationary Phase](#the-method-of-stationary-phase)
    + [The Method of Steepest Descent](#the-method-of-steepest-descent)
      - [Stationary Phase](#stationary-phase)
    + [Asymptotics of Differential Equations](#asymptotics-of-differential-equations)
      - [Nondimensionalisation and scaling](#nondimensionalisation-and-scaling)
      - [Regular problems](#regular-problems)
      - [Rescaling and balancing](#rescaling-and-balancing)
      - [Singular problems and Van Dyke's matching rule](#singular-problems-and-van-dyke-s-matching-rule)
      - [Composite expansions](#composite-expansions)
      - [Rescaling for nonlinear differential equations](#rescaling-for-nonlinear-differential-equations)
    + [Integral Transforms](#integral-transforms)
    + [Complex Methods](#complex-methods)
      - [A useful estimate for the magnitude of a complex integral](#a-useful-estimate-for-the-magnitude-of-a-complex-integral)
      - [Cauchy's Theorem](#cauchy-s-theorem)
      - [The Residue Theorem](#the-residue-theorem)
      - [Contour integral example](#contour-integral-example)
    + [Fourier Transforms](#fourier-transforms)
      - [Definition of Fourier transform and inverse Fourier transform](#definition-of-fourier-transform-and-inverse-fourier-transform)
      - [Properties of Fourier transforms](#properties-of-fourier-transforms)
      - [Example with ODE](#example-with-ode)
      - [Convolution](#convolution)
      - [Parseval's theorem](#parseval-s-theorem)
    + [Laplace Transforms](#laplace-transforms)
      - [Definition of Laplace Transform and Inverse Laplace Transform](#definition-of-laplace-transform-and-inverse-laplace-transform)
      - [Some really important and useful Laplace Transforms](#some-really-important-and-useful-laplace-transforms)
      - [Properties of Laplace transforms](#properties-of-laplace-transforms)
      - [Example with ODE](#example-with-ode-1)
      - [Convolution](#convolution-1)
      - [Solving PDEs](#solving-pdes)
      - [Limits](#limits)
      - [Summary of Fourier and Laplace transform](#summary-of-fourier-and-laplace-transform)


## Lecture notes

[ma269_lecture_notes.pdf](https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/files/11502774/ma269_lecture_notes.pdf)

First of all, feel free to download the 2022-2023 lecture notes for MA269 Asymptotics and Integral Transforms.

## Formula sheet

[ma269_formula_sheet.pdf](https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/files/11502782/ma269_formula_sheet.pdf)

Second, in this module, we are going to cover a lot of computations, so some expansions and formulas are really useful.

## Example sheets

[MA269_Asymptotics_Integral_transforms_tutorial_sheet.pdf](https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/files/11712953/MA269_Asymptotics_Integral_transforms_tutorial_sheet.pdf)

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

### Singular perturbations

* The previous problem $x^{2}+\varepsilon x - 1 = 0$ is called ***regular***; setting $\varepsilon = 0$ gives a solution, and $\varepsilon$ being small but non-zero changes that solution a little. 
* However consider now $\varepsilon x^{2} + x - 1 = 0$. If $\varepsilon = 0$, we get only one solution. Such problems are ***singular***.

### The Exponential Integral

* The exponential integral $E_{1}(z)$, is defined for $z > 0$ as $$E_{1}(z) = \int_{z}^{\infty}\frac{e^{-x}}{x}\mathrm{d}x,$$ it turns out that $E_{1}(0)$ is ***singular***, but how singular is it?

#### First attempt: Taylor expansion

* We use the Taylor expansion of $e^{-x}$: $$E_{1}(\varepsilon) = \int_{\varepsilon}^{\infty}\frac{e^{-x}}{x}\mathrm{d}x = \int_{\varepsilon}^{\infty}\frac{1}{x} - 1 + \frac{x}{2!}-\frac{x^{2}}{3!}+...\mathrm{d}x = \left[\log x - x + \frac{x^{2}}{2\times 2!}-\frac{x^{3}}{3\times 3!}+...\right]_ {\varepsilon}^{\infty}.$$
* The expansion ***diverges at infinity***. Taylor expansion lost the fact that $e^{-x}$ ***decays rapidly*** as $x\to\infty$.

#### Second attempt: Split the integral

* We then split the integral to compare: $$E_{1}(\varepsilon) = \int_{\varepsilon}^{a}\frac{e^{-x}}{x}\mathrm{d}x + \int_{a}^{\infty}\frac{e^{-x}}{x}\mathrm{d}x = \left[\log x - x + \frac{x^{2}}{2\times 2!} - \frac{x^{3}}{3\times 3!} + ...\right]_ {\varepsilon}^{a} + E_{1}(a) = -\log\varepsilon + \varepsilon - \frac{\varepsilon^{2}}{2\times 2!}+\frac{\varepsilon^{3}}{3\times 3!} + \left[E_{1}(a) + \log a - a + \frac{a^{2}}{2\times 2!}-\frac{a^{3}}{3\times 3!}\right].$$
* The final term is ***independent*** of $\varepsilon$, as $\varepsilon$ does not occur in the expression and is independent of $a$, as $a$ dosen't appear in the first term and $E_{1}(\varepsilon)$ should be independent of $a$.
* Therefore, the final term must be a ***constant***.

### Watson's Lemma

* Consider $$I(\lambda) = \int_{0}^{a}f(x)e^{-\lambda x}\mathrm{d}x.$$ If we are interested in $\lambda\to\infty$, we can rescale using $x = t/\lambda$, giving $$I(\lambda) = \int_{0}^{a\lambda}f\left(\frac{t}{\lambda}\right)e^{-t}\frac{\mathrm{d}t}{\lambda} = \sum_{n=0}^{\infty}\frac{f^{(n)}(0)}{\lambda^{n+1}}+O\left(\frac{e^{-\lambda a}}{\lambda}\right).$$

#### Watson's Lemma Theorem

* If $f(x)\sim\displaystyle\sum_{n=0}^{N}a_{n}x^{\alpha_{n}}$ as $x\to 0$ with $\alpha_{0} > -1$, and if $f(x)$ is ***bounded*** for $x\in[\varepsilon, a]$ for all $\varepsilon > 0$, then $$\int_{0}^{a}f(x)e^{-\lambda x}\mathrm{d}x\sim\sum_{n=0}^{N}\frac{a_{n}\Gamma(\alpha_{n}+1)}{\lambda^{\alpha_{n}+1}}\quad\text{as}\quad\lambda\to\infty,$$ where $$\Gamma(n+1) = \int_{0}^{\infty}t^{n}e^{-t}\mathrm{d}t = \left[-t^{n}e^{-t}\right]_ {0}^{\infty} + n\int_{0}^{\infty} t^{n-1}e^{-t}\mathrm{d}t = n!.$$

#### Watson's Lemma General Form

* Consider $$I(\lambda) = \int_{a}^{b}f(x)e^{\lambda g(x)}\mathrm{d}x\quad\text{as}\quad\lambda\to\infty.$$
* An ***exponentially large contribution*** comes from near where $g(x)$ is ***largest***. If $\max_{x\in[a,b]}g(x)$ is at an endpoint, say at $a$, and $g'(a)\ne 0$, then Watson's lemma is ***applicable***: $$I(\lambda) = \int_{a}^{a+\delta}f(x)e^{\lambda g(x)}\mathrm{d}x + \int_{a+\delta}^{b}f(x)e^{\lambda g(x)}\mathrm{d}x.$$
* The second integral will be exponentially small in comparison with the first. So ***changing variables*** by setting $y = g(a) - g(x)$, $$I(\lambda) = e^{\lambda g(a)}\int_{0}^{g(a) - g(a + \delta)} f(x(y))e^{-\lambda y}\frac{\mathrm{d}y}{-g'(x(y))}+O\left(e^{\lambda g(a+\delta)}\right) = e^{\lambda g(a)}\int_{0}^{g(a)-g(a+\delta)}F(y)e^{-\lambda y}\mathrm{d}y + O\left(e^{\lambda g(a+\delta)}\right)\sim e^{\lambda g(a)}\sum_{n=0}^{N}\frac{F_{n}\Gamma(\alpha_{n}+1)}{\lambda^{\alpha_{n}+1}},$$ where $F(y) = \frac{f(x(y))}{-g'(x(y))}\sim\displaystyle\sum_{n=0}^{N}F_{n}y^{\alpha_{n}}\quad\text{as}\quad y\to 0.$

### Laplace's Method

* We again consider the integral $$I(\lambda) = \int_{a}^{b}f(x)e^{\lambda g(x)}\mathrm{d}x\quad\text{as}\quad\lambda\to\infty.$$
* Suppose that $g(x)$ has a ***maximum*** at $x_{0}\in (a,b)$, where we assume that $g'(x_{0}) = 0$ and that $g''(x_{0}) < 0$. Then locally near that maximum, $$g(x)\approx g(x_{0}) + (x-x_{0})g'(x_{0}) + \frac{1}{2}(x-x_{0})^{2}g''(x_{0}) + O((x-x_{0})^{3}).$$
* So with the change of variable $y = (x-x_{0})\sqrt{-\lambda g''(x_{0})}$, $$I(\lambda) = e^{\lambda g(x_{0})}\int_{a}^{b}f(x)\exp\set{\frac{1}{2}\lambda g''(x_{0})(x-x_{0})^{2}+O(\lambda(x-x_{0})^{3})}\mathrm{d}x\sim e^{\lambda g(x_{0})}\int_{-\infty}^{\infty}\frac{f(x_{0})e^{-\frac{1}{2}y^{2}}}{\sqrt{-\lambda g''(x_{0})}}\mathrm{d}y\quad\text{as}\quad\lambda\to\infty = \sqrt{\frac{2\pi}{-\lambda g''(x_{0})}}f(x_{0})e^{\lambda g(x_{0})}.$$

#### Laplace's Method Theorem

* If $g(x)$ is twice continuously differentiable on $[a,b]$, and $\exists x_{0}\in (a,b)$ such that $g(x_{0}) = \max_{x\in[a,b]}g(x)$ and $g''(x_{0}) < 0$, then $$\int_{a}^{b}e^{\lambda g(x)}\mathrm{d}x\sim e^{\lambda g(x_{0})}\sqrt{\frac{2\pi}{-\lambda g''(x_{0})}}\quad\text{as}\quad\lambda\to\infty.$$
* $a$ and $b$ can be $\pm\infty$.
* Can include $f(x)$ in the integrand by expanding $f$ in a asymptotic series about $x_{0}$.
* Can get ***further*** terms in the asymptotic series of $I(\lambda)$ by expanding $g(x)$ about $x_{0}$ too.
* Can deal with problematic cases (e.g. $x_{0} = a, g''(x_{0}) = 0, f(x_{0}) = 0$, etc.) by expanding about $x_{0}$.
* Can deal with multiple maxima by splitting integral so each integral has ***only one maximum***.

#### Stirling's Formula

* Consider $$\Gamma(\lambda + 1) = \int_{0}^{\infty}x^{\lambda}e^{-x}\mathrm{d}x.$$ We have already seen that $\Gamma(n+1) = n!$, but how does $\lambda! = \Gamma(\lambda+1)$ behave as $\lambda\to\infty$?
* Note that $$\Gamma(\lambda+1) = \int_{0}^{\infty}e^{-x + \lambda\log x}\mathrm{d}x = \int_{0}^{\infty}e^{-x}e^{\lambda\log x}\mathrm{d}x,$$ so we first try $f(x) = e^{-x}$ and $g(x) = \log x$. But then $g(x)$ is ***unbounded***, and $g'(x) = \frac{1}{x}\ne 0$. So our try ***fails***.
* The integrand has a ***maximum*** when $$\frac{\mathrm{d}}{\mathrm{d}x}(x^{\lambda}e^{-x}) = x^{\lambda-1}e^{-x}(\lambda - x)\implies x = \lambda.$$
* The ***motives the change of variable*** $x = \lambda t$, leading to $$\Gamma(\lambda+1) = \int_{0}^{\infty}\lambda^{\lambda}t^{\lambda}e^{-\lambda t}\lambda\mathrm{d}t = \lambda^{\lambda + 1}\int_{0}^{\infty}e^{-\lambda(t-\log t)}\mathrm{d}t,$$ so we take $f(t) = 1$ and $g(t) = -(t-\log t)$. Hence by ***differentiation*** we note that when $t_{0} = 1$, $g'(t_{0}) = 0$ and reaches the ***maximum***. Also we calculate that $g''(t_{0}) = -1.$
* Using also that $g(t_{0}) = -1$, Laplace's method gives $$\Gamma(\lambda + 1) \sim \lambda^{\lambda + 1}\sqrt{\frac{2\pi}{-\lambda\times-1}}e^{-\lambda} = \sqrt{2\pi\lambda}\lambda^{\lambda}e^{-\lambda},$$ which is the Stirling's approximation.

### The Method of Stationary Phase

* Suppose we have a rapidly ***oscillating integral***, say $$I(\lambda) = \int_{0}^{\infty}f(x)\cos(\lambda g(x))\mathrm{d}x.$$
* Because of ***cancellation***, the integral are hard to compute, as $\lambda\to\infty$, the ***dominant*** contribution comes from where there is the ***least cancellation*** due to ***oscillation***. The Method of Stationary Phase states that $$I(\lambda)\sim\sqrt{\frac{2\pi}{\lambda|g''(x_{0})|}}f(x_{0})\cos(\lambda g(x_{0})\pm\pi/4),$$ where $g'(x_{0}) = 0$ and $\pm 1 = \text{sgn}(g''(x_{0}).$

### The Method of Steepest Descent

* Suppose for large $\lambda$, we want to evaluate the integral $$I(\lambda) = \int_{\mathcal{C}}f(z)e^{\lambda g(z)}\mathrm{d}z,$$ where $\mathcal{C}$ is some contour in the complex plane (say $\mathcal{C} = \set{q(t):a\leq t\leq b}$)and $f(z)$ and $g(z)$ are complex differentiable.
* The ***dominant contribution*** might come from where $\text{Re}(g(z))$ is ***maximum***. Suppose along $\mathcal{C}$, this occurs at $z = z_{0} = q(t_{0})$, where $\frac{\mathrm{d}}{\mathrm{d}t}\text{Re}\left(g(q(t))\right) = 0$. So near $t_{0}$, $$f(q(t)) = f(z_{0})+...\quad g(q(t)) = g(z_{0}) + (t-t_{0})q'(t_{0})g'(z_{0})+...\quad f(z)e^{\lambda g(z)}\cong f(z_{0})e^{\lambda g(z_{0})}e^{\lambda (t-t_{0})q'(t_{0})g'(z_{0})},$$ which is highly oscillatory, so try another approach.
* Taking the contour with the lower $\text{Re}(g(z))$ means passing through the ***saddle point*** at $z = z_{* }$, where $g'(z_{* }) = 0$. Near $z_{* }$, $$f(z) = f(z_{* }) + (z-z_{* })f'(z_{* })+...,\quad g(z) = g(z_{* }) + 0 + \frac{1}{2}(z-z_{* })^{2}g''(z_{* })+...$$
* Steepest descent from $z_{* }$ means taking the direction where $\frac{1}{2}(z-z_{* })^{2}g''(z_{* }) < 0$ and ***real***.
* Parameterising the section of the ***steepest descent*** contour $\mathcal{C}_ {sd}$ near to $z_{* }$ by $t_{* }$, we therefore set $z-z_{* } = t_{* }/\sqrt{-\lambda g''(z_{* })}$.
* ***Changing variables*** to $t_{* }$, $$I(\lambda) = \int_{-\infty}^{\infty}\left(f(z_{* })+\frac{t_{* }f'(z_{* })}{\sqrt{-\lambda g''(z_{* })}} + O\left(\frac{1}{\lambda}\right)\right)\exp\set{\lambda g(z_{* }) - \frac{1}{2}t_{* }^{2}+O\left(\frac{1}{\sqrt{\lambda}}\right)}\frac{\mathrm{d}t_{* }}{\sqrt{-\lambda g''(z_{* })}} = \sqrt{\frac{2\pi}{-\lambda g''(z_{* })}} f(z_{* })e^{\lambda g(z_{* })}\left(1+O\left(\frac{1}{\lambda}\right)\right). $$
* The ***dominant contribution*** comes from a region of size $z - z_{* } = \Theta(\lambda^{-1/2}),$ so the details of $\mathcal{C}_ {sd}$ aren't important away from the ***saddle point*** $z_{* }$.
* Sometimes there are ***more than one*** saddle point. The ***dominant contribution*** comes from the ***highest saddle point*** (with the ***biggest*** Re$(g(z))$) that mus tbe ***deformed*** through to get from the start point to the end point.
* Sometimes the highest Re$(g(z))$ is at an ***end point***. Then use ***Watson's Lemma*** instead for the ***dominant contribution***.

#### Stationary Phase

* Consider $$I(\lambda) = \int_{a}^{b}f(x)e^{i\lambda g(x)}\mathrm{d}x\quad\text{as}\quad\lambda\to\infty,$$ with $f$ and $g$ real. Suppose $g'(x_{0}) = 0$ for some $x_{0}\in(a,b)$. Then near $x_{0}$, $$ig(x) = ig(x_{0}) + i(x-x_{0})g'(x_{0}) + \frac{1}{2}i(x-x_{0})^{2}g''(x_{0})+...$$
* For the steepest descent contour, we want $$\frac{i}{2}(x-x_{0})^{2}g''(x_{0}) = -\frac{1}{2}t^{2}\implies x = x_{0} + \frac{te^{\pm i\pi/4}}{\sqrt{\pm g''(x_{0})}},$$ where $\pm 1 = \text{sgn}(g''(x_{0})).$ 
* Applying the steepest descent formula, $$I(\lambda) = \int_{a}^{b} f(x)e^{i\lambda g(x)}\mathrm{d}x\sim\sqrt{\frac{2\pi}{\lambda|g''(x_{0})|}}f(x_{0})e^{i\lambda g(x_{0})\pm i\pi/4}\quad\text{as}\quad\lambda\to\infty.$$

### Asymptotics of Differential Equations

Consider a damped spring with extension $y^{* }(t^{* })$, governed by the differential equation $$m^{* }\frac{\mathrm{d}^{2}y^{* }}{(\mathrm{d}t^{* })^{2}} = -K^{* }y^{* }- D^{* }\frac{\mathrm{d}y^{* }}{\mathrm{d}t^{* }},$$ where a star denotes a ***dimensional quantity***, with units 

* $y^{* }$ = meters $(m)$,
* $t^{* }$ = seconds $(s)$,
* $m^{* }$ = kilograms $(kg)$,
* $K^{* }$ = $kgs^{-2}$,
* $D^{* }$ = $kgs^{-1}$.

#### Nondimensionalisation and scaling

In the above differential equation, is $D^{* } = 10kgs^{-1}$ large or small? Does it affect the possible types of behaviours of the spring or does it just scale the response?

To answer this, we ***nondomensionalise***. Pick a ***timescale*** $T^{* }$ and a ***lengthscale*** $L^{* }$, $$T^{* } = \sqrt{\frac{m^{* }}{K^{* }}},$$ and change to ***dimensionless variables***:

* $t^{* } = tT^{* } = t\sqrt{\frac{m^{* }}{K^{* }}}$ and $y^{* }(t^{* }) = L^{* }y(t)$, then
* $$\frac{\mathrm{d}y^{* }}{\mathrm{d}t^{* }} = L^{* }\sqrt{\frac{K^{* }}{m^{* }}}\frac{\mathrm{d}y}{\mathrm{d}t}$$ and $$\frac{\mathrm{d}^{2}y^{* }}{(\mathrm{d}t^{* })^{2}} = L^{* }\frac{K^{* }}{m^{* }}\frac{\mathrm{d}^{2}y}{\mathrm{d}t^{2}}.$$

Note that $\frac{\mathrm{d}y}{\mathrm{d}t}$ scales like $\frac{y}{t}$. The differential equation then becomes, on division by $K^{* }L^{* }$, $$\frac{\mathrm{d}^{2}y}{\mathrm{d}t^{2}} + R\frac{\mathrm{d}y}{\mathrm{d}t} + y = 0,$$ where $R = \frac{D^{* }}{\sqrt{K^{* }m^{* }}}$ is a ***dimensionless parameter***.

#### Regular problems

Consider $$\frac{\mathrm{d}^{2}y}{\mathrm{d}t^{2}} + \varepsilon\frac{\mathrm{d}y}{\mathrm{d}t} + y = 0\quad y(0) = 0\quad\text{and}\quad \dot{y}(0) = 1.$$

* Using ***Method 3: series expansion***, we guess a series $$y(t) = y_{0}(t) + \varepsilon y_{1}(t) + \varepsilon^{2}y_{2}(t)+...,$$
* Substituting in, $$(\ddot{y_{0}} + \varepsilon\ddot{y_{1}}+...) + (\varepsilon\dot{y_{0}}+\varepsilon^{2}\dot{y_{1}}+...) + (y_{0} + \varepsilon y_{1}+...) = 0,\quad y(0) = 0 = y_{0}(0)+\varepsilon y_{1}(0)+...\quad \dot{y}(0) = 1 = \dot{y_{0}}(0) + \varepsilon\dot{y_{1}}(0)+...$$
* Solving at each other, $$\Theta(\varepsilon^{0}): \ddot{y_{0}}+y_{0} = 0\quad y_{0}(0) = 0\quad \dot{y_{0}}(0) = 1\implies y_{0} = A_{0}\cos t+B_{0}\sin t = \sin t,$$ and $$\Theta(\varepsilon^{1}): \ddot{y_{1}} + \dot{y_{0}} + y_{1} = 0,\quad y_{1}(0) = 0\quad\dot{y_{1}}(0) = 0\implies \ddot{y_{1}}+y_{1} = -\cos t\implies y_{1}(t) = A_{1}\cos t + B_{1}\sin t - \frac{1}{2}t\sin t = -\frac{1}{2}t\sin t.$$
* So the ***asymptotic solution*** is $y\sim\sin t - \frac{1}{2}\varepsilon t\sin t+...$

#### Rescaling and balancing

Sometimes we need to rescale differential equations first. Consider $$\frac{\mathrm{d}^{2}y}{\mathrm{d}t^{2}} + \frac{1}{\varepsilon}\frac{\mathrm{d}y}{\mathrm{d}t} + y = 0\quad y(0) = 0,\quad\frac{\mathrm{d}y}{\mathrm{d}t}(0) = 1.$$

* Try ***change of variable*** $t = a\tau$. Then $$\frac{1}{a^{2}}\frac{\mathrm{d}^{2}y}{\mathrm{d}\tau^{2}} + \frac{1}{a\varepsilon}\frac{\mathrm{d}y}{\mathrm{d}\tau} + y = 0\quad, y(0) = 0,\quad \frac{\mathrm{d}y}{\mathrm{d}\tau}(0) = a.$$
* Mathcing terms: $$\frac{1}{a^{2}} = 1\implies a = 1,$$ $$\frac{1}{a\varepsilon} = 1\implies a = \frac{1}{\varepsilon}$$ and $$\frac{1}{a^{2}} = \frac{1}{a\varepsilon}\implies a = \varepsilon.$$
* For $a = \varepsilon$, we get $$\frac{\mathrm{d}^{2}y}{\mathrm{d}\tau^{2}} + \frac{\mathrm{d}y}{\mathrm{d}\tau} + \varepsilon^{2}y = 0\quad y(0) = 0,\quad \frac{\mathrm{d}y}{\mathrm{d}\tau}(0) = \varepsilon.$$
* Use ***Method 2: successive approximation***: for $\varepsilon = 0$, $$y_{0} = A_{0} + B_{0}e^{-\tau} = \varepsilon(1-e^{-\tau}).$$
* So try $y(\tau) = y_{0}(\tau) + e_{0}(\tau),$ $$\frac{\mathrm{d}^{2}e_{0}}{\mathrm{d}\tau^{2}} + \frac{\mathrm{d}e_{0}}{\mathrm{d}\tau} + \varepsilon^{2}e_{0}+\varepsilon^{3}(1-e^{-\tau}) = 0,\quad e_{0}(0) = 0,\quad \frac{\mathrm{d}y}{\mathrm{d}\tau}(0) = 0,$$ $$\implies e_{0} = -\varepsilon^{3}\tau(1+e^{-\tau}) + 2\varepsilon^{3}(1-e^{-\tau}) + e_{1}(\tau).$$
* Consequently, as $\varepsilon\to 0$ for fixed $\tau$, $$y\sim\varepsilon(1-e^{-\tau}) - \varepsilon^{3}(\tau(1+e^{-\tau}) - 2(1-e^{-\tau})).$$

#### Singular problems and Van Dyke's matching rule

* Suppose our solution $f(x)$ has an ***outer solution*** which satisfies, as $\varepsilon\to 0$ with $x$ fixed, $$f(x)\sim\sum_{n=0}^{P}\varepsilon^{n} f_{n}(x) = E_{P}f,$$ where $E_{p}$ means taking the first $(P+1)$ terms of the ***outer asymptotic series***. 
* Suppose also that for $x = \varepsilon\xi$, then as $\varepsilon\to 0$ with $\xi$ fixed, we obtain the ***inner solution*** $$f(\varepsilon\xi)\sim\sum_{n=0}^{Q}\varepsilon^{n} g_{n}(\xi) = H_{Q}f,$$ where $H_{Q}$ means taking the first $(Q+1)$ terms of the ***inner asymptotic seires***.
* ***Van Dyke's matching rule*** states that these two asymptotic series should match according to the matching rule, $$E_{P}H_{Q}f = H_{Q}E_{P}f,$$ for suitable values of $P$ and $Q$; i.e. expanding the ***inner solution*** in the ***outer variable*** gives the same as expanding the ***outer solution*** in the ***inner variable***. 

#### Composite expansions

Suppose that, for $x = \varepsilon\xi$, we have $$f(x)\sim E_{P}f = \sum_{n=0}^{P}\varepsilon^{n}f_{n}(x)$$ for fixed $x$ as $\varepsilon\to 0$, $$f(x)\sim H_{Q}f = \sum_{n=0}^{Q}\varepsilon^{n} g_{n}(\xi)$$ for fixed $\xi$ as $\varepsilon\to 0$, and suppose also that these inner and outer asymptotic series match according to Van Dyke's rule, then $$C(x;\varepsilon) = E_{P}f + H_{Q}f - E_{P}H_{Q}f$$ defines a ***composite expansion***, valid as $\varepsilon\to 0$ for fixed $x$ or fixed $\xi$. Indeed, $$E_{P}C = E_{P}E_{P}f + E_{P}H_{Q}f - E_{P}E_{P}H_{Q}f = E_{P}f,$$ and $$H_{Q}C = H_{Q}E_{P}f + H_{Q}H_{Q}f - H_{Q}H_{Q}E_{P}f = H_{Q}f.$$

* This composite expansion $C(x;\varepsilon)$ is not a Poincare series, and so is ***not necessarily unique***. For example, a multiplicative composite expansion is given by $$M(x;\varepsilon) = \frac{(E_{P}f)(H_{Q}f)}{E_{P}H_{Q}f}.$$

#### Rescaling for nonlinear differential equations

For nonlinear ODEs for $y(t)$, we may need to rescale $y$ as well as $t$. For example, consider $$\varepsilon\ddot{y}+y\dot{y} - y = 0.$$ 

* To leading order, for $y = \Theta(1)$ and $t = \Theta(1)$, $$0 = y_{0}\dot{y_{0}} - y_{0} = y_{0}(\dot{y_{0}} - 1)\implies y_{0} = 0\quad\text{or}\quad y_{0} = A+t.$$
* In either case, $y_{0}\approx 0$ for some value of $t$, and near that value of $t$ we would have $y_{0} = \Theta(\varepsilon)$, and therefore $\varepsilon\ddot{y_{0}}$ could be ***important***.
* So instead, we consider rescaling $t = \varepsilon^{\alpha}\tau$ and $y(t) = \varepsilon^{\beta}Y(\tau)$. Then $$\varepsilon^{1+\beta - 2\alpha}Y'' + \varepsilon^{2\beta - \alpha}Y' - \varepsilon^{\beta} Y = 0.$$
* Mathcing the powers of $\varepsilon$ in these three terms gives $\alpha = \beta = \frac{1}{2}$, for which the ODE becomes $$\sqrt{\varepsilon}(Y'' + YY' - Y) = 0,$$ which is a full nonlinear problem with ***no small parameters***.

### Integral Transforms

Given a function $f(x)$, and integral transformation of $f$ yields another function $g(y)$, where $$g(y) = \int_{\mathcal{C}}f(x)K(x,y)\mathrm{d}x.$$

Often, $\mathcal{C}$ is $\mathbb{R}$ or $[0,\infty)$. $K(x,y)$ is called the ***kernel*** of the integral transform.

### Complex Methods 

#### A useful estimate for the magnitude of a complex integral

* A useful estimate for the magnitude of a complex integral is that $$\left|\int_{\mathcal{C}}f(z)\mathrm{d}z\right|\leq\max_{z\in\mathcal{C}}|f(z)|\int_{a}^{b}\left|\frac{\mathrm{d}q}{\mathrm{d}t}\right|\mathrm{d}t = \max_{z\in\mathcal{C}}|f(z)|L,$$ where $L$ is the length of the curve $\mathcal{C}$.

#### Cauchy's Theorem

* If $f(z)$ is ***differentiable everywhere*** in $\mathcal{D}$ and $\mathcal{D}$ is ***simply connected***, which means if any path in $\mathcal{D}$ can be smoothly deformed into any other path in $\mathcal{D}$ between the same ned points without moving the end points, then the integral of $f(z)$ is independent of the path.

<img width = 50% height = 50% src = https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/assets/128298224/26de83ac-d2d7-4979-b239-1a52db7e9f40>

#### The Residue Theorem

First of all, consider an isolated singularity of $f(z)$ at $z_{0}$, so that in some neighbourhood $\mathcal{A}$ of $z_{0}$, $f(z)$ is ***differentiable*** on $\mathcal{A}\setminus\set{z_{0}}$. We classfiy the singularity at $z_{0}$ as follows:

* If $\lim_{z\to z_{0}} f(z)$ exists, then $z_{0}$ is a ***removable singularity***.
* If $\lim_{z\to z_{0}}(f(z) - a_{1}/(z-z_{0}))$ exists for some $a_{1}\ne 0$, then $f$ has a ***simple pole*** at $z_{0}$ with ***residue*** $\text{Res}(f,z_{0}) = a_{1}$.
* If the limit $$\lim_{z\to z_{0}}\left(f(z)-\frac{a_{1}}{z-z_{0}}-\frac{a_{2}}{(z-z_{0})^{2}}-...-\frac{a_{n}}{(z-z_{0})^{n}}\right)$$ exists for some $n$ and some $a_{1},...,a_{n}$ with $a_{n}\ne 0$, then $f$ has a ***pole of order*** $n$ at $z_{0}$.
* Otherwise, $f$ has an ***essential singularity*** at $z_{0}$, e.g. $$f(z) = e^{1/z}.$$

#### Contour integral example

Consider the function $\tilde{g}(\omega) = \frac{2}{5+2i\omega - \omega^{2}}$, the Fourier inversion formula gives $$g(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty}\frac{2e^{i\omega t}}{5+2i\omega - \omega^{2}}\mathrm{d}\omega.$$

<img width = 50% height = 50% src = https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/assets/128298224/ea6da8a0-4ec0-4751-81d1-00ea828c498e>

* Consider the integration contour given by $\mathcal{C}_ {\pm} = \set{Re^{\pm i\theta}:0\leq\theta\leq\pi}$. Along $\mathcal{C}_ {+}$, provided $t > 0$, $$\left|\frac{1}{2\pi}\int_{\mathcal{C}_ {+}}\tilde{g}(\omega)e^{i\omega t}\mathrm{d}\omega\right|\leq\frac{1}{2\pi}\frac{2}{R^{2}-2R-5}\cdot 1\cdot \pi R\to 0,$$ as $R\to\infty$.
* The part $\frac{2}{R^{2}-2R-5}\leq\max|\tilde{g}|$, the part $1 = \max|e^{i\omega t}|$ and $\pi R = L$.
* Hence if $\mathcal{C}_ {1} = \set{t:-R\leq t\leq R}$, then for $t > 0$, $$\frac{1}{2\pi}\int_{-\infty}^{\infty}\tilde{g}(\omega)e^{i\omega t}\mathrm{d}\omega = \lim_{R\to\infty}\frac{1}{2\pi}\int_{\mathcal{C}_ {1}\cup\mathcal{C}_ {+}}\tilde{g}(\omega)e^{i\omega t}\mathrm{d}\omega,$$ and similarly for $t < 0$ and $\mathcal{C}_ {1}\cup\mathcal{C}_ {-}$.  
* We can therefore consider the closed integration contours $\mathcal{C}_ {1}\cup\mathcal{C}_ {+}$ and $\mathcal{C}_ {1}\cup\mathcal{C}_ {-}$.
* The singularities of $\tilde{g}(\omega)$ are when $$\omega^{2}-2i\omega - 5 = 0\Leftrightarrow \omega = i\pm 2,$$ so residues are $$\text{Res}(i+2) = \frac{1}{2\pi}\frac{2e^{i(i+2)t}}{2i-2(i+2)} = \frac{1}{4\pi}e^{-t}e^{-2it},$$ and $$\text{Res}(i-2) = \frac{-1}{4\pi}e^{-t}e^{2it}.$$
* For $t > 0$, we can use ***Cauchy's Theorem*** to deform the contour of integration to around the singularities, and using Residue's Theorem gives for $t > 0$, $$g(t) = 2\pi i\left(\frac{1}{4\pi}e^{-t}e^{-2it}-\frac{1}{4\pi}e^{-t}e^{2it}\right) = e^{-t}\sin(2t).$$
* For $t < 0$, we get $g(t) = 2\pi i(0) = 0$. Hence, $$g(t) = 1_{t > 0}e^{-t}\sin(2t).$$

We can check this by using ***Fourier Transform***: $$\tilde{g}(\omega) = \int_{-\infty}^{\infty}1_{t > 0}e^{-t}\sin(2t)e^{-i\omega t}\mathrm{d}t = \frac{\frac{1}{2}}{\omega - (i-2)} - \frac{\frac{1}{2}}{\omega - (i+2)}.$$

### Fourier Transforms

#### Definition of Fourier transform and inverse Fourier transform

* The ***Fourier transform*** of a function $f(t)$ is $$\tilde{f}(\omega) = (\mathcal{F}f)(\omega) = \int_{-\infty}^{\infty}f(t)e^{-i\omega t}\mathrm{d}t.$$
* The ***Inverse Fourier transform*** of a function $\tilde{f}(\omega)$ is $$f(t) = (\mathcal{F}^{-1}\tilde{f})(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty}\tilde{f}(\omega)e^{i\omega t}\mathrm{d}t.$$

#### Properties of Fourier transforms

* ***Linearity***: If $h(t) = af(t)+bg(t)$, then $\tilde{h}(\omega) = a\tilde{f}(\omega)+b\tilde{g}(\omega)$.
* ***Shift property***(I): If $g(t) = f(t-a)$, then $\tilde{g}(\omega) = e^{-i\omega a}\tilde{f}(\omega)$.
* ***Shift property***(II): If $g(t) = e^{i\Omega t}f(t)$, then $\tilde{g}(\omega) = \tilde{f}(\omega - \Omega)$.
* ***Scaling***: If $g(t) = f(at)$, then $\tilde{g}(\omega) = \frac{1}{|a|}\tilde{f}(\omega/a)$.
* ***Differentiation***: If $g(t) = f'(t)$, then $\tilde{g}(\omega) = i\omega\tilde{f}(\omega)$.
* ***Product***: If $g(t) = tf(t)$, then $\tilde{g}(\omega) = i\tilde{f}'(\omega)$.

#### Example with ODE

Consider $$\frac{\mathrm{d}^{2}y}{\mathrm{d}t^{2}}+\frac{\mathrm{d}y}{\mathrm{d}t}+ty = 0,\quad y(0) = 1\quad\text{and}\quad\lim_{t\to-\infty}y(t) = 0.$$

* Using Fourier transformation with the properties, $$(i\omega)^{2}\tilde{y}+i\omega\tilde{y}+i\frac{\mathrm{d}}{\mathrm{d}\omega}\tilde{y} = 0\implies \tilde{y} = Ae^{-\omega^{2}/2-i\omega^{3}/3}.$$
* Hence, by inversing Fourier transform, $$y(t) = \frac{A}{2\pi}\int_{-\infty}^{\infty}e^{-\omega^{2}/2-i\omega^{3}/3+i\omega t}\mathrm{d}\omega,$$ where we choose $A$ so that $y(0) = 1$. 
* In fact, we needed $y\to 0$ as $t\to-\infty$ for the Fourier transform $\tilde{y}$ to exist.

#### Convolution

* Given $f(t)$ and $g(t)$, we define the ***convolution*** $h = f* g$ by $$h(t) = \int_{-\infty}^{\infty}f(\tau)g(t-\tau)\mathrm{d}\tau = \int_{-\infty}^{\infty}f(t-\tau)g(\tau)\mathrm{d}\tau.$$
* So, $$\tilde{h}(\omega) = \tilde{f}(\omega)\tilde{g}(\omega).$$

#### Parseval's theorem

Given two functions $f(t)$ and $g(t)$, and using $\overline{x+iy} = x-iy$ to denote the complex conjugate, then $$\frac{1}{2\pi}\int_{-\infty}^{\infty}\tilde{f}(\omega)\overline{\tilde{g}(\omega)} = \int_{-\infty}^{\infty}f(t)\overline{g(t)}\mathrm{d}t.$$

* This is ***Parseval's theorem***. In particular, if $f(t) = g(t)$, then $$\frac{1}{2\pi}\int_{-\infty}^{\infty}|\tilde{f}(\omega)|^{2}\mathrm{d}\omega = \int_{-\infty}^{\infty}|f(t)|^{2}\mathrm{d}t,$$ which is known as ***Plancherel's theorem***.

### Laplace Transforms

One limitation of Fourier transforms is that they only exist for functions $f:\mathbb{R}\to\mathbb{C}$ and what about $f:[a,\infty)\to\mathbb{C}$?

* Extending $f:[0,\infty]\to\mathbb{C}$ to $g:\mathbb{R}\to\mathbb{C}$ by setting $$g(t) = f(t)\quad t\geq 0,$$ and $$g(t) = 0\quad t < 0.$$
* This is called ***zero-extending***.

#### Definition of Laplace Transform and Inverse Laplace Transform

* The ***Laplace Transform*** is given by $$\hat{f}(s) = \int_{0}^{\infty}f(t)e^{-st}\mathrm{d}t.$$
* The ***Inverse Laplace Transform*** of a function $f(t)$ is given by $$f(t) = \frac{1}{2\pi i}\int_{-i\infty+\alpha}^{i\infty+\alpha}\hat{f}(s)e^{st}\mathrm{d}s,$$ with $\alpha > \text{Re}(s_{j})$ for all singularities $s_{j}$ of $\hat{f}(s)$.

#### Some really important and useful Laplace Transforms

* For $f(t) = 1$, provided $\text{Re}(s) > 0$, $$\hat{f}(s) = \int_{0}^{\infty}e^{-st}\mathrm{d}t = \frac{1}{s}.$$
* For $f(t) = e^{at}$, provided $\text{Re}(s) > \text{Re}(a)$, $$\hat{f}(s) = \int_{0}^{\infty}e^{at}e^{-st}\mathrm{d}t = \frac{1}{s-a}.$$
* For $f(t) = \cos(at)$, provided $\text{Re}(s) > |\text{Im}(a)|$, $$f(t) = \frac{1}{2}(e^{iat}+e^{-iat}\implies\hat{f}(s) = \frac{s}{s^{2}+a^{2}}.$$
* For $f(t) = \sin(at)$, provided $\text{Re}(s) > |\text{Im}(a)|$, $$f(t) = \frac{1}{2i}(e^{iat}-e^{-iat})\implies\hat{f}(s) = \frac{a}{s^{2}+a^{2}}.$$
* For $f(t) = t^{n}$, provided $\text{Re}(s) > 0$, $$\hat{f}(s) = \int_{0}^{\infty}t^{n}e^{-st}\mathrm{d}t = \frac{\Gamma(n+1)}{s^{n+1}}.$$
* For $f(t) = e^{t^{2}}$, then $\hat{f}(s)$ doesn't exist for any $s$.

#### Properties of Laplace transforms

* ***Linearity***: If $h(t) = af(t)+bg(t)$, then $\hat{s} = a\hat{f}(s)+b\hat{g}(s).$
* ***Shift property***(I): If $g(t) = f(t-a)$, then $\hat{g}(s) = e^{-sa}\hat{f}(s)$. (Have to zero extend first)
* ***Shift property***(II): If $g(t) = e^{at}f(t)$, then $\hat{g}(s) = \hat{f}(s-a).$
* ***Scaling***: If $g(t) = f(at)$, then $\hat{g}(s) = \frac{1}{a}\hat{f}(s/a)$.
* ***Product***: If $g(t) = tf(t)$, then $\hat{g}(s) = -\frac{\mathrm{d}\hat{f}}{\mathrm{d}s}(s)$.
* ***Differentiation1***: If $g(t) = \frac{\mathrm{d}f}{\mathrm{d}t}(t) = \dot{f}(t)$, then $\hat{g}(s) = -f(0) + s\hat{f}(s)$.
* ***Differentiation2***: If $g(t) = \ddot{f}(t)$, then $\hat{g}(s) = -\dot{f}(0) - sf(0) + s^{2}\hat{f}(s)$.

#### Example with ODE

Consider $$\frac{\mathrm{d}^{2}y}{\mathrm{d}t^{2}}+\frac{\mathrm{d}y}{\mathrm{d}t} - 2y = e^{-2t}\quad\text{with}\quad y(0) = 1,\dot{y}(0) = 0.$$

* Try the Laplace transform: $$-\dot{y}(0) - sy(0) + s^{2}\hat{y}-y(0) + s\hat{y} - 2\hat{y} = \frac{1}{s+2}\implies\hat{y} = \frac{1}{9}\left(\frac{1}{s-1}-\frac{1}{s+2}-\frac{3}{(s+2)^{2}}\right)+\frac{1}{3}\left(\frac{2}{s-1}+\frac{1}{s+2}\right).$$
* Hence by ***Inverse Laplace Transform***, $$y = \frac{1}{9}\left(e^{t}-e^{-2t}-3te^{-2t}\right)+\frac{1}{3}\left(2e^{t}+e^{-2t}\right) = \frac{1}{9}\left(7e^{t}+(2-3t)e^{-2t}\right).$$

#### Convolution

* If $f(t) = g(t) = 0$ for $t < 0$, then $$h(t) = (f* g)(t) = \int_{-\infty}^{\infty}f(\tau)g(t-\tau)\mathrm{d}\tau = \int_{0}^{t}f(\tau)g(t-\tau)\mathrm{d}\tau,$$ and the Laplace transforming gives $$\hat{h}(s)  = \hat{f}(s)\hat{g}(s).$$
***Note***: $f(t)$ here do not have to be $f(t)$, it can also be $\dot{f}(t)$. E.g. Suppose we want to find $f(t)$ for $t > 0$ which solves $$f(t) = a\sin t+2\int_{0}^{t}\dot{f}(\tau)\sin(t-\tau)\mathrm{d}\tau,$$ subject to $f(0) = 0$.
* The integral here is a convolution, $\dot{f}* \sin t$, and the limits suggest a Laplace transform: $$\hat{f}(s) = \frac{a}{s^{2}+1}+2\left(-f(0)+s\hat{f}\right)\frac{1}{s^{2}+1}\implies\hat{f} = \frac{a}{(s-1)^{2}}\implies f(t) = ate^{t}.$$

#### Solving PDEs

For $x > 0$ and $t > 0$, solve the PDE $$x\frac{\partial u}{\partial t}+\frac{\partial u}{\partial x} = x\quad\text{with}\quad u(x,0) = u(0,t) = 0.$$

* Laplace transform $t\mapsto s$: $$x(-u(x,0) + s\hat{u}(x,s)) + \frac{\partial\hat{u}}{\partial x} = \frac{x}{s},\quad\text{with}\quad\hat{u}(0,s) = 0.$$

#### Limits

For $\hat{f}(s) = \int_{0}^{\infty}f(t)e^{-st}\mathrm{d}t$, look at $s\to\infty$ by using Watson's Lemma.

#### Summary of Fourier and Laplace transform

<img width = 100% height = 100% src = https://github.com/Louisli0515/MA269-Asymptotics-and-Integral-Transforms-Revision/assets/128298224/1922b6f0-8317-4a59-9a3a-4bc84a80625c>


