Linear Algebra Done Right - Chapter 3 Linear Maps <br>
3E Products and Quotients of Vector Spaces
================
Rosie Sun <br>
2026-04-02


### 3.87 Definition: product of vector spaces
Suppose $V_1, ..., V_m$ are vector spaces over $F$. 

The product $V_1 \times ... \times V_m$ is defined by

$$V_1 \times ... \times V_m = \\{(v_1, ..., v_m): v_1 \in V_1, ..., v_m \in V_m \\}$$

Addition on $V_1 \times ... \times V_m$ is defined by

$$(u_1, ..., u_m) + (v_1 + ... + v_m) = (u_1 + v_1, ..., u_m + v_m)$$

Scalar multiplication on $V_1 \times ... \times V_m$ is defined by

$$\lambda (v_1, ..., v_m) = (\lambda v_1, ..., \lambda v_m)$$


### 3.89
Suppose $V_1, ..., V_m$ are vector spaces over $F$. Then $V_1 \times ... \times V_m$ is a vector space over $F$.


### 3.92
Suppose $V_1, ..., V_m$ are finite-dimensional vector spaces. Then $V_1, ..., V_m$ is finite-dimensional and 

$$dim (V_1 \times ... \times V_m) = dim V_1 + ... + dim V_m .$$


### 3.93
Suppose that $V_1, ..., V_m$ are subspaces of $V$. Define a linear map $\Gamma: V_1 \times ... \times V_m \rightarrow V_1 + ... + V_m$ by

$$\Gamma(v_1, ..., v_m) = v_1 + ... + v_m .$$

Then $V_1 + ... + V_m$ is a direct sum if and only if $\Gamma$ is injective.

Proof:

By 3.15, $\Gamma$ is injective if and only if the only way to write 0 as a sum $v_1 + ... + v_m$, where each $v_k \in V_k$, is by taking each $v_k$ equal to 0. 

Thus 1.45 shows that $\Gamma$ is injective if and only if $V_1 + ... + V_m$ is a direct sum, as desired.


### 3.94
Suppose $V$ is finite-dimensional and $V_1, ..., V_m$ are subspaces of $V$. Then $V_1 + ... + V_m$ is a direct sum if and only if 

$$dim (V_1 + ... + V_m) = dim V_1 + ... + dim V_m .$$

Proof:

The map $\Gamma$ in 3.93 is surjective, since every $v_1 + ... + v_m \in V_1 + ... + V_m$ can be written as $\Gamma(v_1, ..., v_m)$. 

Thus by 3.21,

$$dim (V_1 \times ... \times V_m) = dim null \Gamma + dim range \Gamma = dim null \Gamma + dim (V_1 + ... + V_m)$$

$\Gamma$ is injective if and only if 

$$dim (V_1 + ... + V_m) = dim (V_1 \times ... \times V_m).$$

Combining 3.93 and 3.92 shows that $V_1 + ... + V_m$ is a direct sum if and only if 

$$dim (V_1 + ... V_m) = dim V_1 + ... + dim V_m,$$

as desired.


### 3.95 Notation
Suppose $v \in V$ and $U \subseteq V$. Then $v + U$ is the subset of $V$ defined by

$$v + U = \\{v + u: u \in U\\}$$


### 3.97 Definition: translate
For $v \in V$ and $U$ a subset of $V$, the set $v + U$ is said to be a translate of $U$.


### 3.99 Definition: quotient space
Suppose $U$ is a subspace of $V$. Then the quotient space $V/U$ is the set of all translates of $U$. Thus 

$$V/U = \\{v + U: v \in V\\}.$$


### 3.101
Suppose $U$ is a subspace of $V$ and $v, w \in V$. Then

$$v - w \in U \iff v + U = w + U \iff (v + U) \cap (w + U) \neq \emptyset.$$

Proof:

First suppose $v - w \in U$. If $u \in U$, then 

$$v + u = w + ((v - w) + u) \in w + U.$$

Thus $v + U \subseteq w + U$. Similarly, 

$$w + u = v - ((v - w) - u) \in v + U$$

$w + U \subseteq v + U$. Thus $v + U = w + U$, completing the proof that $v - w \in U$ implies $v + U = w + U$.

The equation $v + U = w + U$ implies that $(v + U) \cap (w + U) \neq \emptyset$.

Now suppose $(v + U) \cap (w + U) \neq \emptyset$. Thus there exist $u_1, u_2 \in U$ such that 

$$v + u_1 = w + u_2.$$

Thus $v - w = u_2 - u_1$. Hence $v - w \in U$, showing that $(v + U) \cap (w + U) \neq \emptyset$ implies $v - w \in U$, which completes the proof.


### 3.102 Definition: addition and scalar multiplication on $V/U$
Suppose $U$ is a subspace of $V$. Then addition and scalar multiplication are defined on $V/U$ by

$$(v + U) + (w + U) = (v + w) + U$$

$$\lambda (v + U) = (\lambda v) + U$$

for all $v, w \in V$ and all $\lambda \in F$.


### 3.103 
Suppose $U$ is a subspace of $V$. Then $V/U$, with the operations of addition and scalar multiplication as defined above, is a vector space.

Proof:

The potential problem with the definitions above of addition and scalar multiplication on $V/U$ is that the representation of a translate of $U$ is not unique. Specifically, suppose $v_1, v_2, w_1, w_2 \in V$ are such that

$$v_1 + U = v_2 + U$$

and 

$$w_1 + U = w_2 + U.$$

To show that the definition of addition on $V/U$ given above makes sense, we must show that $(v_1 + w_1) + U = (v_2 + w_2) + U$.

By 3.101, we have

$$v_1 - v_2 \in U$$

and 

$$w_1 - w_2 \in U.$$

Because $U$ is a subspace of $V$ and is thus closed under addition, this implies that 

$$(v_1 - v_2) + (w_1 - w_2) \in U.$$ 

Thus

$$(v_1 + w_1) - (v_2 + w_2) \in U.$$

Using 3.101 again, we see that 

$$(v_1 + w_1) + U = (v_2 + w_2) + U,$$

as desired. Thus the definition of addition on $V/U$ makes sense.

Similarly, suppose $\lambda \in F$. We are still assuming that $v_1 + U = v_2 + U$. 

Because $U$ is a subspace of $V$ and thus is closed under scalar multiplication, we have 

$$\lambda (v_1 - v_2) \in U.$$

Thus 

$$\lambda v_1 - \lambda v_2 \in U.$$

Hence 3.1.1 implies that 

$$(\lambda v_1) + U = (\lambda v_2) + U.$$

Thus the definition of scalar multiplication on $V/U$ makes sense.

Note that the additive identity of $V/U$ is $0 + U$ (which equals $U$) and that the additive inverse of $v + U$ is $(-v) + U$.


### 3.104 Definition: quotient map
Suppose $U$ is a subspace of $V$. The quotient map $\pi: V \rightarrow V/U$ is the linear map defined by 

$$\pi(v) = v + U$$

for each $v \in V$.


### 3.105 
Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$. Then 

$$dim V/U = dim V - dim U.$$

Proof:

Let $\pi$ denote the quotient map from $V$ to $V/U$. 

If $v \in V$, then $v + U = 0 + U$ if and only if $v \in U$ by 3.101, which implies that $null \pi = U$. 

The definition of $\pi$ implies $range \pi = V/U$. 

The fundamental theorem of linera maps (3.21) now implies 

$$dim V = dim null \pi + dim range \pi = dim U + dim V/U,$$ 

which gives the desired result. 


### 3.106 Notation
Suppose $T \in L(V, W)$. Define $\tilde{T}: V/(null T) \rightarrow W$ by

$$\tilde{T} (v + null T) = Tv.$$

To show that the definition of $\tilde{T}$ makes sense, suppose $u, v \in V$ are such that $u + null T = v + null T$. By 3.101, we have $u - v \in null T$. Thus $T(u - v) = 0$. Hence $Tu = Tv$. Thus the definition of $\tilde{T}$ indeed makes sense.


### 3.107
Suppose $T \in L(V, W)$. Then 

(a) $\tilde{T} \circ \pi = T$, where $\pi$ is the quotient map of $V$ onto $V/(null T)$;

(b) $\tilde{T}$ is injective;

(c) $range \tilde{T} = range T$;

(d) $V/(null T)$ and $range T$ are isomorphic vector spaces.

Proof:

(a) If $v \in V$, then 

$$(\tilde{T} \circ \pi)(v) = \tilde{T} (\pi(v)) = \tilde{T} (v + null T) = Tv$$

as desired.

(b) Suppose $v \in V$ and $\tilde{T}(v + null T) = 0$. Then $Tv = 0$. Thus $v \in null T$.  Hence 3.101 implies that 

$$v + null T = 0 + null T.$$ 

This implies that $null \tilde{T} = \\{0 + null T \\}$. Hence $\tilde{T}$ is injective, as desired.

(c) The definition of $\tilde{T}$ shows that $range \tilde{T} = range T$.

(d) Now (b) and (c) imply that if we think of $\tilde{T}$ as mapping into $range T$, then $\tilde{T}$ is an isomorphism from $V/ (null T)$ onto $range T$.




## Exercises

### (6) Suppose that $v, x$ are vectors in $V$ and that $U, W$ are subspaces of $V$ such that $v + U = x + W$. Prove that $U = W$.

Suppose $u \in U$. Then $v + u \in v + U$. 

Since $v + U = x + W$, $v + u \in x + W$. Then $v + u = x + w$ for some $w \in W$. We have

$$u = (x - v) + w.$$

We also have $v + 0 \in v + U$ and $v + 0 \in x + W$. So $v + 0 = x + w_1$ for some $w_1 \in W$. Thus $v = x + w_1$, and $v - x = w_1$. Hence $x - v \in W$. 

Since $W$ is a subspace, $u = (x - v) + w \in W$, showing $U \subseteq W$.

Similarly, $W \subseteq U$ (by switching $v$ and $x$). Hence we conclude $U = W$.


### (7) Let $U = \\{(x, y, z) \in R^3: 2x + 3y + 5z = 0\\}$. Suppose $A \subseteq R^3$. Prove that $A$ is a translate of $U$ if and only if there exists $c \in R$ such that $A = \\{(x, y, z) \in R^3: 2x + 3y + 5z = c\\}$.

$\Rightarrow$
Suppose $A$ is a translate of $U$. 

Then $A = a + U$ for some $a = (a_1, a_2, a_3) \in R^3$. Consider $c = 2a_1 + 3a_2 + 5a_3$.

$$
\begin{aligned}
A &= a + U \\
    &= \\{(x, y, z) \in R^3: (x - a_1, y - a_2, z - a_3) \in U\\} \\
    &= \\{(x, y, z) \in R^3: 2(x-a_1) + 3(y-a_2) + 5(z-a_3) = 0 \\} \\
    &= \\{(x, y, z) \in R^3: 2x + 3y + 5z = c \\}
\end{aligned}
$$

$\Leftarrow$
Suppose there exists $c \in R$ such that $A = \\{(x, y, z) \in R^3: 2x + 3y + 5z = c\\}$.

Consider $a = \frac{1}{10} (c, c, c) \in R^3$.

$$
\begin{aligned}
A &= \\{(x, y, z) \in R^3: 2x + 3y + 5z - c = 0 \\} \\
    &= \\{(x, y, z) \in R^3: 2(x - \frac{1}{10} c) + 3(y - \frac{1}{10} c) + 5(z - \frac{1}{10} c) = 0 \\} \\
    &= \\{(x, y, z) \in R^3: (x - \frac{1}{10} c, y - \frac{1}{10} c, z - \frac{1}{10} c) \in U \\} \\
    &= a + U
\end{aligned}
$$

Thus $A$ is a translate of $U$.



### (8) 
#### (a) Suppose $T \in L(V, W)$ and $c \in W$. Prove that $\\{x \in V: Tx = c\\}$ is either the empty set or is a translate of $null T$.

We have 

$$
\begin{aligned}
v + null T 
    &= \\{x \in V: (x - v) \in null T \\} \\
    &= \\{x \in V: T(x - v) = 0 \\} \\
    &= \\{x \in V: Tx = Tv \\}
\end{aligned}
$$

If there exists $v \in V$ such that $Tv = c$, then $\\{x \in V: Tx = c\\}$ is a translate of $null T$. Otherwise it is the empty set.


#### (b) Explain why the set of solutions to a system of linear equations such as 3.27 is either the empty set or is a translate of some subspace of $F^n$.

A system of linear equations is a linear map $T$ from $F^n$ to $F^m$, applied to a vector $x \in F^n$, with some fixed $c \in F^m$. By (a), the solution set is either the empty set or $null T$ (which is a subspace of $F^n$).



### (9) Prove that a nonempty subset $A$ of $V$ is a translate of some subspace of $V$ if and only if $\lambda v + (1 - \lambda) w \in A$ for all $v, w \in A$ and all $\lambda \in F$.

$\Rightarrow$
Suppose $U$ is a subspace of $V$ and suppose $A$ is a translate of $U$. 

Then $A = a + U$ for some $a \in V$. Suppose $v, w \in A$. Then $v = a + u_1$ and $w = a + u_2$ for some $u_1, u_2 \in U$. 

Since $U$ is a subspace, $\lambda u_1 + (1 - \lambda) u_2 \in U$. We have

$$
\begin{aligned}
a + (\lambda u_1 + (1 - \lambda) u_2) &\in a + U \\
\lambda (a + u_1) + (1-\lambda) (a + u_2) &\in a + U \\
\lambda v + (1 - \lambda) w &\in A
\end{aligned}
$$

$\Leftarrow$
Suppose $\lambda v + (1 - \lambda) w \in A$ for all $v, w \in A$ and all $\lambda \in F$.

Define $U = \\{v - a: v \in A\\}$. We want to show that $U$ is a subspace of $V$.

First, $0 \in U$ beacuse $0 = a - a \in U$. 

Next we want to show that $U$ is closed under scalar multiplication. 

Suppose $u \in U, \lambda \in F$. Then $u = v - a$ for some $v \in A$. Apply the hypothesis to our choice of $\lambda, v, and w=a$. We have

$$\lambda v + (1 - \lambda) a = \lambda (u + a) + (1 - \lambda)a = \lambda u + a \in A$$

Hence $\lambda u = \lambda u + a - a \in U$.

Finally we want to show that $U$ is closed under addition.

Suppose $u_1, u_2 \in U$. Then $u_1 = v_1 - a, u_2 = v_2 - a$ for some $v_1, v_2 \in A$. Apply the hypothesis to $\lambda = 1/2, v_1, v_2$. We have

$$\frac{1}{2} v_1 + \frac{1}{2} v_2 \in A$$ 

Thus 

$$\frac{1}{2} v_1 + \frac{1}{2} v_2 - a = \frac{1}{2} (u_1 + u_2 + 2a) - a = \frac{1}{2} (u_1 + u_2) \in U$$

Since $U$ is closed under scalar multiplication, $u_1 + u_2 \in U$.

We have shown that $U$ is a subspace of $V$ and $A = \\{a + U\\}$, thus $A$ is a translate of $U$.



### (10) Suppose $A_1 = v + U_1$ and $A_2 = w + U_2$ for some $v, w \in V$ and some subspaces $U_1, U_2$ of $V$. Prove that the intersection $A_1 \cap A_2$ is either a translate of some subspace of $V$ or is the empty set.

If $A_1 \cap A_2$ is an empty set then we are done. 

Thus suppose $A_1 \cap A_2$ is not empty and $y \in A_1 \cap A_2$. Then $y = v + u_1$ for some $u_1 \in U_1$ and $y = w + u_2$ for some $u_2 \in U_2$. We want to show that 

$$A_1 \cap A_2 = y + (U_1 \cap U_2).$$ 

Note that $U_1 \cap U_2$ is a subspace of $V$ (Chapter 1C, exercise 10).

First suppose $x \in y + (U_1 \cap U_2)$. Then $x = y + u_3$ where $u_3 \in U_1 \cap U_2$. Since $y = v + u_1$, we have 

$$x = y + u_3 = v + u_1 + u_3 = v + (u_1 + u_3) \in v + U_1 = A_1.$$

Similarly, since $y = w + u_2$, we have

$$x = y + u_3 = w + u_2 + u_3 = w + (u_2 + u_3) \in w + U_2 = A_2.$$

Hence $x \in A_1 \cap A_2$.

Next suppose $x \in A_1 \cap A_2$. Then $x = v + u'_1$ for some $u'_1 \in U_1$ and $x = w + u'_2$ for some $u'_2 \in U_2$. We have

$$x - y = (v + u'_1) - (v + u_1) = u'_1 - u_1 \in U_1,$$

$$x - y = (v + u'_2) - (v + u_2) = u'_2 - u_2 \in U_2.$$

Thus $x - y \in U_1 \cap U_2$. Hence 

$$x = y + (x - y) \in y + (U_1 \cap U_2).$$

We conclude that $A_1 \cap A_2$ is either an empty set or a translate of a subspace of $V$.



### (12) Suppose $v_1, ..., v_m \in V$. Let $A = \\{\lambda_1 v_1 + ... + \lambda_m v_m: \lambda_1, ..., \lambda_m \in F, \lambda_1 + ... + \lambda_m = 1\\}$.

#### (a) Prove that $A$ is a translate of some subspace of $V$.

Suppose $w \in A$. Then we have

$$
\begin{aligned}
w &= \lambda_1 v_1 + ... + \lambda_m v_m \\
    &= \lambda_1 v_1 + ... + \lambda_{m-1} v_{m-1} + (1 - \lambda_1 - ... - \lambda_{m-1}) v_m \\
    &= \lambda_1 v_1 + ... + \lambda_{m-1} v_{m-1} + v_m - \lambda_1 v_m - ... - \lambda_{m-1} v_m \\
    &= v_m + \lambda_1 v_1 - \lambda_1 v_m + ... + \lambda_{m-1} v_{m-1} - \lambda_{m-1} v_m \\
    &= v_m + \lambda_1 (v_1 - v_m) + ... + \lambda_{m-1} (v_{m-1} - v_m)
\end{aligned}
$$

Define 

$$U = \\{\lambda_1 (v_1 - v_m) + ... + \lambda_{m-1} (v_{m-1} - v_m): \lambda_1, ..., \lambda_{m-1} \in F\\}.$$ 

Since $U = span( (v_1 - v_m), ..., (v_{m-1} - v_m))$, by 2.6, $U$ is a subspace of $V$.

Thus $A \subseteq v_m + U$.

Suppose $w \in v_m + U$. Then for some $\lambda_1, ..., \lambda_{m-1} \in F$, we have

$$
\begin{aligned}
w &= v_m + \lambda_1 (v_1 - v_m) + ... + \lambda_{m-1} (v_{m-1} - v_m) \\
    &= \lambda_1 v_1 - \lambda_1 v_m + ... + \lambda_{m-1} v_{m-1} - \lambda_{m-1} v_m + v_m \\
    &= \lambda_1 v_1 + ... + \lambda_{m-1} v_{m-1} + (1 - \lambda_1 - ... - \lambda_{m-1}) v_m \\
    &= \lambda_1 v_1 + ... + \lambda_{m-1} v_{m-1} + \lambda_m v_m
\end{aligned}
$$

Thus $&w \in A$ and $v_m + U \subseteq A$. 

Hence we conclude $A = v_m + U$, i.e., $A$ is a translate of subspace $U$ of $V$. 


#### (b) Prove that if $B$ is a translate of some subspace of $V$ and $\\{v_1, ..., v_m\\} \subseteq B$, then $A \subseteq B$.

Suppose $w \in A$. Then $w \in v_m + U$, from part (a). 

Suppose $B = b + Y$ for some $b \in V$ and some subspace $Y$ in $V$. Then $v_i \in B$ for $i = 1,...,m$ and $v_i = b + y_i$ for some $y_i \in Y$.

Then for some $\lambda_1, ..., \lambda_{m-1} \in F$, we have 

$$
\begin{aligned}
w &= v_m + \lambda_1 (v_1 - v_m) + ... + \lambda_{m-1} (v_{m-1} - v_m) \\
    &= (b + y_m) + \lambda_1 (b + y_1 - b - y_m) + ... + \lambda_{m-1} (b + y_{m-1} - b - y_m) \\
    &= b + y_m + \lambda_1 (y_1 - y_m) + ... + \lambda_{m-1} (y_{m-1} - y_m)
\end{aligned}
$$

Since $Y$ is a subspace and is closed under addition and scalar multiplication, we have $y_m \in Y, \lambda_1 (y_1 - y_m) \in Y, ..., \lambda_{m-1} (y_{m-1} - y_m) \in Y$, and $y_m + \lambda_1 (y_1 - y_m) + ... + \lambda_{m-1} (y_{m-1} - y_m) \in Y$.

Thus $w \in b + Y = B$.

Hence we conclude $A \subseteq B$.


#### (c) Prove that $A$ is a translate of some subspace of $V$ of dimension less than m.

From part (a), we have $A = v_m + U$, where $U = span( (v_1 - v_m), ..., (v_{m-1} - v_m))$. 

By definition $(v_1 - v_m), ..., (v_{m-1} - v_m)$ spans $U$. From 2.22, there are at most $m-1$ linearly independent vectors in this list. Thus $dim U \leq m-1 < m$.



### (13) Suppose $U$ is a subspace of $V$ such that $V/U$ is finite-dimensional. Prove that $V$ is isomorphic to $U \times (V/U)$.

Suppose $w_1 + U, ..., w_m + U$ is a basis of $V/U$. Define $W = span(w_1, ..., w_m)$. 

We want to show that $V$ is equal to $U \oplus W$ which is isomorphic to $U \times W$ which is isomorphic to $U \times V/U$.

First we want to show that $V = U \oplus W$. 

Suppose $v \in V$. Then $v + U \in V/U$. We can write 

$$v + U = a_1 (w_1 + U) + ... + a_m (w_m + U) = (a_1 w_1 + ... + a_m w_m) + U$$

for some $a_1, ..., a_m \in F$. From 3.101, $v - (a_1 w_1 + ... + a_m w_m) \in U$. Thus 

$$v = a_1 w_1 + ... + a_m w_m + (v - (a_1 w_1 + ... + a_m w_m))$$

where $a_1 w_1 + ... + a_m w_m \in W$ and $v - (a_1 w_1 + ... + a_m w_m) \in U$. Therefore $V = U + W$. 

Suppose $v \in U \cap W$. Then $v = b_1 w_1 + ... + b_m w_m$ for some $b_1, ..., b_m \in F$. Since $v \in U$, $v + U = 0 + U$ by 3.101. We have

$$
\begin{aligned}
v + U &= (b_1 w_1 + ... + b_m w_m) + U \\
    &= b_1 (w_1 + U) + ... + b_m (w_m + U) \\
    &= 0 + U
\end{aligned}
$$

Since $w_1 + U, ..., w_m + U$ is a basis of $V/U$, $b_1 = ... = b_m = 0$. Hence $v = 0$, and $U \cap W = \\{0\\}$.

Since $V = U + W$ and $U \cap W = \\{0\\}$, $V = U \oplus W$ by 1.46.

Consider the linear map $\Gamma: U \times W \rightarrow U + W$. 

$\Gamma$ is surjective by definition. By 3.93, since $U + W$ is a direct sum, $\Gamma$ is injective. Thus $\Gamma$ is an isomorphism from $U \times W$ onto $U + W$. 

Consider the linear map $\pi: W \rightarrow V/U$. Suppose $w + U \in V/U$. Then 

$$w + U = c_1 (w_1 + U) + ... + c_m (w_m + U) = (c_1 w_1 + ... + c_m w_m) + U = \pi(c_1 w_1 + ... + c_m w_m)$$ 

for some $c_1, ..., c_m \in F$, $c_1 w_1 + ... + c_m w_m \in W$. Thus $\pi$ is surjective. Since $null \pi = \\{0\\}$ (shown previously), $\pi$ is injective. Thus $\pi$ is an isomorphism from $W$ onto $V/U$. 

Define map $T: U \times W \rightarrow U \times (V/U)$ by $T(u, w) = (u, \pi(w))$. Then $T$ is an isomorphism from $U \times W$ onto $U \times (V/U)$.

Hence $V$ is isomorphic with $U \times V/U$.



### (14) Suppose $U$ and $W$ are subspaces of $V$ and $V = U \oplus W$. Suppose $w_1, ..., w_m$ is a basis of $W$. Prove that $w_1 + U, ..., w_m + U$ is a basis of $V/U$.

We have 

$$dim V/U = dim V - dim U = dim W = m$$ 

from 3.105 and 3.94. 

Since $w_1 + U, ..., w_m + U$ is a list of length $m$, we just need to show that the list is linearly independent in $V/U$, by 2.38.

Suppose $a_1 (w_1 + U) + ... + a_m (w_m + U) = 0 + U$ for some $a_1, ..., a_m \in F$. Then 

$$a_1 (w_1 + U) + ... + a_m (w_m + U) = (a_1 w_1 + ... + a_m w_m) + U = 0 + U.$$

Thus $a_1 w_1 + ... + a_m w_m \in U$ by 3.101.

Since $w_1, ..., w_m$ is a basis of $W$, $a_1 w_1 + ... + a_m w_m \in W$. 

Thus $a_1 w_1 + ... + a_m w_m \in U \cap W$. Since $U$ and $W$ are direct sums, $U \cap W = \\{0\\}$, by 1.46. Thus $a_1 w_1 + ... + a_m w_m = 0$, implying $a_1 = ... = a_m = 0$.

Hence $w_1 + U, ..., w_m + U$ is linearly independent and is a basis of $V/U$.



### (15) Suppose $U$ is a subspace of $V$ and $v_1 + U, ..., v_m + U$ is a basis of $V/U$ and $u_1, ..., u_n$ is a basis of $U$. Prove that $v_1, ..., v_m, u_1, ..., u_n$ is a basis of $V$.

Since $dim V = dim U + dim V/U = n + m$, and the length of the list $v_1, ..., v_m, u_1, ..., u_n$ equals $n + m$, we just need to show that $v_1, ..., v_m, u_1, ..., u_n$ is linearly independent in $V$, by 2.38.

Suppose 

$$a_1 v_1 + ... + a_m v_m + b_1 u_1 + ... + b_n u_n = 0$$

for some $a_1, ..., a_m, b_1, ..., b_n \in F$. 

Applying the quotient map $\pi: V \rightarrow V/U$ to both sides, we have

$$
\begin{aligned}
\pi(a_1 v_1 + ... + a_m v_m + b_1 u_1 + ... + b_n u_n) &= \pi(0) \\
(a_1 v_1 + ... + a_m v_m + b_1 u_1 + ... + b_n u_n) + U &= 0 + U \\
(a_1 v_1 + U) + ... + (a_m v_m + U) + (b_1 u_1 + U) + ... + (b_n u_n + U) &= 0 + U \\
a_1 (v_1 + U) + ... + a_m (v_m + U) + (0 + U) + ... + (0 + U) &= 0 + U \\
a_1 (v_1 + U) + ... + a_m (v_m + U) &= 0 + U
\end{aligned}
$$

Since $v_1 + U, ..., v_m + U$ is a basis of $V/U$, $a_1 = ... = a_m = 0$. Thus we have $b_1 u_1 + ... + b_n u_n = 0$. Since $u_1, ..., u_n$ is a basis of $U$, $b_1 = ... = b_n = 0$. 

Hence $v_1, ..., v_m, u_1, ..., u_n$ is linearly independent, and we conclude that it is a basis of $V$.



### (16) Suppose $\phi \in L(V, F)$ and $\phi \neq 0$. Prove that $dim (V / null \phi) = 1$.

Since $\phi \neq 0$, there exists $v \in V$ such that $\phi(v) \neq 0$. Then $dim (range \phi) \geq 1$. Since $range \phi \subseteq F$, $dim (range \phi) \leq dim F = 1$. Thus $dim (range \phi) = 1$.

From 3.107, $V / (null \phi)$ and $range \phi$ are isomorphic. Thus 

$$dim (V / (null \phi)) = dim range \phi = 1.$$



### (17) Suppose $U$ is a subspace of $V$ such that $dim V/U = 1$. Prove that there exists $\phi \in L(V, F)$ such that $null \phi = U$.

Let $w_1 + U$ be a basis of $V/U$. Define $W = span(w_1)$. We want to show that $V = U \oplus W$ and construct a $\phi: V \rightarrow F$. 

Suppose $v \in V$. Then $v + U \in V/U$, and we can write 

$$v + U = a_1 (w_1 + U) = a_1 w_1 + U$$ 

for some $a_1 \in F$. Then $v - a_1 w_1 \in U$ by 3.101. Thus 

$$v = a_1 w_1 + (v - a_1 w_1)$$

where $a_1 w_1 \in W$ and $v - a_1 w_1 \in U$. Hence $V = W + U$. 

Suppose $v \in U \cap W$. Then $v \in W$ and $v = b_1 w_1$ for some $b_1 \in F$. Since $v \in U$, by 3.101 we have

$$v + U = b_1 w_1 + U = b_1 (w_1 + U) = 0 + U.$$

Since $w_1 + U$ is a basis of $V/U$, $b_1 = 0$. Thus $v = 0$, and $U \cap W = \\{0\\}$. 

Since $V = U + W$ and $U \cap W = \\{0\\}$, $V = U \oplus W$ by 1.46.

Define $\phi \in L(V, F)$ such that $\phi(w_1) = 1$ and $\phi(u) = 0$ for all $u \in U$. Every $v \in V$ can be uniquely written as $v = u + a_1 w_1$ for some $a_1 \in F$. Thus $\phi$ is well-defined and $\phi(v) = a_1$. 

Suppose $v \in null \phi$. Then $\phi(v) = 0$. Since $v = u + a_1 w_1$ for some $a_1 \in F$, $\phi(v) = \phi(u + a_1 w_1) = \phi(u) + a_1 = 0 + a_1$, which implies that $a_1 = 0$. Then $v = u + 0w \in U$. 

Suppose $v \in U$. Then $\phi(v) = \phi(u + 0w) = 0$. Thus $v \in null \phi$.

Thus $null \phi = U$.



### (18) Suppose that $U$ is a subspace of $V$ such that $V/U$ is finite-dimensional. 

#### (a) Show that if $W$ is a finite-dimensional subspace of $V$ and $V = U + W$, then $dim W \geq dim V/U$.



#### (b) Prove that there exists a finite-dimensional subspace $W$ of $V$ such that $dim W = dim V/U$ and $V = U \oplus W$.

