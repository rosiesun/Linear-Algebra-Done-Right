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
- For each fixed $v \in V$, the function that takes $u \in V$ to $<u,v>$ is a linear map from $V$ to $F$.
- $<0,v> = 0$ for every $v \in V$.
- $<v,0> = 0$ for every $v \in V$.
- $<u, v+w> = <u,v> + <u,w>$ for all $u,v,w \in V$.
- $<u, \lambda v> = \overline{\lambda} <u, v>$ for all $\lambda \in F$ and all $u, v \in V$.

### 6.7 Definition: norm
For $v \in V$, the norm of $v$, denoted by $||v||$, is defined by $||v|| = \sqrt{<v,v>}$.

### 6.8
Suppose $v \in V$.

- $||v||=0$ if and only if $v=0$.
- $||\lambda v|| = |\lambda| ||v||$ for all $\lambda \in F$.

### 6.10 Definition: orthogonal
Two vectors $u, v \in V$ are called orthogonal if $<u,v>=0$.

### 6.11
- 0 is orthogonal to every vector in $V$.
- 0 is the only vector in $V$ that is orthogonal to itself.

### 6.12 Pythagorean theorem
Suppose $u,v \in V$. If $u$ and $v$ are orthogonal, then $||u+v||^2 = ||u||^2 + ||v||^2$.

Proof: Suppose $<u,v>=0$. Then 

$$||u+v||^2 = <u+v, u+v> = <u,u> + <u,v> + <v,u> + <v,v> = ||u||^2 + ||v||^2$$

### 6.13
Suppose $u,v \in V$, with $v \neq 0$. Set $c = \frac{<u,v>}{||v||^2}$ and $w = u - \frac{<u,v>}{||v||^2} v$. Then $u = cv + w$ and $<w,v>=0$.

### 6.14 Cauchy-Schwartz inequality
Suppose $u,v \in V$. Then $|<u,v>| \leq ||u|| ||v||$. This inequality is an equality if and only if one of $u, v$ is a scalar multiple of the other.

Proof: If $v = 0$, then both sides of the desired inequality equal 0. Thus we can assume that $v \neq 0$. Consider the orthogonal decomposition 

$$u = \frac{<u,v>}{||v||^2} v + w$$

where $w$ is orthogonal to $v$. By the Pythagorean theorem,

$$||u||^2 = ||\frac{<u,v>}{||v||^2} v||^2 + ||w||^2 = \frac{|<u,v>|^2}{||v||^2} + ||w||^2 \geq \frac{|<u,v>|^2}{||v||^2}$$

Multiplying both sides of this inequality by $||v||^2$ and then taking square roots gives the desired inequality.

The proof above shows that the Cauchy-Schwartz inequality is an equality if and only if $w = 0$. But $w = 0$ if and only if $u$ is a multiple of $v$. Thus the Cauchy-Schwartz inequality is an equality if and only if $u$ is a scalar multiple of $v$ or $v$ is a scalar multiple of $u$.

### 6.17 Triangule inequality
Suppose $u,v \in V$. Then $||u+v|| \leq ||u|| + ||v||$. This inequality is an equality if and only if one of $u, v$ is a nonnegative real multiple of the other.

Proof: We have

$$||u+v||^2 = <u+v, u+v> = <u,u> + <v,v> + <u,v> + <v,u> = ||u||^2 + ||v||^2 + <u,v> + \overline{<u,v>}$$

$$||u||^2 + ||v||^2 + <u,v> + \overline{<u,v>} = ||u||^2 + ||v||^2 + 2 Re(<u,v>) \leq ||u||^2 + ||v||^2 + 2 |<u,v>| $$

by 4.4

$$||u||^2 + ||v||^2 + 2 |<u,v>|  \leq ||u||^2 + ||v||^2 + 2 ||u|| ||v|| = (||u|| + ||v||)^2$$

by Cauchy-Schwartz inequality.

Taking square roots of both sides of the inequality above gives the desired inequality.

### 6.21 Parallelogram equality
Suppose $u, v \in V$. Then $||u+v||^2 + ||u-v||^2 = 2 (||u||^2 + ||v||^2)$



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

### 6.22 Definition: orthonormal
- A list of vectors is called orthonormal if each vector in the list has norm 1 and is orthogonal to all the other vectors in the list.
- In other words, a list $e_1,...,e_m$ of vectors in $V$ is orthonormal if $<e_j, e_k> = 1$ if $j=k$, $<e_j, e_k>=0$ if $j \neq k$, for all $j, k \in \\{1,...,m\\}$.

### 6.24
Suppose $e_1,...,e_m$ is an orthonormal list of vectors in $V$. Then 

$$||a_1 e_1 + ... + a_m e_m||^2 = |a_1|^2 + ... + |a_m|^2$$

for all $a_1,...,a_m \in F$.

### 6.25
Every orthonormal list of vectors is linearly independent.

Proof: Suppose $e_1,...,e_m$ is an orthonormal list of vectors in $V$ and $a_1,...,a_m \in F$ are such that $a_1 e_1 + ... + a_m e_m = 0$. Then $|a_1|^2 + ... + |a_m|^2 = 0$ by 6.24, which means that all the $a_k$'s are 0. Thus $e_1,...,e_m$ is linearly independent.

### 6.26 Bessel's inequality
Suppose $e_1,...,e_m$ is an orthonormal list of vectors in $V$. If $v \in V$ then 

$$|<v,e_1>|^2 + ... + |<v,e_m>|^2 \leq ||v||^2$$

Proof: Suppose $v \in V$. Then 

$$v = <v,e_1> e_1 + ... + <v,e_m> e_m + v - <v,e_1> e_1 - ... - <v,e_m> e_m$$

Let $u = <v,e_1> e_1 + ... + <v,e_m> e_m$, $w = v - <v,e_1> e_1 - ... - <v,e_m> e_m$.

If $k \in \\{1,...,m\\}$, then $<w,e_k> = <v,e_k> - <v,e_k> <e_k, e_k> = 0$. This implies that $<w, u> = 0$. The Pythagorean theorem implies that 

$$||v||^2 = ||u||^2 + ||w||^2 \geq ||u||^2 = |<v,e_1>|^2 + ... + |<v,e_m>|^2$$

where the last equality comes from 6.24.

### 6.27 Definition: orthonormal basis
An orthonormal basis of $V$ is an orthonormal list of vectors in $V$ that is also a basis of $V$.

### 6.28
Suppose $V$ is finite-dimensional. Then every orthonormal list of vectors in $V$ of length $dim V$ is an orthonormal basis of $V$.

Proof: By 6.25, every orthonormal list of vectors in $V$ is linearly independent. Thus every such list of the right length is a basis by 2.38.

### 6.30
Suppose $e_1,...,e_n$ is an orthonormal basis of $V$ and $u,v \in V$. Then

- $v = <v, e_1>e_1 + ... <v,e_n>e_n$
- $||v||^2 = |<v,e_1>|^2 + ... + |<v,e_n>|^2$
- $<u,v> = <u,e_1>\overline{<v,e_1>} + ... + <u,e_n>\overline{<v,e_n>}$

### 6.32 Gram-Schmidt procedure
Suppose $v_1,...,v_m$ is a linearly independent list of vectors in $V$. Let $f_1 = v_1$. For $k = 2,...,m$, define $f_k$ inductively by 

$$f_k = v_k - \frac{<v_k, f_1>}{||f_1||^2} f_1 - ... - \frac{<v_k, f_{k-1}>}{||f_{k-1}||^2} f_{k-1}$$

For each $k=1,...,m$, let $e_k = \frac{f_k}{||f_k||}$. Then $e_1,...,e_m$ is an orthonormal list of vectors in $V$ such that

$$span(v_1,...,v_k) = span(e_1,...,e_k)$$

for each $k=1,...,m$.

Proof: 

We will show by induction on $k$ that the desired conclusion holds.

To get started with $k=1$, note that because $e_1 = \frac{f_1}{||f_1||}$, we have $||e_1||=1$; also, $span(v_1) = span(e_1)$ because $e_1$ is a nonzero multiple of $v_1$.

Suppose $1 < k \leq m$, and the list $e_1,...,e_{k-1}$ generated by the procedure is an orthonormal list such that 

$$span(v_1,...,v_{k-1}) = span(e_1,...,e_{k-1})$$

Because $v_1,...,v_m$ is linearly independent, we have $v_k \notin span(v_1,...,v_{k-1})$. Thus 

$$v_k \notin span(e_1,...,e_{k-1}) = span(f_1,...,f_{k-1})$$ 

which implies that $f_k \neq 0$. Hence we are not dividing by 0 in the definition of $e_k$. 

Dividing a vector by its norm produces a new vector with norm 1; thus $||e_k|| = 1$.

Let $j \in \\{1,...,k-1\\}$. Then 

$$<e_k, e_j> = \frac{1}{||f_k|| ||f_j||} <f_k, f_j> $$

$$= \frac{1}{||f_k|| ||f_j||} <v_k - \frac{<v_k, f_1>}{||f_1||^2} f_1 - ... - \frac{<v_k, f_{k-1}>}{||f_{k-1}||^2} f_{k-1}, f_j>$$

$$= \frac{1}{||f_k|| ||f_j||}  (<v_k, f_j> - <\frac{<v_k, f_j>}{||f_j||^2} f_j, f_j>)$$

$$= \frac{1}{||f_k|| ||f_j||} (<v_k, f_j> - <v_k, f_j>) = 0$$

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

$$\phi(u) = <u, v>$$

for every $u \in V$.

Proof: 

First we show that there exists a vector $v \in V$ such that $\phi(u) = <u,v>$ for every $u \in V$. 

Let $e_1,...,e_n$ be an orthonormal basis of $V$. Then 

$$\phi(u) = \phi(<u,e_1>e_1 + ... <u,e_n>e_n) = <u,e_1> \phi(e_1) + ... + <u,e_n> \phi(e_n) = <u, \overline{\phi(e_1)} e_1 + ... \overline{\phi(e_n)} e_n>$$

for every $u \in V$, where the first equality comes from 6.30. 

Thus setting 

$$v = \overline{\phi(e_1)} e_1 + ... + \overline{\phi(e_n)} e_n$$

we have $\phi(u) = <u,v>$ for every $u \in V$, as desired.

Now we prove that only one vector $v \in V$ has the desired behavior. 

Suppose $v_1,v_2 \in V$ are such that 

$$\phi(u) = <u, v_1> = <u, v_2>$$ 

for every $u \in V$. Then 

$$0 = <u, v_1> - <u, v_2> = <u, v_1-v_2>$$

for every $u \in V$. Taking $u = v_1 - v_2$ shows that $v_1 - v_2 = 0$. Thus $v_1 = v_2$, completing the proof of the uniqueness part of the result.


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
(a) Suppose $\theta \in R$. Show that both $(cos \theta, sin \theta), (-sin \theta, cos \theta)$ and $(cos \theta, sin \theta), (sin \theta, -cos \theta)$ are orthonormal bases of $R^2$.

$$||(cos\theta, sin\theta)||^2 = cos^2 \theta + sin^2 \theta = 1$$

$$||(-sin\theta, cos\theta)||^2 = (-sin\theta)^2 + cos^2 \theta = 1$$

$$<(cos\theta, sin\theta), (-sin\theta, cos\theta)> = - cos\theta sin\theta + sin\theta cos\theta = 0$$

Similarly,

$$||(sin\theta, -cos\theta)||^2 = sin^2\theta + (-cos \theta)^2 = 1$$

$$<(cos\theta, sin\theta), (sin\theta, -cos\theta)> = cos\theta sin\theta - sin\theta cos\theta = 0$$

(b) Show that each orthonormal basis of $R^2$ is of the form given by one of the two possibilities in (a).

Let $e_1, e_2$ be an orthonormal basis of $R^2$. Suppose $e_1 = (x_1, y_1)$. Then $x_1^2 + y_1^2 = 1$, we can rewrite as $e_1 = (cos\theta, sin\theta)$. 

Suppose $e_2 = (x_2, y_2)$. Then $<e_1,e_2> = x_2 cos\theta + y_2 \sin\theta = 0$. So $x_2 = -sin\theta, y_2=cos\theta$ or $x_2 = sin\theta, y_2=-cos\theta$.


#### (3) Suppose $e_1,...,e_m$ is an orthonormal list in $V$ and $v \in V$. Prove that $||v||^2 = |<v,e_1>|^2 + ... + |<v,e_m>|^2 \iff v \in span (e_1,...,e_m)$.
$\Rightarrow$
Suppose $||v||^2 = |<v,e_1>|^2 + ... + |<v,e_m>|^2$.

Based on 6.26, we can decompose 

$$v = <v,e_1>e_1 + ... + <v,e_m>e_m + v - <v,e_1>e_1 - ... - <v,e_m>e_m$$

Let $u = <v,e_1>e_1 + ... + <v,e_m>e_m$ and $w = v - <v,e_1>e_1 - ... - <v,e_m>e_m$.

Then $<w,u> = 0$. By the Pythagorean theorem, 

$$||v||^2 = ||u||^2 + ||w||^2$$

By 6.24, $||u||^2 = |<v,e_1>|^2 + ... + |<v,e_m>|^2$.

By hypothesis, $||v||^2 = ||u||^2$, which implies $||w||^2 = 0$. 

Thus $w = 0$, and we conclude 

$$v = <v,e_1>e_1 + ... + <v,e_m>e_m \in span(e_1,...,e_m)$$

$\Leftarrow$
Suppose $v \in span(e_1,...,e_m)$. Then $v = a_1 e_1 + ... + a_m e_m$ for some $a_1,...,a_m$.

$$||v||^2 = <a_1 e_1 + ... + a_m e_m, a_1 e_1 + ... + a_m e_m> = |a_1|^2 + ... + |a_m|^2$$

For $k=1,...,m$, $<v,e_k> = a_k <e_k,e_k> = a_k$. Therefore 

$$||v||^2 = |<v,e_1>|^2 + ... + |<v,e_m>|^2$$


#### (4) Suppose $n$ is a positive integer. Prove ethat $1/\sqrt{2\pi}, cos x / sqrt{\pi}$


#### (6) Suppose $e_1,...,e_n$ is an orthonormal basis of $V$. 
(a) Prove that if $v_1,...,v_n$ are vectors in $V$ such that $||e_k - v_k|| < 1/\sqrt{n}$ for each $k$, then $v_1,...,v_n$ is a basis of $V$.

Suppose $a_1 v_1 + ... + a_n v_n = 0$ for some $a_1,...,a_n \in F$. We can rewrite

$$a_1 (e_1 + v_1 - e_1) + ... + a_n (e_n + v_n - e_n) = 0$$

$$a_1 e_1 + ... + a_n e_n = - (a_1 (v_1-e_1) + ... + a_n(v_n-e_n))$$

Taking the norm of both sides,

$$||a_1 e_1 + ... + a_n e_n||^2 = |a_1|^2 + ... + |a_n|^2$$

$$||a_1 (v_1-e_1) + ... + a_n (v_n-e_n)||^2 \leq |a_1|^2 ||v_1-e_1||^2 + ... + |a_n|^2 ||v_n-e_n||^2 \leq (|a_1|^2+...+|a_n|^2) (||v_1-e_1||^2+...+||v_n-e_n||^2)$$

where the first inequality follows from the triangle inequality, and the second inequality follows from the Cauchy-Schwartz inequality.

$$(|a_1|^2+...+|a_n|^2) (||v_1-e_1||^2+...+||v_n-e_n||^2) < (|a_1|^2+...+|a_n|^2) (1/n+...+1/n) = (|a_1|^2+...+|a_n|^2)$$

$$||a_1 (v_1-e_1) + ... + a_n (v_n-e_n)||^2 < |a_1|^2 + ... + |a_n|^2$$

which is a contradiction.

Therefore $|a_1|^2 + ... + |a_n|^2 = 0$, hence $a_1=...=a_n = 0$. We conclude $v_1,...,v_n$ is a linearly independent list of vectors of the right length, therefore it is a basis of $V$.


(b) Show that there exist $v_1,...,v_n \in V$ such that $||e_k - v_k|| \leq 1/\sqrt{n}$ for each $k$, but $v_1,...,v_n$ is not linearly independent.





# 6C Orthogonal Complements and Minimization Problems

### 6.46 Definition: orthogonal complement
If $U$ is a subset of $V$, then the orthogonal complement of $U$, denoted by $U^{\perp}$, is the set of all vectors in $V$ that are orthogonal to every vector in $U$:

$$U^{\perp} = \\{v \in V: <u,v>=0 for every u \in U\\}$$


