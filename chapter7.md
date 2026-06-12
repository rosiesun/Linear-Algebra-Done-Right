Linear Algebra Done Right - Chapter 7 <br> 
Operators on Inner Product Spaces
================
Rosie Sun <br> 
2026-06-01


# 7A Self-Adjoint and Normal Operators

### 7.1 Definition: adjoint
Suppose $T \in L(V, W)$. The adjoint of $T$ is the function $T^*: W \rightarrow V$ such that 

$$\langle Tv, w\rangle  = \langle v, T^* w\rangle $$

for every $v \in V$ and every $w \in W$.

### 7.4
If $T \in L(V, W)$, then $T^* \in L(W, V)$.

Proof:

### 7.5
Suppose $T \in L(V, W)$. Then

(a) $(S+T)^* = S^* + T^*$ for all $S \in L(V, W)$;

(b) $(\lambda T)^* = \overline{\lambda} T^*$ for all $\lambda \in F$;

(c) $(T^*)^* = T$;

(d) $(ST)^* = T^* S^*$ for all $S \in L(W, U)$ (here $U$ is a finite-dimensional inner product space over $F$);

(e) $I^* = I$, where $I$ is the identity operator on $V$;

(f) if $T$ is invertible, then $T^*$ is invertible and $(T^*)^{-1} = (T^{-1})^*$.

Proof:

### 7.6
Suppose $T \in L(V, W)$. Then 

(a) $null T^* = (range T)^{\perp}$;

(b) $range T^* = (null T)^{\perp}$;

(c) $null T = (range T^*)^{\perp}$;

(d) $range T = (null T^*)^{\perp}$.

Proof:

### 7.7 Definition: conjugate transpose
The conjugate transpose of an m-by-n matrix $A$ is the n-by-m matrix $A^*$ obtained by interchanging the rows and columns and then taking the complex conjugate of each entry. In other words, if $j \in \\{1,...,n\\}$ and $k \in \\{1,...,m\\}$, then 

$$(A^*)_{j, k} = \overline{A_{k, j}}$$

### 7.9


### 7.10 Definition: self-adjoint
An operator $T \in L(V)$ is called self-adjoint if $T = T^*$.

### 7.12
Every eigenvalue of a self-adjoint operator is real.

Proof:

### 7.13
Suppose $V$ is a complex inner product space and $T \in L(V)$. Then

$\langle Tv, v\rangle  = 0$ for every $v \in V$ $\iff T = 0$.

Proof:

### 7.14


### 7.16

### 7.18

### 7.20

### 7.21

### 7.22

### 7.23





## Exercises

### (1) Suppose $n$ is a positive integer. Define $T \in L(V)$ by $T(z_1, ..., z_n) = (0, z_1, ..., z_{n-1}$. Find a formula for $T^* (z_1, ..., z_n)$.

Suppose $(z_1, ..., z_n), (w_1, ..., w_n) \in F^n$. We have 

$$
\begin{aligned}
\langle T(z_1, ..., z_n), (w_1, ..., w_n) \rangle 
    &= \langle (0, z_1, ..., z_{n-1}), (w_1, ..., w_n) \rangle \\
    &= 0 + z_1 \overline{w_2} + ... + z_{n-1} \overline{w_n} \\
    &= \langle (z_1, ..., z_n), (w_2, ..., w_n, 0) \rangle
\end{aligned}
$$

Thus the adjoint of $T$ is the forward shift

$$T^* (w_1, ..., w_n) = (w_2, ..., w_n, 0).$$


### (2) Suppose $T \in L(V, W)$. Prove that $T = 0 \iff T^* = 0 \iff T^* T = 0 \iff T T^* = 0$.

$T = 0 \rightarrow T^* = 0$

Suppose $T = 0$. Then $Tv = 0$ for all $v \in V$, and $\langle Tv, w \rangle = 0$ for all $v \in V, w \in W$. Then $\langle v, T^* w \rangle = 0$ for all $v \in V, w \in W$. Taking $v = T^* w$, $T^* w = 0$ for all $w \in W$. Thus $T^* = 0$.

$T^* = 0 \rightarrow T^* T = 0$

Suppose $T^* = 0$. Then $T^* T = 0$. 

$T^* T = 0 \rightarrow T = 0$

Suppose $T^* T = 0$. Then $T^* T v = 0$ for all $v \in V$, and $\langle T^* T v, v \rangle = 0$ for all $v \in V$. Then $\langle Tv, Tv \rangle = 0$ for all $v \in V$. Hence $Tv = 0$ for all $v \in V$, and $T = 0$.  

$T T^* = 0 \rightarrow T^* = 0$

Suppose $T T^* = 0$. Then $T T^* w = 0$ for all $w \in W$, and $\langle T T^* w, w \rangle = 0$ for all $w \in W$. Then $\langle T^* w, T^* w \rangle = 0$ for all $w \in W$. Hence $T^* w = 0$ for all $w \in W$, and $T^* = 0$.


### (3) Suppose $T \in L(V)$ and $\lambda \in F$. Prove that $\lambda$ is an eigenvalue of $T$ $\iff$ $\overline{\lambda}$ is an eigenvalue of $T^*$.

Suppose $\lambda$ is an eigenvalue of $T$. Then $T - \lambda I$ is not injective, i.e. $null (T - \lambda I) \neq \\{0\\}$. 

From 3.21, we have 

$$dim V = dim null (T - \lambda I) + dim range (T - \lambda I).$$

Since $dim null (T - \lambda I) \geq 1$, $range (T - \lambda I) \subset V$.

From 7.6, we have 

$$null (T - \lambda)^* = (range (T - \lambda I))^\perp.$$

Since 

$$V = range (T - \lambda I) \oplus (range (T - \lambda I))^\perp $$

by 6.49, $(range (T - \lambda I))^\perp \neq \\{0\\}$. So $range (T - \lambda I)$ is a proper subspace, and its orthogonal complement is nonzero.

Thus $null (T - \lambda)^* \neq \\{0\\}$. 

Note that 

$$(T - \lambda)^* = T^* - \overline{\lambda} I.$$

We conclude that $T^* - \overline{\lambda} I$ is not injective. Hence $\overline{\lambda}$ is an eigenvalue of $T^*$.

The opposite direction follows from symmetry and the fact that $(T^* - \overline{\lambda} I)^* = T - \lambda I$.


### (4) Suppose $T \in L(V)$ and $U$ is a subspace of $V$. Prove that $U$ is invariant under $T$ $\iff$ $U^\perp$ is invariant under $T^*$.

Suppose $U$ is invariant under $T$. Suppose $u \in U$ and $w \in U^\perp$. Then $Tu \in U$. We have 

$$0 = \langle Tu, w \rangle = \langle u, T^* w \rangle$$

So $T^* w$ is orthogonal to $U$. Hence $T^* w \in U^\perp$ and $U^\perp$ is invariant under $T^*$.

The opposite direction follows from symmetry and the fact that $(U^\perp)^\perp = U$.


### (5) Suppose $T \in L(V, W)$. Suppose $e_1, ..., e_n$ is an orthonormal basis of $V$ and $f_1, ..., f_m$ is an orthonormal basis of $W$. Prove that $\lVert Te_1 \rVert^2 + ... + \lVert Te_n \rVert^2 = \lVert T^* f_1 \rVert^2 + ... + \lVert T^* f_m \rVert^2$.

From the proof of 7.9, we have 

$$Te_k = \langle Te_k, f_1 \rangle f_1 + ... + \langle Te_k, f_m \rangle f_m.$$

From 6.24, we have

$$\lVert Te_k \rVert^2 = |\langle Te_k, f_1 \rangle|^2 + ... + |\langle Te_k, f_m \rangle|^2.$$

Therefore 

$$\sum_{k=1}^n \lVert Te_k \rVert^2 = \sum_{k=1}^n \sum_{j=1}^m |\langle Te_k, f_j \rangle|^2.$$

Similarly, we have

$$T^* f_j = \langle T^* f_j, e_1 \rangle e_1 + ... + \langle T^* f_j, e_n \rangle e_n.$$

Therefore 

$$
\begin{aligned}
\sum_{j=1}^m \lVert T^* f_j \rVert^2 
    &= \sum_{j=1}^m \sum_{k=1}^n |\langle T^* f_j, e_k \rangle|^2 \\
    &= \sum_{j=1}^m \sum_{k=1}^n |\langle f_j, T e_k \rangle|^2 \\
    &= \sum_{j=1}^m \sum_{k=1}^n |\overline{\langle Te_k, f_j \rangle} |^2 \\
    &= \sum_{j=1}^m \sum_{k=1}^n |\langle Te_k, f_j \rangle|^2
\end{aligned}
$$

Hence 

$$\lVert Te_1 \rVert^2 + ... + \lVert Te_n \rVert^2 = \lVert T^* f_1 \rVert^2 + ... + \lVert T^* f_m \rVert^2.$$


### (6) Suppose $T \in L(V, W)$. Prove that 

#### (a) $T$ is injective $\iff$ $T^*$ is surjective.

$\Rightarrow$
Suppose $T$ is injective. Then $null T = \\{0\\}$ by 3.15. We have 

$$V = range T^* \oplus (range T^*)^\perp.$$

From 7.6 we have 

$$null T = (range T^*)^\perp = \\{0\\}.$$

Then $range T^* = V$. Hence we conclude $T^*$ is surjective.

$\Leftarrow$
Suppose $T^*$ is surjective. Then $range T^* = V$. We have 

$$V = null T \oplus (null T)^\perp.$$

From 7.6 we have 

$$range T^* = (null T)^\perp = V.$$

Then $null T = \\{0\\}$. Hence we conclude $T$ is injective.


#### (b) $T$ is surjective $\iff$ $T^*$ is injective.

$\Rightarrow$
Suppose $T$ is surjective. Then $range T = W$. We have 

$$W = null T^* \oplus (null T^*)^\perp.$$

From 7.6 we have

$$range T = (null T^*)^\perp = W.$$

Then $null T^* = \\{0\\}$. Hence we conclude $T^*$ is injective.

$\Leftarrow$
Suppose $T^*$ is injective. Then $null T^* = \\{0\\}$. We have 

$$W = range T \oplus (range T)^\perp.$$

From 7.6 we have

$$null T^* = (range T)^\perp = \\{0\\}.$$

Then $range T = W$. Hence we conclude $T$ is surjective.


### (7) Prove that if $T \in L(V, W)$, then 

#### (a) $dim null T^* = dim null T + dim W - dim V$.

$$
\begin{aligned}
dim null T^* &= dim (range T)^\perp \\
    &= dim W - dim range T \\
    &= dim W - (dim V - dim null T) \\
    &= dim null T + dim W - dim V
\end{aligned}
$$

#### (b) $dim range T^* = dim range T$.

$$
\begin{aligned}
dim range T^* &= dim W - dim null T^* \\
    &= dim W - dim (range T)^\perp \\
    &= dim range T
\end{aligned}
$$


### (10)

### (15)

### (17)

### (18)

### (20)

### (22)

### (29)

### (30)

### (32) Suppose $T: V \rightarrow W$ is a linear map. Show that under the standard identification of $V$ with $V'$ and the corresponding identification of $W$ and $W'$, the adjoint map $T*: W \rightarrow V$ corresponds to the dual map $T': W' \rightarrow V'$. More precisely, show that $T'(\phi_w) = \phi_{T* w}$. 

Suppose $v \in V, w \in W$. Then 

$$
\begin{aligned}
T'(\phi_w) (v) &= (\phi_w \circ T) (v) \\
    &= \phi_w (Tv) \\
    &= \langle Tv, w \rangle \\
    &= \langle v, T^* w \rangle \\
    &= \phi_{T^* w} (v)
\end{aligned}
$$

for all $v \in V$. 

Thus $T'(\phi_w) = \phi_{T^* w}$.




# 7B Spectral Theorem








# 7C Positive Operators

### 7.34 Definition: positive operator
An operator $T \in L(V)$ is called positive if $T$ is self-adjoint and 

$$\langle Tv, v\rangle  = 0$$

for all $v \in V$.

### 7.36 Definition: square root
An operator $R$ is called a square root of an operator $T$ if $R^2 = T$.

### 7.38
Let $T \in L(V)$. Then the following are equivalent.

(a) $T$ is a positive operator. 

(b) $T$ is self-adjoint and all eigenvalues of $T$ are nonnegative.

(c) With respect to some orthonormal basis of $V$, the matrix of $T$ is a diagonal matrix with only nonnegative numbers on the diagonal.

(d) $T$ has a positive square root.

(e) $T$ has a self-adjoint square root.

(f) $T = R^* R$ for some $R \in L(V)$.

### 7.39
Every positive operator on $V$ has a unique positive square root.

### 7.40 Notation
For $T$ a positive operator, $\sqrt{T}$ denotes the unique positive square root of $T$.

### 7.43
Suppose $T$ is a positive operator on $V$ and $v \in V$ is such that $\langle Tv, v\rangle  = 0$. Then $Tv = 0$.






# 7D Isometries, Unitary Operators, and Matrix Factorization

### 7.44 Definition: isometry
A linear map $S \in L(V, W)$ is called an isometry if 

$$||Sv|| = ||v||$$

for every $v \in V$. In other words, a linear map is an isometry if it preserves norms.

### 7.49
Suppose $S \in L(V, W)$. Suppose $e_1, ..., e_n$ is an orthonormal basis of $V$ and $f_1, ..., f_m$ is an orthonormal basis of $W$. Then the following are equivalent. 

(a) $S$ is an isometry.

(b) $S^* S = I$.

(c) $\langle Su, Sv\rangle  = \langle u, v\rangle $ for all $u, v \in V$.

(d) $Se_1, ..., Se_n$ is an orthonormal list in $W$.

(e) The columns of $M(S, (e_1, ..., e_n), (f_1, ..., f_m))$ form an orthonormal list in $F^m$ with respect to the Euclidean inner product.

### 7.51 Definition: unitary operator
An operator $S \in L(V)$ is called unitary if $S$ is an invertible isometry.

### 7.53

### 7.58 QR factorization
Suppose $A$ is a square matrix with linearly independent columns. Then there exist unique matrices $Q$ and $R$ such that $Q$ is unitary, $R$ is upper triangular with only positive numbers on its diagonal, and 

$$A = QR.$$

### 7.63 Cholesky factorization
Suppose $B$ is a positive definite matrix. Then there exists a unique upper-triangular matrix $R$ with only positive numbers on its diagonal such that 

$$B = R^* R.$$








# 7E Singular Value Decomposition

### 7.64
Suppose $T \in L(V, W)$. Then

(a) $T^* T$ is a positive operator on $V$;

(b) $null T^* T = null T$;

(c) $range T^* T = range T^*$;

(d) $dim range T = dim range T^* = dim range T^* T$.



### 7.65 Definition: singular values
Suppose $T \in L(V, W)$. The singular values of $T$ are teh nonnegative square roots of the eigenvalues of $T^* T$, listed in decreasing order, each included as many times as the dimension of the corresponding eigenspace of $T^* T$.

### 7.70 Singular value decomposition
Suppose $T \in L(V, W)$ and the positive singular values of $T$ are $s_1,...,s_m$. Then there exist orthonormal lists $e_1,...,e_m$ in $V$ and $f_1,...,f_m$ in $W$ such that 

$$Tv = s_1 \langle v, e_1\rangle  f_1 + ... + s_m \langle v, e_m\rangle  f_m$$

for every $v \in V$.

### 7.80 Matrix version of SVD
Suppose $A$ is a p-by-n matrix of rank m \rangle = 1. Then there exist a p-by-m matrix $B$ with orthonormal columns, an m-by-m diagonal matrix $D$ with positive numbers on the diagonal, and an n-by-m matrix $C$ with orthonormal columns such that 

$$A = B D C^*.$$






# 7F Consequences of Singular Value Decomposition

### 7.86 Definition: norm of a linear map
Suppose $T \in L(V, W)$. Then the norm of $T$, denoted by $\lVert T \rVert$, is defined by

$$\lVert T \rVert = max \\{\lVert Tv \rVert: v \in V, \lVert v \rVert \leq 1 \\}.$$ 


## Exercises



