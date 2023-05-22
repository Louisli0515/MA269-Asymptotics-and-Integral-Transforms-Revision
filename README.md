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
