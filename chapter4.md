Linear Algebra Done Right - Chapter 4 <br>
Polynomials
================
Rosie Sun <br>
2026-04-19


### 4.1 Definition: real part, imaginary part
Suppose $z = a + bi$, where $a$ and $b$ are real numbers.

- The real part of $z$, denoted by $Re z$, is defined by $Re z = a$.
- The imaginary part of $z$, denoted by $Im z$, is defined by $Im z = b$.

Thus for every complex number $z$, we have 

$$z = Re z + (Im z) i.$$

### 4.2 Definition: complex conjugate, absolute value
Suppose $z \in C$.

- The complex conjugate of $z \in C$, denoted by $\overline{z}$, is defined by

$$\overline{z} = Re z - (Im z) i.$$

- The absolute value of a complex number $z$, denoted by $|a|$, is defined by

$$|z| = \sqrt{(Re z)^2 + (Im z)^2}.$$

### 4.4
Suppose $w, z \in C$. Then the following equalities and inequalities hold.

- sum of $z$ and $\overline{z}$
$z + \overline{z} = 2 Re z$.

- difference of $z$ and $\overline{z}$
$z - \overline{z} = 2 (Im z) i$.

- product of $z$ and $\overline{z}$
$z \overline{z} = |z|^2$.

- additivity and multiplicativity of complex conjugate
$\overline{w + z} = \overline{w} + \overline{z}$ and $\overline{wz} = \overline{w} \overline{z}$.

- double complex conjugate
$\overline{\overline{z}} = z$.

- real and imaginary parts are bounded by $|z|$
$|Re z| \leq |z|$ and $|Im z| \leq |z|$.

- absolute value of the complex conjugate
$|\overline{z}| = |z|$.

- multiplicativity of absolute value
$|wz| = |w||z|$.

- triangle inequality
$|w+z| \leq |w| + |z|$.

Proof:

To verify the triangle inequality, we have

$$
\begin{aligned}
|w+z|^2 &= (w + z)(\overline{w} + \overline{z}) \\
    &= w \overline{w} + z \overline{z} + w \overline{z} + z \overline{w} \\
    &= |w|^2 + |z|^2 + w \overline{z} + \overline{w \overline{z}} \\
    &= |w|^2 + |z|^2 + 2 Re (w \overline{z}) \\
    &\leq |w|^2 + |z|^2 + 2 |w \overline{z}| \\
    &= |w|^2 + |z|^2 + 2|w||z| \\
    &= (|w| + |z|)^2
\end{aligned}
$$

Taking square roots now gives the desired inequality $|w+z|^2 \leq |w| + |z|$.


### 4.5 Definition: zero of a polynomial
A number $\lambda \in F$ is called a zero (or root) of a polynomial $p \in P(F)$ if 

$$p(\lambda)=0$$.


### 4.6
Suppose $m$ is a positive integer and $p \in P(F)$ is a polynomial of degree $m$. Suppose $\lambda \in F$. Then $p(\lambda)=0$ if and only if there exists a polynomial $q \in P(F)$ of degree $m-1$ such that 

$$p(z) = (z - \lambda) q(z)$$

for every $z \in F$.


### 4.8
Suppose $m$ is a positive integer and $p \in P(F)$ is a polynomial of degree $m$. Then $p$ has at most $m$ zeros in $F$.


### 4.9
Suppose that $p, s \in P(F)$, with $s \neq 0$. Then there exist unique polynomials $q, r \in P(F)$ such that 

$$p = sq + r$$

and $deg r < deg s$.


### 4.12
Every nonconstant polynomial with complex coefficients has a zero in $C$.


### 4.13
If $p \in P(C)$ is a nonconstant polynomial, then $p$ has a unique factorization of the form 

$$p(z) = c(z - \lambda_1) ... (z - \lambda_m)$$

where $c, \lambda_1,...,\lambda_m \in C$.


### 4.14
Suppose $p \in P(C)$ is a polynomial with real coefficients. If $\lambda \in C$ is a zero of $p$, then so is $\bar{\lambda}$.


### 4.15
Suppose $b, c \in R$. Then there is a polynomial factorization of the form 

$$x^2 + bx + c = (x - \lambda_1) (x - \lambda_2)$$

with $\lambda_1, \lambda_2 \in R$ if and only if $b^2 \geq 4c$.


### 4.16
Suppose $p \in P(R)$ is a nonconstant polynomial. Then $p$ has a unique factorization (except for the order of the factors) of the form

$$p(x) = c(x - \lambda_1) ... (x - \lambda_m) (x^2 + b_1 x + c_1) ... (x^2 + b_M x + c_M)$$

where $c, \lambda_1, ..., \lambda_m, b_1,...,b_M, c_1,...,c_M \in R$, with $b_k^2 < 4c_k$ for each $k$.


## Exercises

### (1) Suppose $w, z \in C$. Verify the following equalities and inequalities.

Suppose $z = a + bi$ and $w = c + di$.


#### (a) $z + \overline{z} = 2 Re z$

$$z + \overline{z} = (a + bi) + (a - bi) = 2a = 2 Re z$$

#### (b) $z - \overline{z} = 2 (Im z) i$

$$z - \overline{z} = (a + bi) - (a - bi) = 2 bi = 2 (Im z) i$$

#### (c) $z \overline{z} = |z|^2$

$$z \overline{z} = (a + bi) (a - bi) = a^2 - (bi)^2 = a^2 + b^2 = (Re z)^2 + (Im z)^2 = |z|^2$$

#### (d) $\overline{w + z} = \overline{w} + \overline{z}$ and $\overline{wz} = \overline{w} \overline{z}$

$$w + z = (c + di) + (a + bi) = (c+a) + (d+b)i$$

$$\overline{w + z} = (c+a) - (d+b)i = (c - di) + (a - bi) = \overline{w} + \overline{z}$$

$$wz = (c + di) (a + bi) = (ca - db) + (da + cb)i$$

$$\overline{wz} = (ca - db) - (da + cb)i = (c - di) (a - bi) = \overline{w} \overline{z}$$

#### (e) $\overline{\overline{z}} = z$

$$\overline{z} = a - bi = a + (-bi)$$

$$\overline{\overline{z}} = a - (-bi) = a+bi = z$$

#### (f) $|Re z| \leq |z|$ and $|Im z| \leq |z|$

$$|Re z|^2 = |a|^2 = a^2 \leq a^2 + b^2 = (Re z)^2 + (Im z)^2 = |z|^2$$

Taking square root of both sides, 

$$|Re z| \leq |z|.$$

Similarly, 

$$|Im z| \leq |z|.$$

#### (g) $|\overline{z}| = |z|$

$$|\overline{z}| = |a - bi| = \sqrt{a^2 + (-b)^2} = \sqrt{a^2 + b^2} = |z|$$

#### (h) $|wz| = |w| |z|$

$$wz = (c + di) (a + bi) = (ca - db) + (da + cb)i$$

$$|wz|^2 = (ca - db)^2 + (da + cb)^2 = c^2 a^2 + d^2 b^2 + d^2 a^2 + c^2 b^2 - 2cadb + 2dacb = c^2 (a^2 + b^2) + d^2 (a^2 + b^2) = (c^2 + d^2) (a^2 + b^2) = |w|^2 |z|^2$$

Taking square root of both sides,

$$|wz| = |w| |z|.$$


### (3) Suppose $V$ is a complex vector space and $\phi \in V'$. Define $\sigma: V \rightarrow R$ by $\sigma(v) = Re \phi(v)$ for each $v \in V$. Show that $\phi(v) = \sigma(v) - i \sigma(iv)$ for all $v \in V$.


### (4)

### (5)

### (7)

