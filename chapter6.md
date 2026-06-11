Linear Algebra Done Right - Chapter 6 <br>
Inner Product Spaces
================
Rosie Sun \langle br \rangle
2026-05-15


# 6A Inner Products and Norms

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
Suppose $u,v \in V$, with $v \neq 0$. Set $c = \frac{\langle u,v \rangle}{\lVert v \rVert^2}$ and $w = u - \frac{\langle u,v \rangle}{\lVert v \rVert^2} v$. Then $u = cv + w$ and $\langle w,v \rangle=0$.

### 6.14 Cauchy-Schwartz inequality
Suppose $u,v \in V$. Then $|\langle u,v \rangle| \leq \lVert u \rVert \lVert v \rVert$. This inequality is an equality if and only if one of $u, v$ is a scalar multiple of the other.

Proof: 

If $v = 0$, then both sides of the desired inequality equal 0. Thus we can assume that $v \neq 0$. Consider the orthogonal decomposition 

$$u = \frac{\langle u,v \rangle}{\lVert v \rVert^2} v + w$$

where $w$ is orthogonal to $v$. By the Pythagorean theorem,

$$\lVert u \rVert^2 = \lVert \frac{\langle u,v \rangle}{ \rVertv\lVert ^2} v \rVert^2 + \lVert w \rVert^2 = \frac{|\langle u,v \rangle|^2}{\lVert v \rVert^2} + \lVert w \rVert^2 \geq \frac{|\langle u,v \rangle|^2}{\lVert v \rVert^2}$$

Multiplying both sides of this inequality by $\lVert v \rVert^2$ and then taking square roots gives the desired inequality.

The proof above shows that the Cauchy-Schwartz inequality is an equality if and only if $w = 0$. But $w = 0$ if and only if $u$ is a multiple of $v$. Thus the Cauchy-Schwartz inequality is an equality if and only if $u$ is a scalar multiple of $v$ or $v$ is a scalar multiple of $u$.

### 6.17 Triangule inequality
Suppose $u,v \in V$. Then $\lVert u+v \rVert \leq \lVert u \rVert + \lVert v \rVert$. This inequality is an equality if and only if one of $u, v$ is a nonnegative real multiple of the other.

Proof: 

We have

$$\lVert u+v \rVert^2 = \langle u+v, u+v \rangle = \langle u,u \rangle + \langle v,v \rangle + \langle u,v \rangle + \langle v,u \rangle = \lVert u \rVert^2 + \lVert v \rVert^2 + \langle u,v \rangle + \overline{\langle u,v \rangle}$$

$$\lVert u \rVert^2 + \lVert v \rVert^2 + \langle u,v \rangle + \overline{\langle u,v \rangle} = \lVert u \rVert^2 + \lVert v \rVert^2 + 2 Re(\langle u,v \rangle) \leq \lVert u \rVert^2 + \lVert v \rVert^2 + 2 |\langle u,v \rangle| $$

by 4.4

$$\lVert u \rVert^2 + \lVert v \rVert^2 + 2 |\langle u,v \rangle|  \leq \lVert u \rVert^2 + \lVert v \rVert^2 + 2 \lVert u \rVert \lVert v \rVert = (\lVert u \rVert + \lVert v \rVert)^2$$

by Cauchy-Schwartz inequality.

Taking square roots of both sides of the inequality above gives the desired inequality.

### 6.21 Parallelogram equality
Suppose $u, v \in V$. Then $\lVert u+v \rVert^2 + \lVert u-v \rVert^2 = 2 (\lVert u \rVert^2 + \lVert v \rVert^2)$



## Exercises
#### (1) Prove or give a counterexample: If $v_1,...,v_m \in V$, then $\sum^m_{j=1} \sum^m_{k=1} \langle v_j,v_k \rangle \geq 0$.
Note that 

$$\sum^m_{j=1} \sum^m_{k=1} \langle v_j,v_k \rangle = \langle v_1+...+v_m, v_1+...v_m \rangle \geq 0$$

from the bilinearity of the inner product.


#### (2) Suppose $S \in L(V)$. Define $\langle .,. \rangle_1$ by $\langle u,v \rangle_1 = \langle Su,Sv \rangle$ for all $u,v \in V$. Show that $\langle .,. \rangle_1$ is an inner product on $V$ if and only if $S$ is injective.
$\Rightarrow$
Suppose $\langle .,. \rangle_1$ is an inner product. Assume towards contradiction that $S$ is not injective. Then $null S \neq \\{0\\}$, and there exists some $v \in V, v \neq 0$ such that $Sv = 0$. We have $\langle v,v \rangle_1 = \langle Sv, Sv \rangle = \langle 0,0 \rangle = 0$. This violates the definiteness of the inner product, hence a contradiction.

$\Leftarrow$
Suppose $S$ is injective. We verify each property in the inner product definition 6.2

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


#### (3)
(3a) Show that the function taking an ordered pair $(x_1,x_2), (y_1,y_2)$ of elements of $R^2$ to $|x_1 y_1| + |x_2 y_2|$ is not an inner product of $R^2$.

The function violates the additivity in the first slot. Suppose $(x_1,x_2), (y_1,y_2), (z_1,z_2) \in R^2$. 

$$\langle (x_1 + y_1, x_2 + y_2), (z_1, z_2) \rangle = |(x_1 + y_1)z_1| + |(x_2 + y_2)z_2|$$

which is less than or equal to

$$\langle (x_1, x_2), (z_1, z_2) \rangle + \langle (y_1,y_2), (z_1,z_2) \rangle = |x_1 z_1| + |x_2 z_2| + |y_1 z_1| + |y_2 z_2|$$

by the triangle inequality on absolute values.

(3b) Show that the function taking an ordered pair $(x_1,x_2,x_3), (y_1,y_2,y_3)$ of elements of $R^3$ to $x_1 y_1 + x_3 y_3$ is not an inner product on $R^3$.

The function violates definiteness. $\langle (0,1,0), (0,1,0) \rangle = 0$ but $(0,1,0) \neq 0$.


#### (4) Suppose $T \in L(V)$ is such that $\lVert Tv \rVert \leq \lVert v \rVert$ for every $v \in V$. Prove that $T - \sqrt{2} I$ is injective.
Assume towards contradiction that $T-\sqrt{2} I$ is not injective. Then $null (T-\sqrt{2} I) \neq \\{0\\}$, and $(T-\sqrt{2}I)v = 0$ for some $v \neq 0, v \in V$. We have $Tv = \sqrt{2} v$. $\lVert Tv \rVert = \lVert  \sqrt{2} v \rVert = \sqrt{2} \lVert v \rVert$. However, by hypothesis, $\lVert Tv \rVert \leq \lVert v \rVert$, which is a contradiction. Therefore we conclude $T - \sqrt{2} I$ is injective.


#### (5) Suppose $V$ is a real inner product space. 
(a) Show that $\langle u+v, u-v \rangle = \lVert u \rVert^2 - \lVert v \rVert^2$ for every $u,v \in V$.

$$\langle u+v,u-v \rangle = \langle u,u-v \rangle + \langle v,u-v \rangle = \langle u,u \rangle - \langle u,v \rangle + \langle v,u \rangle - \langle v,v \rangle = \langle u,u \rangle - \langle u,v \rangle + \overline{\langle u,v \rangle} - \langle v,v \rangle = \lVert u \rVert^2 - \lVert v \rVert^2$$

(b) Show that $u,v \in V$ have the same norm, then $u+v$ is orthogonal to $u-v$.

From (a), if $\lVert u \rVert=\lVert v \rVert$, then $\langle u+v, u-v \rangle = 0$.

(c) Use (b) to show that the diagonals of a rhombus are perpendicular to each other.

The diagonals of the rhombus are $u+v, u-v$, with $\lVert u \rVert=\lVert v \rVert$. Therefore by (b), the diagonals are perpendicular to each other.


#### (6) Suppose $u,v \in V$. Prove that $\langle u,v \rangle=0 \iff \lVert u \rVert \leq \lVert u+av \rVert$ for all $a \in F$.
$\Rightarrow$
Suppose $\langle u,v \rangle=0$. Then $\langle u,av \rangle=\overline{a}\langle u,v \rangle=0$. By the Pythagorean theorem, $\lVert u+av \rVert^2 = \lVert u \rVert^2 + \lVert av \rVert^2$. Thus $\lVert u \rVert^2 \leq \lVert u + av \rVert^2$. Taking square root, we have the desired inequality.

$\Leftarrow$
Suppose $\lVert u \rVert \leq \lVert u+av \rVert$ for all $a \in F$. Then $\lVert u \rVert^2 \leq \lVert u+av \rVert^2$.

$$\lVert u+av \rVert^2 = \langle u+av,u+av \rangle = \lVert u \rVert^2 + \overline{a}\langle u,v \rangle + a \overline{\langle u,v \rangle} + |a|^2 \lVert v \rVert^2$$

Let $\lambda = \langle u,v \rangle$.

$$0 \leq \overline{a} \lambda + a \overline{\lambda} + |a|^2 \lVert v \rVert^2$$

$$0 \leq 2 Re(a \overline{\lambda}) + |a|^2 \lVert v \rVert^2$$

Let $a = -t \lambda, t \in R, t  \rangle 0$. Note that $a \overline{\lambda} = -t |\lambda|^2$ which is real. Then the equation above becomes

$$0 \leq -2 t |\lambda|^2 + t^2 |\lambda|^2 \lVert v \rVert^2$$

Dividing both sides by $t$,

$$0 \leq -2 |\lambda|^2 + t |\lambda|^2 \lVert v \rVert^2$$

For small $t$, $t \rightarrow 0^+$, we have $0 \leq -2 |\lambda|^2$, which forces $|\lambda|^2 = 0$. Thus $\lambda = \langle u,v \rangle=0$.


#### (7) Suppose $u,v \in V$. Prove that $\lVert au + bv \rVert = \lVert bu + av \rVert$ for all $a,b \in R$ if and only if $\lVert u \rVert = \lVert v \rVert$.
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


#### (8) Suppose $a,b,c,x,y \in R$ and $a^2 + b^2 + c^2 + x^2 + y^2 \leq 1$. Prove that $a+b+c+4x+9y \leq 10$.
We have $\lVert (a,b,c,x,y) \rVert^2 \leq 1$. Then $\lVert (a,b,c,x,y) \rVert \leq 1$.

$$a + b + c + 4x + 9y = \langle (a,b,c,x,y),(1,1,1,4,9) \rangle \leq |\langle (a,b,c,x,y),(1,1,1,4,9) \rangle|$$

By Cauchy-Schwartz inequality, 

$$|\langle (a,b,c,x,y),(1,1,1,4,9) \rangle| \leq \lVert (a,b,c,x,y) \rVert \lVert (1,1,1,4,9) \rVert \leq 1 \sqrt{100} = 10$$

Thus $a+b+c+4x+9y \leq 10$.


#### (9) Suppose $u,v \in V$ and $\lVert u \rVert= \lVert v \rVert = 1$ and $\langle u,v \rangle=1$. Prove that $u=v$.
$$\langle u-v, u-v \rangle = \langle u,u \rangle - \langle u,v \rangle - \langle v,u \rangle - \langle v,v \rangle = \langle u,u \rangle + \langle u,v \rangle - \overline{\langle u,v \rangle} + \langle v,v \rangle = 1-1-1+1=0$$

Therefore $u-v=0$, and $u=v$.


#### (10) Suppose $u,v \in V$ and $\lVert u \rVert \leq 1$ and $\lVert v \rVert \leq 1$. Prove that $\sqrt{1-\lVert u \rVert^2} \sqrt{1-\lVert v \rVert^2} \leq 1 - |\langle u,v \rangle|$.
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


#### (11) Find vectors $u, v \in R^2$ such that $u$ is a scalar multiple of $(1,3)$, $v$ is orthogonal to $(1,3)$, and $(1,2)=u+v$.
By hypothesis, $u = a(1,3)$. 

Let $v=(x,y)$. $\langle (x,y), (1,3) \rangle = x+3y = 0$. $y = -1/3 x$.

$$u + v = (a, 3a) + (x, -1/3 x) = (1,2)$$

Solving the two equations, we have

$u = (7/10, 21/10), v = (3/10, -1/10)$.


#### (12) Suppose $a,b,c,d$ are positive numbers.
(a) Prove that $(a+b+c+d)(1/a + 1/b + 1/c + 1/d) \geq 16$.

$$|\langle (\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}), (1/sqrt{a}, 1/sqrt{b}, 1/sqrt{c}, 1/sqrt{d}) \rangle|^2 = (1+1+1+1)^2 = 16$$

$$\lVert (\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}) \rVert^2 = = a+b+c+d$$

$$\lVert (\sqrt{1/a}, \sqrt{1/b}, \sqrt{1/c}, \sqrt{1/d}) \rVert^2 = = 1/a + 1/b + 1/c + 1/d$$

By Cauchy-Schwartz inequality, 

$$16 \leq (a+b+c+d)(1/a + 1/b + 1/c + 1/d)$$

(b) For which numbers $a,b,c,d$ is the inequality above an equality?

Equality holds when one vector is a scalar multiple of the other. 

$$(\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}) = 1/\lambda (1/sqrt{a}, 1/sqrt{b}, 1/sqrt{c}, 1/sqrt{d})$$

Then $\sqrt{a}=\lambda / \sqrt{a}$, $a=\lambda$. Similarly, $b=c=d=\lambda$. 

Hence $a=b=c=d$.


#### (13) Show that the square of an average is less than or equal to the average of the squares. More precisely, show that if $a_1,...,a_n \in R$, then the square of the average of $a_1,...,a_n$ is less than or equal to the average of $a_1^2,...,a_n^2$.
$$|\langle (1/n,...,1/n), (a_1,...,a_n) \rangle|^2 = (a_1 /n + ... + a_n /n)^2$$

$$\lVert (1/n, ..., 1/n) \rVert^2 = 1/n^2 + ... + 1/n^2 = 1/n$$

$$\lVert (a_1,...,a_n) \rVert^2 = a_1^2 + ... + a_n^2$$

By Cauchy-Schwartz inequality, 

$$(a_1 /n + ... + a_n /n)^2 \leq 1/n (a_1^2 + ... + a_n^2)$$


#### (17) Prove that $(\sum_{k=1}^n a_k b_k)^2 \leq (\sum_{k=1}^n k a_k^2)(\sum_{k=1}^n b_k^2 / k)$ for all real numbers $a_1,...,a_n$ and $b_1,...,b_n$.
Consider 

$$u = (a_1, \sqrt{2} a_2, ..., \sqrt{n} a_n)$$

$$v = (b_1, \frac{b_2}{sqrt{2}}, ..., \frac{b_n}{sqrt{n}}$$

Then 

$$|\langle u,v \rangle|^2 = (\sum_{k=1}^n a_k b_k)^2$$

$$\lVert u \rVert^2 = \sum_{k=1}^n k a_k^2$$

$$\lVert v \rVert^2 = \sum_{k=1}^n b_k^2 / k$$

By the Cauchy-Schwartz inequality, we have $|\langle u, v \rangle|^2 \leq \lVert u \rVert^2 \lVert v \rVert^2$. Thus 

$$(\sum_{k=1}^n a_k b_k)^2 \leq (\sum_{k=1}^n k a_k^2)(\sum_{k=1}^n b_k^2 / k)$$


#### (19) Suppose $v_1,...,v_n$ is a basis of $V$ and $T \in L(V)$. Prove that if $\lambda$ is an eigenvalue of $T$, then $|\lambda|^2 \leq \sum_{j=1}^n \sum_{k=1}^n |M(T)_{j,k}|^2$, where $M(T)_{kl}$ denotes the entry in row j, k of the matrix of $T$ with respect to the basis $v_1,...,v_n$.





# 6B Orthonormal Bases

### 6.22 Definition: orthonormal
- A list of vectors is called orthonormal if each vector in the list has norm 1 and is orthogonal to all the other vectors in the list.
- In other words, a list $e_1,...,e_m$ of vectors in $V$ is orthonormal if $\langle e_j, e_k \rangle = 1$ if $j=k$, $\langle e_j, e_k \rangle=0$ if $j \neq k$, for all $j, k \in \\{1,...,m\\}$.

### 6.24
Suppose $e_1,...,e_m$ is an orthonormal list of vectors in $V$. Then 

$$\lVert a_1 e_1 + ... + a_m e_m \rVert^2 = |a_1|^2 + ... + |a_m|^2$$

for all $a_1,...,a_m \in F$.

### 6.25
Every orthonormal list of vectors is linearly independent.

Proof: Suppose $e_1,...,e_m$ is an orthonormal list of vectors in $V$ and $a_1,...,a_m \in F$ are such that $a_1 e_1 + ... + a_m e_m = 0$. Then $|a_1|^2 + ... + |a_m|^2 = 0$ by 6.24, which means that all the $a_k$'s are 0. Thus $e_1,...,e_m$ is linearly independent.

### 6.26 Bessel's inequality
Suppose $e_1,...,e_m$ is an orthonormal list of vectors in $V$. If $v \in V$ then 

$$|\langle v,e_1 \rangle|^2 + ... + |\langle v,e_m \rangle|^2 \leq \lVert v \rVert^2$$

Proof: Suppose $v \in V$. Then 

$$v = \langle v,e_1 \rangle e_1 + ... + \langle v,e_m \rangle e_m + v - \langle v,e_1 \rangle e_1 - ... - \langle v,e_m \rangle e_m$$

Let $u = \langle v,e_1 \rangle e_1 + ... + \langle v,e_m \rangle e_m$, $w = v - \langle v,e_1 \rangle e_1 - ... - \langle v,e_m \rangle e_m$.

If $k \in \\{1,...,m\\}$, then $\langle w,e_k \rangle = \langle v,e_k \rangle - \langle v,e_k \rangle \langle e_k, e_k \rangle = 0$. This implies that $\langle w, u \rangle = 0$. The Pythagorean theorem implies that 

$$\lVert v \rVert^2 = \lVert u \rVert^2 + \lVert w \rVert^2 \geq \lVert u \rVert^2 = |\langle v,e_1 \rangle|^2 + ... + |\langle v,e_m \rangle|^2$$

where the last equality comes from 6.24.

### 6.27 Definition: orthonormal basis
An orthonormal basis of $V$ is an orthonormal list of vectors in $V$ that is also a basis of $V$.

### 6.28
Suppose $V$ is finite-dimensional. Then every orthonormal list of vectors in $V$ of length $dim V$ is an orthonormal basis of $V$.

Proof: 

By 6.25, every orthonormal list of vectors in $V$ is linearly independent. Thus every such list of the right length is a basis by 2.38.

### 6.30
Suppose $e_1,...,e_n$ is an orthonormal basis of $V$ and $u,v \in V$. Then

- $v = \langle v, e_1 \ranglee_1 + ... \langle v,e_n \ranglee_n$
- $\lVert v \rVert^2 = |\langle v,e_1 \rangle|^2 + ... + |\langle v,e_n \rangle|^2$
- $\langle u,v \rangle = \langle u,e_1 \rangle\overline{\langle v,e_1 \rangle} + ... + \langle u,e_n \rangle\overline{\langle v,e_n \rangle}$

### 6.32 Gram-Schmidt procedure
Suppose $v_1,...,v_m$ is a linearly independent list of vectors in $V$. Let $f_1 = v_1$. For $k = 2,...,m$, define $f_k$ inductively by 

$$f_k = v_k - \frac{\langle v_k, f_1 \rangle}{\lVert f_1 \rVert^2} f_1 - ... - \frac{\langle v_k, f_{k-1} \rangle}{\lVert f_{k-1} \rVert^2} f_{k-1}$$

For each $k=1,...,m$, let $e_k = \frac{f_k}{\lVert f_k \rVert}$. Then $e_1,...,e_m$ is an orthonormal list of vectors in $V$ such that

$$span(v_1,...,v_k) = span(e_1,...,e_k)$$

for each $k=1,...,m$.

Proof: 

We will show by induction on $k$ that the desired conclusion holds.

To get started with $k=1$, note that because $e_1 = \frac{f_1}{\lVert f_1 \rVert}$, we have $\lVert e_1 \rVert=1$; also, $span(v_1) = span(e_1)$ because $e_1$ is a nonzero multiple of $v_1$.

Suppose $1 \langle  k \leq m$, and the list $e_1,...,e_{k-1}$ generated by the procedure is an orthonormal list such that 

$$span(v_1,...,v_{k-1}) = span(e_1,...,e_{k-1})$$

Because $v_1,...,v_m$ is linearly independent, we have $v_k \notin span(v_1,...,v_{k-1})$. Thus 

$$v_k \notin span(e_1,...,e_{k-1}) = span(f_1,...,f_{k-1})$$ 

which implies that $f_k \neq 0$. Hence we are not dividing by 0 in the definition of $e_k$. 

Dividing a vector by its norm produces a new vector with norm 1; thus $\lVert e_k \rVert = 1$.

Let $j \in \\{1,...,k-1\\}$. Then 

$$\langle e_k, e_j \rangle = \frac{1}{\lVert f_k \rVert \lVert f_j \rVert} \langle f_k, f_j \rangle $$

$$= \frac{1}{\lVert f_k \rVert \lVert f_j \rVert} \langle v_k - \frac{\langle v_k, f_1 \rangle}{\lVert f_1 \rVert^2} f_1 - ... - \frac{\langle v_k, f_{k-1} \rangle}{\lVert f_{k-1} \rVert^2} f_{k-1}, f_j \rangle$$

$$= \frac{1}{\lVert f_k \rVert \lVert f_j \rVert}  (\langle v_k, f_j \rangle - \langle \frac{\langle v_k, f_j \rangle}{\lVert f_j \rVert^2} f_j, f_j \rangle)$$

$$= \frac{1}{\lVert f_k \rVert \lVert f_j \rVert} (\langle v_k, f_j \rangle - \langle v_k, f_j \rangle) = 0$$

Thus $e_1,...,e_k$ is an orthonormal list.

From the definition of $e_k$, we see that $v_k \in span(e_1,...,e_k)$. Combining this information with the inductive hypothesis shows that 

$$span(v_1,...,v_k) \subseteq span(e_1,...,e_k)$$

Both lists above are linearly independent (the $v$'s by hypothesis, and the $e$'s by orthonormality and 6.25). Thus both subspaces above have dimension $k$, and hence they are equal, completing the induction step and thus completing the proof. 


### 6.35
Every finite-dimensional inner product space has an orthonormal basis.

### 6.36
Suppose $V$ is finite-dimensional. Then every orthonormal list of vectors in $V$ can be extended to an orthonormal basis of $V$.

### 6.37
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some orthonormal basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$.

### 6.38 Schur's theorem
Every operator on a finite-dimensional complex inner product space has an upper-triangular matrix with respect to some orthonormal basis.

### 6.42 Riesz representation theorem
Suppose $V$ is finite-dimensional and $\phi$ is a linear functional on $V$. Then there is a unique vector $v \in V$ such that 

$$\phi(u) = \langle u, v \rangle$$

for every $u \in V$.

Proof: 

First we show that there exists a vector $v \in V$ such that $\phi(u) = \langle u,v \rangle$ for every $u \in V$. 

Let $e_1,...,e_n$ be an orthonormal basis of $V$. Then 

$$\phi(u) = \phi(\langle u,e_1 \ranglee_1 + ... \langle u,e_n \ranglee_n) = \langle u,e_1 \rangle \phi(e_1) + ... + \langle u,e_n \rangle \phi(e_n) = \langle u, \overline{\phi(e_1)} e_1 + ... \overline{\phi(e_n)} e_n \rangle$$

for every $u \in V$, where the first equality comes from 6.30. 

Thus setting 

$$v = \overline{\phi(e_1)} e_1 + ... + \overline{\phi(e_n)} e_n$$

we have $\phi(u) = \langle u,v \rangle$ for every $u \in V$, as desired.

Now we prove that only one vector $v \in V$ has the desired behavior. 

Suppose $v_1,v_2 \in V$ are such that 

$$\phi(u) = \langle u, v_1 \rangle = \langle u, v_2 \rangle$$ 

for every $u \in V$. Then 

$$0 = \langle u, v_1 \rangle - \langle u, v_2 \rangle = \langle u, v_1-v_2 \rangle$$

for every $u \in V$. Taking $u = v_1 - v_2$ shows that $v_1 - v_2 = 0$. Thus $v_1 = v_2$, completing the proof of the uniqueness part of the result.


## Exercises

#### (1) Suppose $e_1,...,e_m$ is a list of vectors in $V$ such that $\lVert a_1 e_1 + ... + a_m e_m \rVert^2 = |a_1|^2 + ... + |a_m|^2$ for all $a_1,...,a_m \in F$. Show that $e_1,...,e_m$ is an orthonormal list.

First we want to show that the norms of each $e_i, i=1,...,m$ is 1.

Let $a_k=1$, $a_i = 0, i \neq k$. Then 

$$\lVert a_k e_k \rVert^2 = |a_k|^2 \lVert e_k \rVert^2 = |a_k|^2$$

Therefore $\lVert e_k \rVert = 1$. Since $k$ was arbitrary, all the $e_i, i=1,...,m$ has unit norm.

Next we want to show that the inner product of $e_k, e_l$ is 0 for $k \neq l$.

Let $a_k, a_l \in F$, $a_i = 0, i \neq k, i \neq l$. Then 

$$\lVert a_k e_k a_l e_l \rVert^2 = |a_k|^2 + |a_l|^2 + a_k \overline{a_l} \langle e_k, e_l \rangle + a_l \overline{a_k} \langle e_l, e_k \rangle = |a_k|^2 + |a_l|^2$$

Thus 

$$a_k \overline{a_l} \langle e_k, e_l \rangle + a_l \overline{a_k} \langle e_l, e_k \rangle = 0$$ 

for all $a_k, a_l \in F$.

Consider $a_k = a_l = 1$. Then 

$$\langle e_k, e_l \rangle + \langle e_l, e_k \rangle = \langle e_k, e_l \rangle + \overline{\langle e_k, e_l \rangle} = 2 Re(\langle e_k, e_l \rangle) = 0$$ 

Thus $Re(\langle e_k, e_l \rangle) = 0$.

Consider $a_k = i, a_l = 1$. Then

$$i \langle e_k, e_l \rangle + (-i) \overline{\langle e_k, e_l \rangle} = i (\langle e_k, e_l \rangle - \overline{\langle e_k,e_l \rangle}) = i 2Im(\langle e_k, e_l \rangle)$$

Thus $Im(\langle e_k, e_l \rangle) = 0$.

Therefore $\langle e_k, e_l \rangle = 0$ for $k \neq l$.


#### (2) 
(a) Suppose $\theta \in R$. Show that both $(cos \theta, sin \theta), (-sin \theta, cos \theta)$ and $(cos \theta, sin \theta), (sin \theta, -cos \theta)$ are orthonormal bases of $R^2$.

$$\lVert (cos\theta, sin\theta) \rVert^2 = cos^2 \theta + sin^2 \theta = 1$$

$$\lVert (-sin\theta, cos\theta) \rVert^2 = (-sin\theta)^2 + cos^2 \theta = 1$$

$$\langle (cos\theta, sin\theta), (-sin\theta, cos\theta) \rangle = - cos\theta sin\theta + sin\theta cos\theta = 0$$

Similarly,

$$\lVert (sin\theta, -cos\theta) \rVert^2 = sin^2\theta + (-cos \theta)^2 = 1$$

$$\langle (cos\theta, sin\theta), (sin\theta, -cos\theta) \rangle = cos\theta sin\theta - sin\theta cos\theta = 0$$

(b) Show that each orthonormal basis of $R^2$ is of the form given by one of the two possibilities in (a).

Let $e_1, e_2$ be an orthonormal basis of $R^2$. Suppose $e_1 = (x_1, y_1)$. Then $x_1^2 + y_1^2 = 1$, we can rewrite as $e_1 = (cos\theta, sin\theta)$. 

Suppose $e_2 = (x_2, y_2)$. Then $\langle e_1,e_2 \rangle = x_2 cos\theta + y_2 \sin\theta = 0$. So $x_2 = -sin\theta, y_2=cos\theta$ or $x_2 = sin\theta, y_2=-cos\theta$.


#### (3) Suppose $e_1,...,e_m$ is an orthonormal list in $V$ and $v \in V$. Prove that $\lVert v \rVert^2 = |\langle v,e_1 \rangle|^2 + ... + |\langle v,e_m \rangle|^2 \iff v \in span (e_1,...,e_m)$.
$\Rightarrow$
Suppose $\lVert v \rVert^2 = |\langle v,e_1 \rangle|^2 + ... + |\langle v,e_m \rangle|^2$.

Based on 6.26, we can decompose 

$$v = \langle v,e_1 \ranglee_1 + ... + \langle v,e_m \ranglee_m + v - \langle v,e_1 \ranglee_1 - ... - \langle v,e_m \ranglee_m$$

Let $u = \langle v,e_1 \ranglee_1 + ... + \langle v,e_m \ranglee_m$ and $w = v - \langle v,e_1 \ranglee_1 - ... - \langle v,e_m \ranglee_m$.

Then $\langle w,u \rangle = 0$. By the Pythagorean theorem, 

$$\lVert v \rVert^2 = \lVert u \rVert^2 + \lVert w \rVert^2$$

By 6.24, $\lVert u \rVert^2 = |\langle v,e_1 \rangle|^2 + ... + |\langle v,e_m \rangle|^2$.

By hypothesis, $\lVert v \rVert^2 = \lVert u \rVert^2$, which implies $\lVert w \rVert^2 = 0$. 

Thus $w = 0$, and we conclude 

$$v = \langle v,e_1 \ranglee_1 + ... + \langle v,e_m \ranglee_m \in span(e_1,...,e_m)$$

$\Leftarrow$
Suppose $v \in span(e_1,...,e_m)$. Then $v = a_1 e_1 + ... + a_m e_m$ for some $a_1,...,a_m$.

$$\lVert v \rVert^2 = \langle a_1 e_1 + ... + a_m e_m, a_1 e_1 + ... + a_m e_m \rangle = |a_1|^2 + ... + |a_m|^2$$

For $k=1,...,m$, $\langle v,e_k \rangle = a_k \langle e_k,e_k \rangle = a_k$. Therefore 

$$\lVert v \rVert^2 = |\langle v,e_1 \rangle|^2 + ... + |\langle v,e_m \rangle|^2$$


#### (4) Suppose $n$ is a positive integer. Prove ethat $1/\sqrt{2\pi}, cos x / sqrt{\pi}$


#### (6) Suppose $e_1,...,e_n$ is an orthonormal basis of $V$. 
(a) Prove that if $v_1,...,v_n$ are vectors in $V$ such that $\lVert e_k - v_k \rVert \langle  1/\sqrt{n}$ for each $k$, then $v_1,...,v_n$ is a basis of $V$.

Suppose $a_1 v_1 + ... + a_n v_n = 0$ for some $a_1,...,a_n \in F$. We can rewrite

$$a_1 (e_1 + v_1 - e_1) + ... + a_n (e_n + v_n - e_n) = 0$$

$$a_1 e_1 + ... + a_n e_n = - (a_1 (v_1-e_1) + ... + a_n(v_n-e_n))$$

Taking the norm of both sides,

$$\lVert a_1 e_1 + ... + a_n e_n \rVert^2 = |a_1|^2 + ... + |a_n|^2$$

$$\lVert a_1 (v_1-e_1) + ... + a_n (v_n-e_n) \rVert^2 \leq |a_1|^2 \lVert v_1-e_1 \rVert^2 + ... + |a_n|^2 \lVert v_n-e_n \rVert^2 \leq (|a_1|^2+...+|a_n|^2) (\lVert v_1-e_1 \rVert^2+...+\lVert v_n-e_n \rVert^2)$$

where the first inequality follows from the triangle inequality, and the second inequality follows from the Cauchy-Schwartz inequality.

$$(|a_1|^2+...+|a_n|^2) (\lVert v_1-e_1 \rVert^2+...+\lVert v_n-e_n \rVert^2) \langle  (|a_1|^2+...+|a_n|^2) (1/n+...+1/n) = (|a_1|^2+...+|a_n|^2)$$

$$\lVert a_1 (v_1-e_1) + ... + a_n (v_n-e_n) \rVert^2 \langle  |a_1|^2 + ... + |a_n|^2$$

which is a contradiction.

Therefore $|a_1|^2 + ... + |a_n|^2 = 0$, hence $a_1=...=a_n = 0$. We conclude $v_1,...,v_n$ is a linearly independent list of vectors of the right length, therefore it is a basis of $V$.


(b) Show that there exist $v_1,...,v_n \in V$ such that $\lVert e_k - v_k \rVert \leq 1/\sqrt{n}$ for each $k$, but $v_1,...,v_n$ is not linearly independent.


#### (18) Suppose $u_1,...,u_m$ is a linearly independent list in $V$. Show that there exists $v \in V$ such that $\langle u_k, v \rangle = 1$ for all $k \in \\{1,...,m\\}$.
Suppose $V$ is finite-dimensional. Since $u_1,...,u_m$ is a lineary independent list, we can extend it to a basis of $V$, $u_1,...,u_m, v_1,...,v_n$ by 2.32. 

Define a linear functional on $V$ such that $\phi(u_k) = 1, k=1,...,m$ and $\phi(v_j) = 0, j=1,...n$. This is well-defined by 3.4. 

By the Riesz representation theorem 6.42, there exists a unique $v \in V$ such that $\phi(u) = \langle u, v \rangle$ for all $u \in V$. 

Thus there exists $v \in V$ such that $\langle u_k, v \rangle = 1$ for $k=1,...,m$. 


#### (19) Suppose $v_1,...,v_n$ is a basis of $V$. Prove that there exists a basis $u_1,...,u_n$ of $V$ such that $\langle v_j, u_k \rangle = 0$ if $j \neq k$, and $\langle v_j, u_k \rangle = 1$ if $j = k$.
Define $n$ linear functionals on $V$ such that $\phi_k(v_j)=1$ if $k=j$, $\phi_k(v_j) = 0$ if $k \neq j$, for $k=1,...,n$. This is well-defined by 3.4.

By the Riesz representation theorem 6.42, there exists unique $u_k \in V$ such that $\phi_k(v)=\langle v, u_k \rangle$ for all $v \in V$, for $k=1,...,n$.

Since the length of the list $u_1,...,u_n$ is $n$, we need to show that $u_1,...,u_n$ is linearly independent. 

Suppose $a_1 u_1 + ... + a_n u_n = 0$ for some $a_1,...,a_n \in F$.

For each $j=1,...,n$, we have

$$0 = \langle v_j, a_1 u_1 + ... + a_n u_n \rangle = a_j \langle v_j, u_j \rangle = a_j \phi_j(v_j) = a_j$$

since the cross terms disappear. 

Thus $u_1,...,u_n$ is linearly independent, and we conclude it is a basis of $V$.


#### (22) Suppose $C[-1, 1]$ is the vector space of continuous real-valued functions on the interval [-1, 1] with inner product given by $\langle f,g \rangle = \int^1_{-1} fg$ for all $f,g \in C[-1,1]$. Let $\phi$ be the linear functional on $C[-1, 1]$ defined by $\phi(f) = f(0)$. Show that there does not exist $g \in C[-1, 1]$ such that $\phi(f) = \langle f,g \rangle$ for every $f \in C[-1, 1]$.
Assume towards contradiction that there exists $g \in C[-1, 1]$ such that $\phi(f) = \langle f,g \rangle$ for every $f \in C[-1, 1]$.

Consider the tent function, for some $0\langle  \epsilon \langle  1$, $f(x) = 1 - \frac{|x|}{\epsilon}$ for $|x| \langle = \epsilon$, $f(x) = 0$ for $|x|  \rangle \epsilon$.







# 6C Orthogonal Complements and Minimization Problems

### 6.46 Definition: orthogonal complement
If $U$ is a subset of $V$, then the orthogonal complement of $U$, denoted by $U^{\perp}$, is the set of all vectors in $V$ that are orthogonal to every vector in $U$:

$$U^{\perp} = \\{v \in V: \langle u,v \rangle=0 for every u \in U\\}$$

### 6.48
(a) If $U$ is a subset of $V$, then $U^{\perp}$ is a subspace of $V$.

(b) $\\{0\\}^{\perp} = V$.

(c) $V^{\perp} = \\{0\\}$.

(d) If $U$ is a subset of $V$, then $U \cap U^{\perp} \subseteq \\{0\\}$.

(e) If $G$ and $H$ are subsets of $V$ and $G \subseteq H$, then $H^{\perp} \subseteq G^{\perp}$.

Proof:

(a) Suppose $U$ is a subset of $V$. Then $\langle u, 0 \rangle = 0$ for every $u \in U$; thus $0 \in U^{\perp}$. 

Suppose $v, w \in U^{\perp}$. If $u \in U$, then 

$$\langle u, v+w \rangle = \langle u,v \rangle + \langle u,w \rangle = 0 + 0 = 0$$

Thus $v + w \in U^{\perp}$, which shows that $U^{\perp}$ is closed under addition.

Similarly, suppose $\lambda \in F$ and $v \in U^{\perp}$. If $u \in U$, then 

$$\langle u, \lambda v \rangle = \overline{\lambda} \langle u, v \rangle = \overline{\lambda} 0 = 0$$

Thus $\lambda v \in U^{\perp}$, which shows that $U^{\perp}$ is closed under scalar multiplication. 

Thus $U^{\perp}$ is a subspace of $V$.

(b) Suppose $v \in V$. Then $\langle 0, v \rangle = 0$, which implies that $v \in \\{0\\}^{\perp}$. Thus $\\{0\\}^{\perp} = V$.

(c) Suppose $v \in V^{\perp}$. Then $\langle v, v \rangle = 0$, which implies that $v = 0$. Thus $V^{\perp} = \\{0\\}$.

(d) Suppose $U$ is a subset of $V$ and $u \in U \cap U^{\perp}$. Then $\langle u, u \rangle = 0$, which implies that $u = 0$. Thus $U \cap U^{\perp} \subseteq \\{0\\}$. 

(e) Suppose $G$ and $H$ are subsets of $V$ and $G \subseteq H$. Suppose $v \in H^{\perp}$. Then $\langle u, v \rangle = 0$ for every $u \in H$, which implies that $\langle u, v \rangle = 0$ for every $u \in G$. Hence $v \in G^{\perp}$. Thus $H^{\perp} \subseteq G^{\perp}$.


### 6.49
Suppose $U$ is a finite-dimensional subspace of $V$. Then 

$$V = U \oplus U^{\perp}$$

Proof:

First we will show that $V = U + U^{\perp}$. To do this, suppose that $v \in V$. Let $e_1,...,e_m$ be an orthonormal basis of $U$. 

We want to write $v$ as the sum of a vector in $U$ and a vector orthogonal to $U$. We have

$$v = (\langle v, e_1 \rangle e_1 + ... + \langle v, e_m \rangle e_m) + (v - \langle v, e_1 \rangle e_1 - ... - \langle v, e_m \rangle e_m)$$

Let $u = \langle v, e_1 \rangle e_1 + ... + \langle v, e_m \rangle e_m$ and $w = v - \langle v, e_1 \rangle e_1 - ... - \langle v, e_m \rangle e_m$. Because each $e_k \in U$, we see that $u \in U$. Because $e_1,...,e_m$ is an orthonormal list, for each $k=1,...,m$, we have 

$$\langle w, e_k \rangle = \langle v, e_k \rangle - \langle  \langle v, e_k \rangle e_k, e_k \rangle = \langle v, e_k \rangle - \langle v, e_k \rangle \langle e_k, e_k \rangle = 0$$

Thus $w$ is orthogonal to every vector in $span(e_1,...,e_m)$, which shows that $w \in U^{\perp}$. 

Hence we have written $v = u + w$, where $u \in U, w, \in U^{\perp}$, completing the proof that $V = U + U^{\perp}$. 

From 6.48, we know that $U \cap U^{\perp} = \\{0\\}$. This implies that $V = U \oplus U^{\perp}$ by 1.46.


### 6.51
Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$. Then

$$dim U^{\perp} = dim V - dim U$$

Proof: 

The formula for $dim U^{\perp}$ follows from 6.49 and 3.94.


### 6.52
Suppose $U$ is a finite-dimensional subspace of $V$. Then

$$U = (U^{\perp})^{\perp}$$

Proof:

$\subseteq$ Suppose $u \in U$. Then $\langle u, w \rangle = 0$ for every $w \in U^{\perp}$. Because $u$ is orthogonal to every vector in $U^{\perp}$, we have $u \in (U^{\perp})^{\perp}$.

$\supseteq$ Suppose $v \in (U^{\perp})^{\perp}$. By 6.49, we can write $v = u + w$, where $u \in U$ and $w \in U^{\perp}$. 

We have $v - u = w \in U^{\perp}$. Because $v \in (U^{\perp})^{\perp}$ and $u \in (U^{\perp})^{\perp}$ (first paragraph), we have $v - u \in (U^{\perp})^{\perp}$. 

Thus $v - u \in U^{\perp} \cap (U^{\perp})^{\perp}$, which implies that $v - u = 0$ by 6.48, which implies that $v - u$, which implies that $v \in U$.

Thus $(U^{\perp})^{\perp} \subseteq U$.


### 6.54
Suppose $U$ is a finite-dimensional subspace of $V$. Then

$$U^{\perp} = \\{0\\} \iff U = V$$

Proof:

First suppose $U^{\perp} = \\{0\\}. Then by 6.52, $U = (U^{\perp})^{\perp} = \\{0\\}^{\perp} = V$, as desired.

Conversely, if $U = V$, then $U^{\perp} = V^{\perp} = \\{0\\}$ by 6.48.


### 6.55 Definition: orthogonal projection
Suppose $U$ is a finite-dimensional subspace of $V$. The orthogonal projection of $V$ onto $U$ is the operator $P_U \in L(V)$ defined as follows: For each $v \in V$, write $v = u + w$, where $u \in U$ and $w \in U^{\perp}$. Then let $P_U v = u$.

### 6.57
Suppose $U$ is a finite-dimensional subspace of $V$. Then

(a) $P_U \in L(V)$;

(b) $P_U u = u$ for every $u \in U$;

(c) $P_U w = 0$ for every $w \in U^{\perp}$;

(d) $range P_U = U$;

(e) $null P_U = U^{\perp}$;

(f) $v - P_U v \in U^{\perp}$ for every $v \in V$;

(g) $P_U^2 = P_U$;

(h) $\lVert P_U v \rVert \leq \lVert v \rVert$ for every $v \in V$;

(i) if $e_1,...,e_m$ is an orthonormal basis of $U$ and $v \in V$, then

$$P_U v = \langle v, e_1 \rangle e_1 + ... + \langle v, e_m \rangle e_m.$$

Proof:

(a) To show that $P_U$ is a linear map on $V$, suppose $v_1, v_2 \in V$. Write $v_1 = u_1 + w_1$ and $v_2 = u_2 + w_2$ with $u_1, u_2 \in U$ and $w_1, w_2 \in U^{\perp}$. Thus $P_U v_1 = u_1$ and $P_U v_2 = u_2$. 

Now $v_1 + v_2 = (u_1 + u_2) + (w_1 + w_2)$ where $(u_1 + u_2) \in U$ and $w_1 + w_2 \in U^{\perp}$. Thus $P_U (v_1 + v_2) = u_1 + u_2 = P_U v_1 + P_U v_2$.

Similarly, suppose $\lambda \in F$ and $v \in V$. Write $v = u + w$, where $u \in U$ and $w \in U^{\perp}$. Then $\lambda v = \lambda u + \lambda w$ with $\lambda u \in U$ and $\lambda w \in U^{\perp}$. Thus $P_U (\lambda v) = \lambda u = \lambda P_U v$. 

Hence $P_U$ is a linear map from $V to V$.

(b) Suppose $u \in U$. We can write $u = u + 0$, where $u \in U$ and $0 \in U^{\perp}$. Thus $P_U u = u$.

(c) Suppose $w \in U^{\perp}$. We can write $w = 0 + w$, where $0 \in U$ and $w \in U^{\perp}$. Thus $P_U w = 0$. 

(d) The definition of $P_U$ implies that $range P_U \subseteq U$. Furthermore, (b) implies that $U \subseteq range P_U$. Thus $range P_U = U$.

(e) The inclusion $U^{\perp} \subseteq null P_U$ follows from (c). To prove the inclusion in the other direction, note that if $v \in null P_U$ then the decomposition must be $v = 0 + v$, where $0 \in U$ and $v \in U^{\perp}$. Thus $null P_U \subseteq U^{\perp}$.

(f) If $v \in V$ and $v = u + w$ with $u \in U$ and $w \in U^{\perp}$, then 

$$v - P_U v = v - u = w \in U^{\perp}$$

(g) If $v \in V$ and $v = u + w$ with $u \in U$ and $w \in U^{\perp}$, then 

$$P_U^2 v = P_U (P_U v) = P_U u = u = P_U v$$

If $v \in V$ and $v = u + w$ with $u \in U$ and $w \in U^{\perp}$, then

$$\lVert P_U v \rVert^2 = \lVert u \rVert^2 \leq \lVert u \rVert^2 + \lVert w \rVert^2 = \lVert v \rVert^2$$

where the last equality comes from the Pythagorean theorem.

(i) The formula for $P_U v$ comes from the proof of 6.49.


### 6.58 Riesz representation theorem revisited
Suppose $V$ is finite-dimensional. For each $v \in V$, define $\phi_v \in V'$ by 

$$\phi_v(u) = \langle u,v \rangle$$

for each $u \in V$. Then $v \rightarrow \phi_v$ is a one-to-one function from $V$ to $V'$.

Proof:

To show that $v \rightarrow \phi_v$ is surjective, suppose $\phi \in V'$. 

If $\phi = 0$, then $\phi = \phi_0$. Thus assume $\phi \neq 0$. Hence $null \phi \neq V$, which implies that $(null \phi)^{\perp} \neq \\{0\\}$ by 6.49.

Let $w \in (null \phi)^{\perp}$ be such that $w \neq 0$. Let 

$$(6.59)  v = \frac{\overline{\phi(w)}}{\lVert w \rVert^2} w$$

Then $v \in (null \phi)^{\perp}$. Also $v \neq 0$ (because $w \neq null \phi$).

Taking the norm of both sides gives

$$\lVert v \rVert = \frac{|\phi(w)|}{\lVert w \rVert}$$

Applying $\phi$ to both sides of 6.59 and then using 6.60, we have

$$\phi(v) = \frac{|\phi(w)|^2}{\lVert w \rVert^2} = \lVert v \rVert^2$$

Now suppose $u \in V$. Using the equation above, we have

$$u = u - \frac{\phi(u)}{\phi(v)} v + \frac{\phi(u)}{\phi(v)} v = (u - \frac{\phi(u)}{\phi(v)} v) + \frac{\phi(u)}{\lVert v \rVert^2} v$$

The term in parentheses above is in $null \phi$ and hence is orthogonal to $v$. Thus taking the inner product of both sides of the equation above with $v$ shows that 

$$\langle u,v \rangle = \frac{\phi(u)}{\lVert v \rVert^2} \langle v,v \rangle = \phi(u)$$

Thus $\phi = \phi_v$, showing that $v \rightarrow \phi_v$ is surjective, as desired.


### 6.59
Suppose $U$ is a finite-dimensional subspace of $V$, $v \in V$, and $u \in U$. Then

$$\lVert v - P_U v \rVert \leq \lVert v - u \rVert$$

Furthermore, the inequality above is an equality if and only if $u = P_U v$.

Proof:

We have 

$$\lVert v - P_U v \rVert^2 \leq \lVert v - P_U v \rVert^2 + \lVert P_U v - u \rVert^2 = \lVert (v - P_U v) + (P_Uv - u) \rVert^2 = \lVert v-u \rVert^2$$

where the first inequality holds because $0 \leq \lVert P_U v - u \rVert^2$, the second inequality comes from the Pythagorean theorem (which applies because $v - P_U v \in U^{\perp}$ by 6.57 and $P_U v - u \in U$). 

Taking square roots gives the desired inequality.

The inequality proved is an equality if and only if $\lVert v - P_U v \rVert^2 = \lVert v - P_U v \rVert^2 + \lVert P_U v - u \rVert^2$, which happens if and only if $\lVert P_U v - u \rVert = 0$, which happens if and only if $u = P_U v$.


### 6.67



## Exercises

#### (1) Suppose $v_1,...,v_m \in V$. Prove that $\\{v_1,...,v_m\\}^{\perp} = (span(v_1,...,v_m))^{\perp}$.
$\subseteq$ Suppose $v \in \\{v_1,...,v_m\\}^{\perp}$. Then $\langle v_k, v \rangle = 0$ for $k = 1,...,m$. 

Let $a_1,...,a_m \in F$. Then 

$$0 = a_1 \langle v_1, v \rangle + ... + a_m \langle v_m, v \rangle = \langle a_1 v_1, v \rangle + ... + \langle a_m v_m, v \rangle = \langle a_1 v_1 + ... + a_m v_m, v \rangle$$

Since $a_1,...,a_m$ is arbitrary, $v \in (span(v_1,...,v_m))^{\perp}$.

$\supseteq$ Suppose $v \in (span(v_1,...,v_m))^{\perp}$. Then $\langle a_1 v_1 + ... + a_m v_m, v \rangle = 0$ for any $a_1,...,a_m \in F$. 

Since $v_k \in span(v_1,...,v_m)$ for $k=1,...,m$, we have $\langle v_k, v \rangle = 0$ for $k=1,...,m$. 

Hence $v \in \\{v_1,...,v_m\\}^{\perp}$.


#### (2)


#### (3)


#### (4)


#### (5) Suppose that $V$ is finite-dimensional and $U$ is a subspace of $V$. Show that $P_{U^{\perp}} = I - P_U$, where $I$ is the identity operator on $V$.
Suppose $v \in V$. We can uniquely write $v = u + w$ where $u \in U$ and $w \in U^{\perp}$ by 6.49. Hence 

$$P_{U^{\perp}} v = w = v - u = Iv - P_U v = (I - P_U) v$$


#### (6) Suppose $V$ is finite-dimensional and $T \in L(V,W)$. Show that $T = TP_{(null T)^{\perp}} = P_{range T} T$.
First we want to show $T = TP_{(null T)^{\perp}}$.

Suppose $v \in V$. We have $V = null T \oplus (null T)^{\perp}$. We can write $v = v_1 + v_2$, where $v_1 \in null T$ and $v_2 \in (null T)^{\perp}$. Then $P_{(null T)^{\perp}} v = v_2$. We have

$$Tv = T(v_1 + v_2) = Tv_1 + Tv_2 = Tv_2 = T (P_{(null T)^{\perp}} v)$$

Hence $T = TP_{(null T)^{\perp}}$.

Next we want to show $T = P_{range T} T$. 

Since $Tv \in range T, $, by 6.57(b), we have $P_{range T} (Tv) = Tv = (P_{range T} T) v$ for all $v \in V$.

Hence $T = P_{range T} T$.


#### (7) Suppose $X$ and $Y$ are finite-dimensional subspaces of $V$. Prove that $P_X P_Y = 0$ if and only if $\langle x, y \rangle=0$ for all $x \in X$ and all $y \in Y$.
$\Rightarrow$
Suppose $P_X P_Y = 0$. Suppose $y \in Y$. Then $P_Y y = y$ by 6.57(b), and 

$$P_X y = P_X (P_Y y) = (P_X P_Y) y = 0$$ 

By 6.57(c), $y \in X^{\perp}$. Thus $Y \subseteq X^{\perp}$. 

Therefore $\langle x, y \rangle = 0$ for every $x \in X, y \in Y$.

$\Leftarrow$
Suppose $\langle x, y \rangle = 0$ for all $x \in X$ and $y \in Y$. Then $Y \subseteq X^{\perp}$. 

Suppose $v \in V$. We can write $v = y + w$ where $y \in Y$ and $w \in Y^{\perp}$. Then $P_Y v = y$. 

$$0 = P_X y = P_X (P_Y v) = (P_X P_Y) v$$ 

Therefore $P_X P_Y = 0$.


#### (8) Suppose $U$ is a finite-dimensional subspace of $V$ and $v \in V$. Define a linear functional $\phi: U \rightarrow F$ by $\phi(u) = \langle u, v \rangle$ for all $u \in U$. By the Riesz representation theorem, there exists a unique vector $w \in U$ such that $\phi(u) = \langle u, w \rangle$ for all $u \in U$. Show that $w = P_U v$.
Since $\phi(u) = \langle u, v \rangle = \langle u, w \rangle$ for all $u \in U$, we have $\langle u, v \rangle - \langle u, w \rangle = \langle u, v-w \rangle = 0$ for all $u \in U$. 

Hence $v - w \in U^{\perp}$. 

Because $w \in U$, we can write $v = (v - w) + w$ where $v - w \in U^{\perp}$ and $w \in U$. Therefore we have

$$P_U v = P_U (v-w+w) = P_U (v-w) + P_U w = 0 + w = w$$


#### (12)


#### (13) Suppose $F=R$ and $V$ is finite-dimensional. For each $v \in V$, let $\phi_v$ denote the linear functional on $V$ defined by $\phi_v(u) = \langle u,v \rangle$ for all $u \in V$.
(a) Show that $v \rightarrow \phi_v$ is an injective linear map from $V$ to $V'$.

Define $T \in L(V, V')$, where $Tv = \phi_v$ where $\phi_v(u) = \langle u,v \rangle$.

First we want to show that $T$ is linear. 

Let $v, w \in V$. Then $T(v+w) = \phi_{v+w}$. 

$$\phi_{v+w} (u) = \langle u, v+w \rangle = \langle u, v \rangle + \langle u, w \rangle = \phi_v(u) + \phi_w(u)$$

Therefore $T(v+w) = Tv + Tw$.

Let $\lambda \in R, v \in V$. Then $T(\lambda v) = \phi_{\lambda v}$.

$$\phi_{\lambda v} (u) = \langle u, \lambda v \rangle = \lambda \langle u, v \rangle = \lambda \phi_v(u)$$

where the second equality follows from the fact that $F = R$ so $\lambda = \overline{\lambda}$.

Therefore $T(\lambda v) = \lambda Tv$. Thus $T$ is a linear map.

To show that $T$ is injective, suppose $Tv = 0$. Then $\phi_v = 0$, and $\phi(u) = \langle u, v \rangle= 0$ for all $u \in V$. Taking $u = v$, we have $\langle v, v \rangle = 0$. Hence $v = 0$. Therefore $null T = \\{0\\}$, and $T$ is injective.


(b) Use (a) and a dimension-counting argument to show that $v \rightarrow \phi_v$ is an isomorphism from $V$ to $V'$.

By 3.111, $dim V = dim V'$. From part (a), $T$ is injective, therefore $T$ is surjective by 3.65. Thus it is an isomorphism.


#### (14) Suppose that $e_1,...,e_n$ is an orthonormal basis of $V$. Explain why the dual basis (3.112) of $e_1,...,e_n$ is $e_1,...,e_n$ under the identification of $V'$ with $V$ provided by the Riesz representation theorem 6.58.
Define $\phi_k(u) = \langle u, e_k \rangle$ for $k=1,...,n$, for all $u \in V$. 

Since $e_1,...,e_n$ is an orthonormal basis of $V$, $\phi_k(e_j) = \langle e_j, e_k \rangle = \delta_{jk}$. Therefore $\phi_1,...,\phi_n$ satisfies the condition in 3.112 and is the dual basis of $e_1,...,e_n$.

By the Riesz representation, we can associate each $\phi_k$ with $e_k$. Thus the dual basis $\phi_1,...,\phi_n$ corresponds to $e_1,...,e_n$.


#### (15) In $R^4$, let $U = span((1,1,0,0), (1,1,1,2))$. Find $u \in U$ such that $\lVert u - (1,2,3,4) \rVert$ is as small as possible.



