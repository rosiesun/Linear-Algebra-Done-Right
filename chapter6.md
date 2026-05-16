Linear Algebra Done Right - Chapter 6 <br>
Inner Product Spaces
================
Rosie Sun <br>
2026-05-15


# 6A Inner Products and Norms

### 6.1 Definition: dot product
For $x, y \in R^n$, the dot product of $x$ and $y$, denoted by $x \dot y$, is defined by 

$$x \dot y = x_1 y_1 + ... + x_n y_n$$

where $x = (x_1,...,x_n)$ and $y = (y_1, ..., y_n)$.

### 6.2 Definition: inner product
An inner product on $V$ is a function that takes each ordered pair $(u,v)$ of elements of $V$ to a number $<u,v> \in F$ and has the following properties:

- positivity: $<v,v> \geq 0$ for all $v \in V$.
- definiteness: $<v,v>=0$ if and only if $v=0$.
- additivity in the first slot: $<u+v,w> = <u,w> + <v,w>$ for all $u,v,w \in V$.
- homogeneity in first slot: $<\lambda u, v> = \lambda <u,v>$ for all $\lambda in F$ and all $u,v \in V$.
- conjugate symmetry: $<u,v> = \overline{<v,u>}$ for all $u,v \in V$.

### 6.4 Definition: inner product space
An inner product space is a vector space $V$ along with an inner product on $V$.

### 6.6
- 


## Exercises
#### (1) Prove or give a counterexample: If $v_1,...,v_m \in V$, then $\sum^m_{j=1} \sum^m_{k=1} <v_j,v_k> \geq 0$.
Note that 

$$\sum^m_{j=1} \sum^m_{k=1} <v_j,v_k> = <v_1+...+v_m, v_1+...v_m> \geq 0$$

from the bilinearity of the inner product.


#### (2) Suppose $S \in L(V)$. Define $<.,.>_1$ by $<u,v>_1 = <Su,Sv>$ for all $u,v \in V$. Show that $<.,.>_1$ is an inner product on $V$ if and only if $S$ is injective.
$\Rightarrow$
Suppose $<.,.>_1$ is an inner product. Assume towards contradiction that $S$ is not injective. Then $null S \neq \\{0\\}$, and there exists some $v \in V, v \neq 0$ such that $Sv = 0$. We have $<v,v>_1 = <Sv, Sv> = <0,0> = 0$. This violates the definiteness of the inner product, hence a contradiction.

$\Leftarrow$
Suppose $S$ is injective. We verify each property in the inner product definition 6.2

Positivity: $<v,v>_1 = <Sv, Sv> \geq 0$ for all $v \in V$, by the property of the inner product.

Definiteness: $<v,v>_1 = <Sv,Sv> = 0$ if and only if $Sv=0$. By the injectivity of $S$, $v=0$. 

Additivity in the first slot satisfied by the linearity of $S$: 

$$<u+v, w>_1 = <S(u+v), Sw> = <Su + Sv, Sw> = <Su,Sw> + <Sv,Sw> = <u,w>_1 + <v,w>_1$$

for all $u,v,w \in V$.

Homogeneity in the first slot satisfied by the homogeneity of $S$:

$$<\lambda u, v>_1 = <S(\lambda u), Sv> = <\lambda Su, Sv> = \lambda <Su, Sv> = \lambda <u,v>_1$$

for all $\lambda \in F, u,v \in V$.

Conjugate symmetry satisfied from the property of the inner product: 

$$<u,v>_1 = <Su,Sv> = \overline{<Sv,Su>} = \overline{<v,u>_1}$$

for all $u,v \in V$.


#### (3)
(3a) Show that the function taking an ordered pair $(x_1,x_2), (y_1,y_2)$ of elements of $R^2$ to $|x_1 y_1| + |x_2 y_2|$ is not an inner product of $R^2$.

The function violates the additivity in the first slot. Suppose $(x_1,x_2), (y_1,y_2), (z_1,z_2) \in R^2$. 

$$<(x_1 + y_1, x_2 + y_2), (z_1, z_2)> = |(x_1 + y_1)z_1| + |(x_2 + y_2)z_2|$$

which is less than or equal to

$$<(x_1, x_2), (z_1, z_2)> + <(y_1,y_2), (z_1,z_2)> = |x_1 z_1| + |x_2 z_2| + |y_1 z_1| + |y_2 z_2|$$

by the triangle inequality on absolute values.

(3b) Show that the function taking an ordered pair $(x_1,x_2,x_3), (y_1,y_2,y_3)$ of elements of $R^3$ to $x_1 y_1 + x_3 y_3$ is not an inner product on $R^3$.

The function violates definiteness. $<(0,1,0), (0,1,0)> = 0$ but $(0,1,0) \neq 0$.


#### (4) Suppose $T \in L(V)$ is such that $||Tv|| \leq ||v||$ for every $v \in V$. Prove that $T - \sqrt{2} I$ is injective.
Assume towards contradiction that $T-\sqrt{2} I$ is not injective. Then $null (T-\sqrt{2} I) \neq \\{0\\}$, and $(T-\sqrt{2}I)v = 0$ for some $v \neq 0, v \in V$. We have $Tv = \sqrt{2} v$. $||Tv|| = || \sqrt{2} v|| = \sqrt{2} ||v||$. However, by hypothesis, $||Tv|| \leq ||v||$, which is a contradiction. Therefore we conclude $T - \sqrt{2} I$ is injective.


#### (5) Suppose $V$ is a real inner product space. 
(a) Show that $<u+v, u-v> = ||u||^2 - ||v||^2$ for every $u,v \in V$.

$$<u+v,u-v> = <u,u-v> + <v,u-v> = <u,u> - <u,v> + <v,u> - <v,v> = <u,u> - <u,v> + \overline{<u,v>} - <v,v> = ||u||^2 - ||v||^2$$

(b) Show that $u,v \in V$ have the same norm, then $u+v$ is orthogonal to $u-v$.

From (a), if $||u||=||v||$, then $<u+v, u-v> = 0$.

(c) Use (b) to show that the diagonals of a rhombus are perpendicular to each other.

The diagonals of the rhombus are $u+v, u-v$, with $||u||=||v||$. Therefore by (b), the diagonals are perpendicular to each other.


#### (6) Suppose $u,v \in V$. Prove that $<u,v>=0 \iff ||u|| \leq ||u+av||$ for all $a \in F$.
$\Rightarrow$
Suppose $<u,v>=0$. Then $<u,av>=\overline{a}<u,v>=0$. By the Pythagorean theorem, $||u+av||^2 = ||u||^2 + ||av||^2$. Thus $||u||^2 \leq ||u + av||^2$. Taking square root, we have the desired inequality.

$\Leftarrow$
Suppose $||u|| \leq ||u+av||$ for all $a \in F$. Then $||u||^2 \leq ||u+av||^2$.

$$||u+av||^2 = <u+av,u+av> = ||u||^2 + \overline{a}<u,v> + a \overline{<u,v>} + |a|^2 ||v||^2$$

Let $\lambda = <u,v>$.

$$0 \leq \overline{a} \lambda + a \overline{\lambda} + |a|^2 ||v||^2$$

$$0 \leq 2 Re(a \overline{\lambda}) + |a|^2 ||v||^2$$

Let $a = -t \lambda, t \in R, t > 0$. Note that $a \overline{\lambda} = -t |\lambda|^2$ which is real. Then the equation above becomes

$$0 \leq -2 t |\lambda|^2 + t^2 |\lambda|^2 ||v||^2$$

Dividing both sides by $t$,

$$0 \leq -2 |\lambda|^2 + t |\lambda|^2 ||v||^2$$

For small $t$, $t \rightarrow 0^+$, we have $0 \leq -2 |\lambda|^2$, which forces $|\lambda|^2 = 0$. Thus $\lambda = <u,v>=0$.


#### (7) Suppose $u,v \in V$. Prove that $||au + bv|| = ||bu + av||$ for all $a,b \in R$ if and only if $||u|| = ||v||$.
$\Leftarrow$
Suppose $||u||=||v|| = \lambda$. Then 

$$||au + bv||^2 = <au+bv, au+bv> = a^2 ||u||^2 + b^2 ||v||^2 + 2ab Re(<u,v>)$$

$$||bu + av||^2 = <bu+av, bu+av> = b^2 ||u||^2 + a^2 ||v||^2 + 2ab Re(<u,v>)$$

Since $||au + bv||^2 = ||bu + av||^2$, $||au + bv|| = ||bu + av||$.

$\Rightarrow$
Suppose $||au + bv|| = ||bu + av||$. Then $||au + bv||^2 = ||bu + av||^2$.

$$||au + bv||^2 - ||bu + av||^2 = a^2 (||u||^2 - ||v||^2) + b^2 (||v||^2 - ||u||^2) = (a^2 - b^2) (||u||^2 - ||v||^2)$$

Let $a=1, b=0$, then $a^2 - b^2 = 1 \neq 0$, so $||u||^2 - ||v||^2$ must be 0.

Therefore $||u||^2 = ||v||^2$, and $||u|| = ||v||$.


#### (8) Suppose $a,b,c,x,y \in R$ and $a^2 + b^2 + c^2 + x^2 + y^2 \leq 1$. Prove that $a+b+c+4x+9y \leq 10$.
We have $||(a,b,c,x,y)||^2 \leq 1$. Then $||(a,b,c,x,y)|| \leq 1$.

$$a + b + c + 4x + 9y = <(a,b,c,x,y),(1,1,1,4,9)> \leq |<(a,b,c,x,y),(1,1,1,4,9)>|$$

By Cauchy-Schwartz inequality, 

$$|<(a,b,c,x,y),(1,1,1,4,9)>| \leq ||(a,b,c,x,y)|| ||(1,1,1,4,9)|| \leq 1 \sqrt{100} = 10$$

Thus $a+b+c+4x+9y \leq 10$.


#### (9) Suppose $u,v \in V$ and $||u||= ||v|| = 1$ and $<u,v>=1$. Prove that $u=v$.
$$<u-v, u-v> = <u,u> - <u,v> - <v,u> - <v,v> = <u,u> + <u,v> - \overline{<u,v>} + <v,v> = 1-1-1+1=0$$

Therefore $u-v=0$, and $u=v$.


#### (10) Suppose $u,v \in V$ and $||u|| \leq 1$ and $||v|| \leq 1$. Prove that $\sqrt{1-||u||^2} \sqrt{1-||v||^2} \leq 1 - |<u,v>|$.
Squaring both sides of the desired inequality, we have

$$(1-||u||^2)(1-||v||^2) \leq (1 - |<u,v>|)^2$$

Note that 

$$(1 - ||u|| ||v||)^2 \leq (1 - |<u,v>|)^2$$

by Cauchy-Schwartz inequality.

We want to show

$$(1-||u||^2)(1-||v||^2) \leq (1 - ||u|| ||v||)^2$$

Expanding LHS

$$(1-||u||^2)(1-||v||^2) = 1 - ||u||^2 - ||v||^2 + ||u||^2 ||v||^2$$

Expanding RHS

$$(1 - ||u|| ||v||)^2 = 1 + ||u||^2 ||v||^2 - 2 ||u|| ||v||$$

Subtracting $ ||u||^2 ||v||^2$,

We want to show 

$$1 - ||u||^2 - ||v||^2 \leq 1 - 2 ||u|| ||v||$$

Rearranging, we have

$$||u||^2 + ||v||^2 - 2 ||u|| ||v|| = (||u||-||v||)^2 \geq 0$$

which holds. Taking square root of both sides, we have the desired inequality.


#### (11) Find vectors $u, v \in R^2$ such that $u$ is a scalar multiple of $(1,3)$, $v$ is orthogonal to $(1,3)$, and $(1,2)=u+v$.
By hypothesis, $u = a(1,3)$. 

Let $v=(x,y)$. $<(x,y), (1,3)> = x+3y = 0$. $y = -1/3 x$.

$$u + v = (a, 3a) + (x, -1/3 x) = (1,2)$$

Solving the two equations, we have

$u = (7/10, 21/10), v = (3/10, -1/10)$.


#### (12) Suppose $a,b,c,d$ are positive numbers.
(a) Prove that $(a+b+c+d)(1/a + 1/b + 1/c + 1/d) \geq 16$.

$$|<(\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}), (1/sqrt{a}, 1/sqrt{b}, 1/sqrt{c}, 1/sqrt{d})>|^2 = (1+1+1+1)^2 = 16$$

$$||(\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d})||^2 = = a+b+c+d$$

$$||(\sqrt{1/a}, \sqrt{1/b}, \sqrt{1/c}, \sqrt{1/d})||^2 = = 1/a + 1/b + 1/c + 1/d$$

By Cauchy-Schwartz inequality, 

$$16 \leq (a+b+c+d)(1/a + 1/b + 1/c + 1/d)$$

(b) For which numbers $a,b,c,d$ is the inequality above an equality?

Equality holds when one vector is a scalar multiple of the other. 

$$(\sqrt{a}, \sqrt{b}, \sqrt{c}, \sqrt{d}) = 1/\lambda (1/sqrt{a}, 1/sqrt{b}, 1/sqrt{c}, 1/sqrt{d})$$

Then $\sqrt{a}=\lambda / \sqrt{a}$, $a=\lambda$. Similarly, $b=c=d=\lambda$. 

Hence $a=b=c=d$.


#### (13) Show that the square of an average is less than or equal to the average of the squares. More precisely, show that if $a_1,...,a_n \in R$, then the square of the average of $a_1,...,a_n$ is less than or equal to the average of $a_1^2,...,a_n^2$.
$$|<(1/n,...,1/n), (a_1,...,a_n)>|^2 = (a_1 /n + ... + a_n /n)^2$$

$$||(1/n, ..., 1/n)||^2 = 1/n^2 + ... + 1/n^2 = 1/n$$

$$||(a_1,...,a_n)||^2 = a_1^2 + ... + a_n^2$$

By Cauchy-Schwartz inequality, 

$$(a_1 /n + ... + a_n /n)^2 \leq 1/n (a_1^2 + ... + a_n^2)$$



# 6B Orthonormal Bases

### 6.30
Suppose $e_1,...,e_n$ is an orthonormal basis of $V$ and $u,v \in V$. Then

- $v = <v, e_1>e_1 + ... <v,e_n>e_n$
- $||v||^2 = |<v,e_1>|^2 + ... + |<v,e_n>|^2$
- $<u,v> = <u,e_1>\overline{<v,e_1>} + ... + <u,e_n>\overline{<v,e_n>}$

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

$$\phi(u) = <u, v>$$

for every $u \in V$.


## Exercises

#### (1) Suppose $e_1,...,e_m$ is a list of vectors in $V$ such that $||a_1 e_1 + ... + a_m e_m||^2 = |a_1|^2 + ... + |a_m|^2$ for all $a_1,...,a_m \in F$. Show that $e_1,...,e_m$ is an orthonormal list.

First we want to show that the norms of each $e_i, i=1,...,m$ is 1.

Let $a_k=1$, $a_i = 0, i \neq k$. Then 

$$||a_k e_k||^2 = |a_k|^2 ||e_k||^2 = |a_k|^2$$

Therefore $||e_k|| = 1$. Since $k$ was arbitrary, all the $e_i, i=1,...,m$ has unit norm.

Next we want to show that the inner product of $e_k, e_l$ is 0 for $k \neq l$.

Let $a_k, a_l \in F$, $a_i = 0, i \neq k, i \neq l$. Then 

$$||a_k e_k a_l e_l||^2 = |a_k|^2 + |a_l|^2 + a_k \overline{a_l} <e_k, e_l> + a_l \overline{a_k} <e_l, e_k> = |a_k|^2 + |a_l|^2$$

Thus 

$$a_k \overline{a_l} <e_k, e_l> + a_l \overline{a_k} <e_l, e_k> = 0$$ 

for all $a_k, a_l \in F$.

Consider $a_k = a_l = 1$. Then 

$$<e_k, e_l> + <e_l, e_k> = <e_k, e_l> + \overline{<e_k, e_l>} = 2 Re(<e_k, e_l>) = 0$$ 

Thus $Re(<e_k, e_l>) = 0$.

Consider $a_k = i, a_l = 1$. Then

$$i <e_k, e_l> + (-i) \overline{<e_k, e_l>} = i (<e_k, e_l> - \overline{<e_k,e_l>}) = i 2Im(<e_k, e_l>)$$

Thus $Im(<e_k, e_l>) = 0$.

Therefore $<e_k, e_l> = 0$ for $k \neq l$.


#### (2)
(a)

(b)

#### (3) Suppose $e_1,...,e_m$ is an orthonormal list in $V$ and $v \in V$. Prove that $||v||^2 = |<v,e_1>|^2 + ... + |<v,e_m>|^2 \iff v \in span (e_1,...,e_m)$.

#### (4) Suppose $n$ is a positive integer. Prove ethat $1/\sqrt{2\pi}, cos x / sqrt{\pi}$



# 6C Orthogonal Complements and Minimization Problems

### 6.46 Definition: orthogonal complement
If $U$ is a subset of $V$, then the orthogonal complement of $U$, denoted by $U^{\perp}$, is the set of all vectors in $V$ that are orthogonal to every vector in $U$:

$$U^{\perp} = \\{v \in V: <u,v>=0 for every u \in U\\}$$


