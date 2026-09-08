Linear Algebra Done Right - Chapter 6 Inner Product Spaces <br>
6A Inner Products and Norms
================
Rosie Sun <br>
2026-05-15


### 6.1 Definition: dot product
For $x, y \in R^n$, the dot product of $x$ and $y$, denoted by $x \dot y$, is defined by 

$$x \dot y = x_1 y_1 + ... + x_n y_n$$

where $x = (x_1,...,x_n)$ and $y = (y_1, ..., y_n)$.


### 6.2 Definition: inner product
An inner product on $V$ is a function that takes each ordered pair $(u,v)$ of elements of $V$ to a number $\langle u,v \rangle \in F$ and has the following properties:

- positivity: $\langle v,v \rangle \geq 0$ for all $v \in V$.
- definiteness: $\langle v,v \rangle=0$ if and only if $v=0$.
- additivity in the first slot: $\langle u+v,w \rangle = \langle u,w \rangle + \langle v,w \rangle$ for all $u,v,w \in V$.
- homogeneity in first slot: $\langle \lambda u, v \rangle = \lambda \langle u,v \rangle$ for all $\lambda in F$ and all $u,v \in V$.
- conjugate symmetry: $\langle u,v \rangle = \overline{\langle v,u \rangle}$ for all $u,v \in V$.


### 6.4 Definition: inner product space
An inner product space is a vector space $V$ along with an inner product on $V$.


### 6.6
- For each fixed $v \in V$, the function that takes $u \in V$ to $\langle u,v \rangle$ is a linear map from $V$ to $F$.
- $\langle 0,v \rangle = 0$ for every $v \in V$.
- $\langle v,0 \rangle = 0$ for every $v \in V$.
- $\langle u, v+w \rangle = \langle u,v \rangle + \langle u,w \rangle$ for all $u,v,w \in V$.
- $\langle u, \lambda v \rangle = \overline{\lambda} \langle u, v \rangle$ for all $\lambda \in F$ and all $u, v \in V$.


### 6.7 Definition: norm
For $v \in V$, the norm of $v$, denoted by $\lVert v \rVert$, is defined by $\lVert v \rVert = \sqrt{\langle v,v \rangle}$.


### 6.8
Suppose $v \in V$.

- $\lVert v \rVert=0$ if and only if $v=0$.
- $\lVert \lambda v \rVert = |\lambda| \lVert v \rVert$ for all $\lambda \in F$.


### 6.10 Definition: orthogonal
Two vectors $u, v \in V$ are called orthogonal if $\langle u,v \rangle=0$.


### 6.11
- 0 is orthogonal to every vector in $V$.
- 0 is the only vector in $V$ that is orthogonal to itself.


### 6.12 Pythagorean theorem
Suppose $u,v \in V$. If $u$ and $v$ are orthogonal, then $\lVert u+v \rVert^2 = \lVert u \rVert^2 + \lVert v \rVert^2$.

Proof: 

Suppose $\langle u,v \rangle=0$. Then 

$$\lVert u+v \rVert^2 = \langle u+v, u+v \rangle = \langle u,u \rangle + \langle u,v \rangle + \langle v,u \rangle + \langle v,v \rangle = \lVert u \rVert^2 + \lVert v \rVert^2$$


### 6.13
Suppose $u,v \in V$, with $v \neq 0$. Set 

$$c = \frac{\langle u,v \rangle}{\lVert v \rVert^2}$$ 

and 

$$w = u - \frac{\langle u,v \rangle}{\lVert v \rVert^2} v.$$ 

Then $u = cv + w$ and $\langle w,v \rangle=0$.


### 6.14 Cauchy-Schwartz inequality
Suppose $u,v \in V$. Then $|\langle u,v \rangle| \leq \lVert u \rVert \lVert v \rVert$. This inequality is an equality if and only if one of $u, v$ is a scalar multiple of the other.

Proof: 

If $v = 0$, then both sides of the desired inequality equal 0. Thus we can assume that $v \neq 0$. Consider the orthogonal decomposition 

$$u = \frac{\langle u,v \rangle}{\lVert v \rVert^2} v + w$$

where $w$ is orthogonal to $v$. By the Pythagorean theorem,

$$
\begin{aligned}
\lVert u \rVert^2 
    &= \lVert \frac{\langle u,v \rangle}{ \rVert v \lVert ^2} v \rVert^2 + \lVert w \rVert^2 \\
    &= \frac{|\langle u,v \rangle|^2}{\lVert v \rVert^2} + \lVert w \rVert^2 \\
    &\geq \frac{|\langle u,v \rangle|^2}{\lVert v \rVert^2}
\end{aligned}
$$

Multiplying both sides of this inequality by $\lVert v \rVert^2$ and then taking square roots gives the desired inequality.

The proof above shows that the Cauchy-Schwartz inequality is an equality if and only if $w = 0$. But $w = 0$ if and only if $u$ is a multiple of $v$. Thus the Cauchy-Schwartz inequality is an equality if and only if $u$ is a scalar multiple of $v$ or $v$ is a scalar multiple of $u$.


### 6.17 Triangule inequality
Suppose $u,v \in V$. Then $\lVert u+v \rVert \leq \lVert u \rVert + \lVert v \rVert$. This inequality is an equality if and only if one of $u, v$ is a nonnegative real multiple of the other.

Proof: 

We have

$$
\begin{aligned}
\lVert u+v \rVert^2 &= \langle u+v, u+v \rangle \\
    &= \langle u,u \rangle + \langle v,v \rangle + \langle u,v \rangle + \langle v,u \rangle \\
    &= \langle u,u \rangle + \langle v,v \rangle + \langle u,v \rangle + \overline{\langle u,v \rangle} \\
    &= \lVert u \rVert^2 + \lVert v \rVert^2 + \langle u,v \rangle + \overline{\langle u,v \rangle} \\
    &= \lVert u \rVert^2 + \lVert v \rVert^2 + 2 Re(\langle u,v \rangle) \\
    &\leq \lVert u \rVert^2 + \lVert v \rVert^2 + 2 |\langle u,v \rangle| \\
    &\leq \lVert u \rVert^2 + \lVert v \rVert^2 + 2 \lVert u \rVert \lVert v \rVert \\
    &= (\lVert u \rVert + \lVert v \rVert)^2
\end{aligned}
$$

where the second inequality follows from the Cauchy-Schwartz inequality. Taking square roots of both sides of the inequality above gives the desired inequality.


### 6.21 Parallelogram equality
Suppose $u, v \in V$. Then 

$$\lVert u+v \rVert^2 + \lVert u-v \rVert^2 = 2 (\lVert u \rVert^2 + \lVert v \rVert^2).$$




## Exercises
### (1) Prove or give a counterexample: If $v_1,...,v_m \in V$, then $\sum^m_{j=1} \sum^m_{k=1} \langle v_j,v_k \rangle \geq 0$.
Note that 

$$\sum^m_{j=1} \sum^m_{k=1} \langle v_j,v_k \rangle = \langle v_1+...+v_m, v_1+...v_m \rangle \geq 0$$

from the bilinearity of the inner product.



### (2) Suppose $S \in L(V)$. Define $\langle .,. \rangle_1$ by $\langle u,v \rangle_1 = \langle Su,Sv \rangle$ for all $u,v \in V$. Show that $\langle .,. \rangle_1$ is an inner product on $V$ if and only if $S$ is injective.
$\Rightarrow$
Suppose $\langle .,. \rangle_1$ is an inner product. 

Assume towards contradiction that $S$ is not injective. Then $null S \neq \\{0\\}$, and there exists some $v \in V, v \neq 0$ such that $Sv = 0$. We have $\langle v,v \rangle_1 = \langle Sv, Sv \rangle = \langle 0,0 \rangle = 0$. This violates the definiteness of the inner product, hence a contradiction.

$\Leftarrow$
Suppose $S$ is injective. 

We verify each property in the inner product definition 6.2

Positivity: $\langle v,v \rangle_1 = \langle Sv, Sv \rangle \geq 0$ for all $v \in V$, by the property of the inner product.

Definiteness: $\langle v,v \rangle_1 = \langle Sv,Sv \rangle = 0$ if and only if $Sv=0$. By the injectivity of $S$, $v=0$. 

Additivity in the first slot satisfied by the linearity of $S$: 

$$\langle u+v, w \rangle_1 = \langle S(u+v), Sw \rangle = \langle Su + Sv, Sw \rangle = \langle Su,Sw \rangle + \langle Sv,Sw \rangle = \langle u,w \rangle_1 + \langle v,w \rangle_1$$

for all $u,v,w \in V$.

Homogeneity in the first slot satisfied by the homogeneity of $S$:

$$\langle \lambda u, v \rangle_1 = \langle S(\lambda u), Sv \rangle = \langle \lambda Su, Sv \rangle = \lambda \langle Su, Sv \rangle = \lambda \langle u,v \rangle_1$$

for all $\lambda \in F, u,v \in V$.

Conjugate symmetry satisfied from the property of the inner product: 

$$\langle u,v \rangle_1 = \langle Su,Sv \rangle = \overline{\langle Sv,Su \rangle} = \overline{\langle v,u \rangle_1}$$

for all $u,v \in V$.



### (3)
#### (a) Show that the function taking an ordered pair $(x_1,x_2), (y_1,y_2)$ of elements of $R^2$ to $|x_1 y_1| + |x_2 y_2|$ is not an inner product of $R^2$.

The function violates the additivity in the first slot. Suppose $(x_1,x_2), (y_1,y_2), (z_1,z_2) \in R^2$. 

$$\langle (x_1 + y_1, x_2 + y_2), (z_1, z_2) \rangle = |(x_1 + y_1)z_1| + |(x_2 + y_2)z_2|$$

which is less than or equal to

$$\langle (x_1, x_2), (z_1, z_2) \rangle + \langle (y_1,y_2), (z_1,z_2) \rangle = |x_1 z_1| + |x_2 z_2| + |y_1 z_1| + |y_2 z_2|$$

by the triangle inequality on absolute values.


#### (b) Show that the function taking an ordered pair $(x_1,x_2,x_3), (y_1,y_2,y_3)$ of elements of $R^3$ to $x_1 y_1 + x_3 y_3$ is not an inner product on $R^3$.

The function violates definiteness. $\langle (0,1,0), (0,1,0) \rangle = 0$ but $(0,1,0) \neq 0$.



### (4) Suppose $T \in L(V)$ is such that $\lVert Tv \rVert \leq \lVert v \rVert$ for every $v \in V$. Prove that $T - \sqrt{2} I$ is injective.

Assume towards contradiction that $T-\sqrt{2} I$ is not injective. 

Then $null (T-\sqrt{2} I) \neq \\{0\\}$, and $(T-\sqrt{2}I)v = 0$ for some $v \neq 0, v \in V$. We have $Tv = \sqrt{2} v$. $\lVert Tv \rVert = \lVert  \sqrt{2} v \rVert = \sqrt{2} \lVert v \rVert$. However, by hypothesis, $\lVert Tv \rVert \leq \lVert v \rVert$, which is a contradiction. 

Therefore we conclude $T - \sqrt{2} I$ is injective.



### (5) Suppose $V$ is a real inner product space. 

#### (a) Show that $\langle u+v, u-v \rangle = \lVert u \rVert^2 - \lVert v \rVert^2$ for every $u,v \in V$.

$$
\begin{aligned}
\langle u+v,u-v \rangle 
    &= \langle u,u-v \rangle + \langle v,u-v \rangle \\
    &= \langle u,u \rangle - \langle u,v \rangle + \langle v,u \rangle - \langle v,v \rangle \\
    &= \langle u,u \rangle - \langle u,v \rangle + \overline{\langle u,v \rangle} - \langle v,v \rangle \\
    &= \lVert u \rVert^2 - \lVert v \rVert^2
\end{aligned}
$$


#### (b) Show that $u,v \in V$ have the same norm, then $u+v$ is orthogonal to $u-v$.

From (a), if $\lVert u \rVert=\lVert v \rVert$, then $\langle u+v, u-v \rangle = 0$.


#### (c) Use (b) to show that the diagonals of a rhombus are perpendicular to each other.

The diagonals of the rhombus are $u+v, u-v$, with $\lVert u \rVert=\lVert v \rVert$. Therefore by (b), the diagonals are perpendicular to each other.



### (6) Suppose $u,v \in V$. Prove that $\langle u,v \rangle=0 \iff \lVert u \rVert \leq \lVert u+av \rVert$ for all $a \in F$.
$\Rightarrow$
Suppose $\langle u,v \rangle=0$. 

Then $\langle u,av \rangle=\overline{a}\langle u,v \rangle=0$. By the Pythagorean theorem, $\lVert u+av \rVert^2 = \lVert u \rVert^2 + \lVert av \rVert^2$. Thus $\lVert u \rVert^2 \leq \lVert u + av \rVert^2$. Taking square root, we have the desired inequality.

$\Leftarrow$
Suppose $\lVert u \rVert \leq \lVert u+av \rVert$ for all $a \in F$. 

Then $\lVert u \rVert^2 \leq \lVert u+av \rVert^2$.

$$\lVert u+av \rVert^2 = \langle u+av,u+av \rangle = \lVert u \rVert^2 + \overline{a}\langle u,v \rangle + a \overline{\langle u,v \rangle} + |a|^2 \lVert v \rVert^2$$

Let $\lambda = \langle u,v \rangle$.

$$0 \leq \overline{a} \lambda + a \overline{\lambda} + |a|^2 \lVert v \rVert^2$$

$$0 \leq 2 Re(a \overline{\lambda}) + |a|^2 \lVert v \rVert^2$$

Let $a = -t \lambda, t \in R, t  \rangle 0$. Note that $a \overline{\lambda} = -t |\lambda|^2$ which is real. Then the equation above becomes

$$0 \leq -2 t |\lambda|^2 + t^2 |\lambda|^2 \lVert v \rVert^2$$

Dividing both sides by $t$,

$$0 \leq -2 |\lambda|^2 + t |\lambda|^2 \lVert v \rVert^2$$

For small $t$, $t \rightarrow 0^+$, we have $0 \leq -2 |\lambda|^2$, which forces $|\lambda|^2 = 0$. Thus $\lambda = \langle u,v \rangle=0$.



### (7) Suppose $u,v \in V$. Prove that $\lVert au + bv \rVert = \lVert bu + av \rVert$ for all $a,b \in R$ if and only if $\lVert u \rVert = \lVert v \rVert$.

$\Leftarrow$
Suppose $\lVert u \rVert=\lVert v \rVert = \lambda$. Then 

$$\lVert au + bv \rVert^2 = \langle au+bv, au+bv \rangle = a^2 \lVert u \rVert^2 + b^2 \lVert v \rVert^2 + 2ab Re(\langle u,v \rangle)$$

$$\lVert bu + av \rVert^2 = \langle bu+av, bu+av \rangle = b^2 \lVert u \rVert^2 + a^2 \lVert v \rVert^2 + 2ab Re(\langle u,v \rangle)$$

Since $\lVert au + bv \rVert^2 = \lVert bu + av \rVert^2$, $\lVert au + bv \rVert = \lVert bu + av \rVert$.

$\Rightarrow$
Suppose $\lVert au + bv \rVert = \lVert bu + av \rVert$. Then $\lVert au + bv \rVert^2 = \lVert bu + av \rVert^2$.

$$\lVert au + bv \rVert^2 - \lVert bu + av \rVert^2 = a^2 (\lVert u \rVert^2 - \lVert v \rVert^2) + b^2 (\lVert v \rVert^2 - \lVert u \rVert^2) = (a^2 - b^2) (\lVert u \rVert^2 - \lVert v \rVert^2)$$

Let $a=1, b=0$, then $a^2 - b^2 = 1 \neq 0$, so $\lVert u \rVert^2 - \lVert v \rVert^2$ must be 0.

Therefore $\lVert u \rVert^2 = \lVert v \rVert^2$, and $\lVert u \rVert = \lVert v \rVert$.



### (8) Suppose $a,b,c,x,y \in R$ and $a^2 + b^2 + c^2 + x^2 + y^2 \leq 1$. Prove that $a+b+c+4x+9y \leq 10$.

We have $\lVert (a,b,c,x,y) \rVert^2 \leq 1$. Then $\lVert (a,b,c,x,y) \rVert \leq 1$.

$$
\begin{aligned}
a + b + c + 4x + 9y 
    &= \langle (a,b,c,x,y), (1,1,1,4,9) \rangle \\
    &\leq |\langle (a,b,c,x,y), (1,1,1,4,9) \rangle|
\end{aligned}
$$

By Cauchy-Schwartz inequality, 

$$
\begin{aligned}
|\langle (a,b,c,x,y),(1,1,1,4,9) \rangle| 
    &\leq \lVert (a,b,c,x,y) \rVert \lVert (1,1,1,4,9) \rVert \\
    &\leq 1 \sqrt{100} \\
    &= 10
\end{aligned}
$$

Thus $a+b+c+4x+9y \leq 10$.



### (9) Suppose $u,v \in V$ and $\lVert u \rVert= \lVert v \rVert = 1$ and $\langle u,v \rangle=1$. Prove that $u=v$.

$$
\begin{aligned}
\langle u-v, u-v \rangle 
    &= \langle u,u \rangle - \langle u,v \rangle - \langle v,u \rangle - \langle v,v \rangle \\
    &= \langle u,u \rangle + \langle u,v \rangle - \overline{\langle u,v \rangle} + \langle v,v \rangle \\
    &= 1-1-1+1 \\
    &=0
\end{aligned}
$$

Therefore $u-v=0$, and $u=v$.



### (10) Suppose $u,v \in V$ and $\lVert u \rVert \leq 1$ and $\lVert v \rVert \leq 1$. Prove that $\sqrt{1-\lVert u \rVert^2} \sqrt{1-\lVert v \rVert^2} \leq 1 - |\langle u,v \rangle|$.

Squaring both sides of the desired inequality, we have

$$(1-\lVert u \rVert^2)(1-\lVert v \rVert^2) \leq (1 - |\langle u,v \rangle|)^2$$

Note that 

$$(1 - \lVert u \rVert \lVert v \rVert)^2 \leq (1 - |\langle u,v \rangle|)^2$$

by Cauchy-Schwartz inequality.

We want to show

$$(1-\lVert u \rVert^2)(1-\lVert v \rVert^2) \leq (1 - \lVert u \rVert \lVert v \rVert)^2$$

Expanding LHS

$$(1-\lVert u \rVert^2)(1-\lVert v \rVert^2) = 1 - \lVert u \rVert^2 - \lVert v \rVert^2 + \lVert u \rVert^2 \lVert v \rVert^2$$

Expanding RHS

$$(1 - \lVert u \rVert \lVert v \rVert)^2 = 1 + \lVert u \rVert^2 \lVert v \rVert^2 - 2 \lVert u \rVert \lVert v \rVert$$

Subtracting $ \lVert u \rVert^2 \lVert v \rVert^2$,

We want to show 

$$1 - \lVert u \rVert^2 - \lVert v \rVert^2 \leq 1 - 2 \lVert u \rVert \lVert v \rVert$$

Rearranging, we have

$$\lVert u \rVert^2 + \lVert v \rVert^2 - 2 \lVert u \rVert \lVert v \rVert = (\lVert u \rVert-\lVert v \rVert)^2 \geq 0$$

which holds. Taking square root of both sides, we have the desired inequality.



### (11) Find vectors $u, v \in R^2$ such that $u$ is a scalar multiple of $(1,3)$, $v$ is orthogonal to $(1,3)$, and $(1,2)=u+v$.
By hypothesis, $u = a(1,3)$. 

Let $v=(x,y)$. $\langle (x,y), (1,3) \rangle = x+3y = 0$. $y = -1/3 x$.

$$u + v = (a, 3a) + (x, -1/3 x) = (1,2)$$

Solving the two equations, we have

$u = (7/10, 21/10), v = (3/10, -1/10)$.



### (12) Suppose $a, b, c, d$ are positive numbers.

#### (a) Prove that $(a+b+c+d)(\frac{1}{a} + \frac{1}{b} + \frac{1}{c} + \frac{1}{d}) \geq 16$.

$$
\begin{aligned}
|\langle (\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}), (\frac{1}{\sqrt{a}}, \frac{1}{\sqrt{b}}, \frac{1}{\sqrt{c}}, \frac{1}{\sqrt{d}}) \rangle|^2 
    &= (1+1+1+1)^2 \\
    &= 16
\end{aligned}
$$

$$\lVert (\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}) \rVert^2 = = a+b+c+d$$

$$\lVert (\sqrt{\frac{1}{a}}, \sqrt{\frac{1}{b}}, \sqrt{\frac{1}{c}}, \sqrt{\frac{1}{d}}) \rVert^2 = = \frac{1}{a} + \frac{1}{b} + \frac{1}{c} + \frac{1}{d}$$

By Cauchy-Schwartz inequality, 

$$16 \leq (a+b+c+d)(\frac{1}{a} + \frac{1}{b} + \frac{1}{c} + \frac{1}{d})$$


#### (b) For which numbers $a,b,c,d$ is the inequality above an equality?

Equality holds when one vector is a scalar multiple of the other. 

$$(\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}) = 1/\lambda (1/sqrt{a}, 1/sqrt{b}, 1/sqrt{c}, 1/sqrt{d})$$

Then $\sqrt{a}=\lambda / \sqrt{a}$, $a=\lambda$. Similarly, $b=c=d=\lambda$. 

Hence $a=b=c=d$.


### (13) Show that the square of an average is less than or equal to the average of the squares. More precisely, show that if $a_1,...,a_n \in R$, then the square of the average of $a_1,...,a_n$ is less than or equal to the average of $a_1^2,...,a_n^2$.

$$|\langle (1/n,...,1/n), (a_1,...,a_n) \rangle|^2 = (a_1 /n + ... + a_n /n)^2$$

$$\lVert (1/n, ..., 1/n) \rVert^2 = 1/n^2 + ... + 1/n^2 = 1/n$$

$$\lVert (a_1,...,a_n) \rVert^2 = a_1^2 + ... + a_n^2$$

By Cauchy-Schwartz inequality, 

$$(a_1 /n + ... + a_n /n)^2 \leq 1/n (a_1^2 + ... + a_n^2)$$


### (17) Prove that $(\sum_{k=1}^n a_k b_k)^2 \leq (\sum_{k=1}^n k a_k^2)(\sum_{k=1}^n b_k^2 / k)$ for all real numbers $a_1,...,a_n$ and $b_1,...,b_n$.

Consider 

$$u = (a_1, \sqrt{2} a_2, ..., \sqrt{n} a_n)$$

$$v = (b_1, \frac{b_2}{sqrt{2}}, ..., \frac{b_n}{sqrt{n}}$$

Then 

$$|\langle u,v \rangle|^2 = (\sum_{k=1}^n a_k b_k)^2$$

$$\lVert u \rVert^2 = \sum_{k=1}^n k a_k^2$$

$$\lVert v \rVert^2 = \sum_{k=1}^n b_k^2 / k$$

By the Cauchy-Schwartz inequality, we have $|\langle u, v \rangle|^2 \leq \lVert u \rVert^2 \lVert v \rVert^2$. Thus 

$$(\sum_{k=1}^n a_k b_k)^2 \leq (\sum_{k=1}^n k a_k^2)(\sum_{k=1}^n b_k^2 / k)$$



### (19) Suppose $v_1,...,v_n$ is a basis of $V$ and $T \in L(V)$. Prove that if $\lambda$ is an eigenvalue of $T$, then $|\lambda|^2 \leq \sum_{j=1}^n \sum_{k=1}^n |M(T)_{j,k}|^2$, where $M(T)_{kl}$ denotes the entry in row j, k of the matrix of $T$ with respect to the basis $v_1,...,v_n$.

