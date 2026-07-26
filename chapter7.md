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

Suppose $T \in L(V, W)$. If $v \in V$ and $w_1, w_2 \in W$, then 

$$\langle Tv, w_1 + w_2 \rangle = \langle v, T^* (w_1 + w_2) \rangle .$$

and

$$
\begin{aligned}
\langle Tv, w_1 + w_2 \rangle 
    &= \langle Tv, w_1 \rangle + \langle Tv, w_2 \rangle \\
    &= \langle v, T^* w_1 \rangle + \langle v, T^* w_2 \rangle \\
    &= \langle v, T^* w_1 + T^* w_2 \rangle 
\end{aligned}
$$

We have

$$
\begin{aligned}
\langle v, T^* (w_1 + w_2) \rangle &= \langle v, T^* w_1 + T^* w_2 \rangle \\
\langle v, T^* (w_1 + w_2) \rangle - \langle v, T^* w_1 + T^* w_2 \rangle &= 0 \\
\langle v, T^* (w_1 + w_2) - (T^* w_1 + T^* w_2) \rangle &= 0
\end{aligned}
$$

for all $v \in V$. 

Take $v = T^* (w_1 + w_2) - T^* w_1 + T^* w_2$. Then by the positive definiteness of the inner product, $T^* (w_1 + w_2) - T^* w_1 + T^* w_2 = 0$. Thus

$$T^* (w_1 + w_2) = T^* w_1 + T^* w_2.$$

Similarly, if $v \in V$, $\lambda \in F$, and $w \in W$, then 

$$\langle Tv, \lambda w \rangle = \langle v, T^* (\lambda w) \rangle $$

and

$$
\begin{aligned}
\langle Tv, \lambda w \rangle 
    &= \overline{\lambda} \langle Tv, w \rangle \\
    &= \overline{\lambda} \langle v, T^* w \rangle \\
    &= \langle v, \lambda T^* w \rangle
\end{aligned}
$$

for all $v \in V$. Applying the same positive-definiteness argument, we have

$$T^* (\lambda w) = \lambda T^* w.$$

Thus $T^*$ satisfies additivity and homogeneity, therefore is a linear map.


### 7.5
Suppose $T \in L(V, W)$. Then

(a) $(S+T)^* = S^* + T^*$ for all $S \in L(V, W)$;

(b) $(\lambda T)^* = \overline{\lambda} T^*$ for all $\lambda \in F$;

(c) $(T^*)^* = T$;

(d) $(ST)^* = T^* S^*$ for all $S \in L(W, U)$ (here $U$ is a finite-dimensional inner product space over $F$);

(e) $I^* = I$, where $I$ is the identity operator on $V$;

(f) if $T$ is invertible, then $T^*$ is invertible and $(T^*)^{-1} = (T^{-1})^*$.

Proof:

Suppose $v \in V$ and $w \in W$.

(a) 

If $S \in L(V, W)$, then

$$\langle (S + T)v, w \rangle = \langle v, (S + T)^* w \rangle .$$

and 

$$
\begin{aligned}
\langle (S + T)v, w \rangle 
    &= \langle Sv, w \rangle + \langle Tv, w \rangle \\
    &= \langle v, S^* w \rangle + \langle v, T^* w \rangle \\
    &= \langle v, S^* w + T^* w \rangle 
\end{aligned}
$$

for all $v \in V$, all $w \in W$. Thus

$$(S + T)^* w = S^* w + T^* .$$

(b) 

If $\lambda \in F$, then 

$$\langle (\lambda T) v, w \rangle &= \langle v, (\lambda T)^* w \rangle$$

and

$$
\begin{aligned}
\langle (\lambda T) v, w \rangle 
    &= \lambda \langle Tv, w \rangle \\
    &= \lambda \langle v, T^* w \rangle \\
    &= \langle v, \overline{\lambda} T^* w \rangle
\end{aligned}
$$

for all $v \in V$, all $w \in W$. Thus 

$$(\lambda T)^* w = \overline{\lambda} T^* w .$$

(c)

We have

$$\langle T^* w, v \rangle = \langle w, (T^*)^* v \rangle$$

and

$$
\begin{aligned}
\langle T^* w, v \rangle 
    &= \overline{\langle v, T^* w \rangle} \\
    &= \overline{\langle Tv, w \rangle} \\
    &= \langle w, Tv \rangle 
\end{aligned}
$$

for all $v \in V$. Thus 

$$(T^*)^* v = Tv.$$

(d)

Suppose $S \in L(W, U)$ and $u \in U$. Then 

$$\langle (ST)v, u \rangle = \langle v, (ST)^* u \rangle$$

and

$$
\begin{aligned}
\langle (ST)v, u \rangle 
    &= \langle S(Tv), u \rangle \\
    &= \langle Tv, S^* u \rangle \\
    &= \langle v, T^* (S^* u) \rangle 
\end{aligned}
$$

for all $v \in V$, all $u \in U$. Thus 

$$(ST)^* u = T^* (S^* u).$$

(e)

Suppose $u \in V$. Then 

$$\langle Iu, v \rangle = \langle u, I^* v \rangle$$

and

$$\langle Iu, v \rangle = \langle u, v \rangle$$

for all $u, v \in V$. Thus

$$I^* v = v.$$

(f)

Suppose $T$ is invertible. We have $T^{-1} T = I$. Taking adjoints of both sides of the equation, we have

$$(T^{-1} T)^* = T^* (T^{-1})^* = I^* = I.$$

Similarly, taking adjoints of both sides of the equation $T T^{-1} = I$, we have 

$$(T T^{-1})^* = (T^{-1})^* T^* = I^* = I.$$

Thus $(T^{-1})^*$ is the inverse of $T^*$.


### 7.6
Suppose $T \in L(V, W)$. Then 

(a) $null T^* = (range T)^{\perp}$;

(b) $range T^* = (null T)^{\perp}$;

(c) $null T = (range T^*)^{\perp}$;

(d) $range T = (null T^*)^{\perp}$.

Proof:

(a) Let $w \in W$. Then 

$$
\begin{aligned}
w \in null T^* \iff T^* = 0 \\
    &\iff \langle v, T^* w \rangle = 0 \forall v \in V \\
    &\iff \langle Tv, w \rangle = 0 \forall v \in V \\
    &\iff w \in (range T)^\perp
\end{aligned}
$$

Thus 

$$null T^* = (range T)^\perp .$$

(d)

Taking the orthogonal complement of both sides of (a), we have

$$(null T^*)^\perp = ((range T)^\perp)^\perp = range T$$

where the second equality follows from 6.52.

(c)

Replacing $T$ with $T^*$ in (a), we have

$$null (T^*)^* = null T = (range T^*)^\perp$$

where the first equality follows from 7.5.

(b)

Replacing $T$ with $T^*$ in (d) gives (b).


### 7.7 Definition: conjugate transpose
The conjugate transpose of an m-by-n matrix $A$ is the n-by-m matrix $A^*$ obtained by interchanging the rows and columns and then taking the complex conjugate of each entry. In other words, if $j \in \\{1,...,n\\}$ and $k \in \\{1,...,m\\}$, then 

$$(A^*)_{j, k} = \overline{A_{k, j}}$$


### 7.9
Let $T \in L(V, W)$. Suppose $e_1, ..., e_n$ is an orthonormal basis of $V$ and $f_1, ..., f_m$ is an orthonormal basis of $W$. Then $M(T^*, (f_1, ..., f_m), (e_1, ..., e_n))$ is the conjugate transpose of $M(T, (e_1, ..., e_n), (f_1, ..., f_m))$. In other words, 

$$M(T^*) = (M(T))^* .$$

Proof:

Recall that we obtain the kth column of $M(T)$ by writing $Te_k$ as a linear combination of the $f_j$'s; the scalars used in this linear combination then become the kth column of $M(T)$. 

Because $f_1, ..., f_m$ is an orthonormal basis of $W$, we know how to write $Te_k$ as a linear combination of the $f_j$'s by 6.30:

$$Te_k = \langle Te_k, f_1 \rangle f_1 + ... + \langle Te_k, f_m \rangle f_m .$$

Thus the entry in row j, column k, of $M(T)$ is $\langle Te_k, f_j \rangle$.

In the statement above, replace $T$ with $T^*$ and interchange $e_1, ..., e_n$ and $f_1, ..., f_m$. 

This shows that the entry in row j, column k, of $M(T^*)$ is $\langle T^* f_k, e_j \rangle$, which equals $\langle f_k, Te_j \rangle$, which equals $\overline{\langle Te_j, f_k \rangle}$, which equals the complex conjugate of the entry in row k, column j, of $M(T)$.

Thus $M(T^*) = (M(T))^*$.


### 7.10 Definition: self-adjoint
An operator $T \in L(V)$ is called self-adjoint if $T = T^*$.


### 7.12
Every eigenvalue of a self-adjoint operator is real.

Proof:

Suppose $T$ is a self-adjoint operator on $V$. Let $\lambda$ be an eigenvalue of $T$, and let $v$ and a nonzero vector in $V$ such that $Tv = \lambda v$. Then 

$$
\begin{aligned}
\lambda \lvert v \rvert^2 &= \langle \lambda v, v \rangle \\
    &= \langle Tv, v \rangle \\
    &= \langle v, T^* v \rangle \\
    &= \langle v, Tv \rangle \\
    &= \langle v, \lambda v \rangle \\
    &= \overline{\lambda} \lvert v \rvert^2 
\end{aligned}
$$

Since $\lvert v \rvert \neq 0$, $\lambda = \overline{\lambda}$, which means that $\lambda$ is real.


### 7.13
Suppose $V$ is a complex inner product space and $T \in L(V)$. Then

$$\langle Tv, v \rangle  = 0 \forall v \in V \iff T = 0.$$

Proof:

If $u, w \in V$, then 

$$\langle Tu, w \rangle = \frac{\langle T(u + w), u + w \rangle - \langle T(u - w), u - w \rangle}{4} + \frac{\langle T(u + iw), u + iw \rangle - \langle T(u - iw), u - iw \rangle}{4} i .$$

Note that each term on the right side is of the form $\langle Tv, v \rangle$ for appropriate $v \in V$.

Now suppose $\langle Tv, v \rangle = 0$ for all $v \in V$. Then the equation above implies that $\langle Tu, w \rangle = 0$ for all $u, w \in V$. Take $w = Tu$. Then $\langle Tu, Tu \rangle = 0$ for all $u \in V$. Thus $Tu = 0$ for all $u \in V$. Hence $T = 0$.


### 7.14
Suppose $V$ is a complex inner product space and $T \in L(V)$. Then 

$$T = T^* \iff \langle Tv, v \rangle \in R \forall v \in V.$$

Proof:

If $v \in V$, then 

$$\langle T^* v, v \rangle = \overline{\langle v, T^* v \rangle} = \overline{\langle Tv, v \rangle}.$$

Now

$$
\begin{aligned}
T = T^* &\iff T - T^* = 0 \\
    &\iff \langle (T - T^*) v, v \rangle = 0 \forall v \in V \\
    &\iff \langle Tv, v \rangle - \langle T^* v, v \rangle = 0 \forall v \in V \\
    &\iff \langle Tv, v \rangle - \overline{\langle Tv, v \rangle} = 0 \forall v \in V \\
    &\iff \langle Tv, v \rangle \in R \forall v \in V
\end{aligned}
$$

where the second equivalence follows from 7.13.


### 7.16
Suppose $T$ is a self-adjoint operator on $V$. Then 

$$\langle Tv, v \rangle = 0 \forall v \in V \iff T = 0.$$

Proof:

We have already proved this without the hypothesis that $T$ is self-adjoint when $V$ is a complex inner product space (7.13). Thus we can assume that $V$ is a real inner product space. 

If $u, w \in V$, we have

$$\langle Tw, u \rangle = \langle w, T^* u \rangle = \langle w, Tu \rangle = \overline{\langle w, Tu \rangle} = \langle w, Tu \rangle .$$

where the second equality holds because $T$ is self-adjoint, and the fourth equality holds because we are working in a real inner product space.

We have

$$\langle Tu, w \rangle = \frac{\langle T(u + w), u + w \rangle - \langle T(u - w), u - w \rangle}{4} .$$

Now suppose $\langle Tv, v \rangle = 0$ for every $v \in V$. Because each term on the right side of the equation is of the form $\langle Tv, v \rangle$ for appropriate $v$, this implies that $\langle Tu, w \rangle = 0$ for all $u, w \in V$. Take $w = Tu$. Then $\langle Tu, Tu \rangle = 0$. Thus $Tu = 0$ for every $u \in V$. Hence $T = 0$.


### 7.18 Definition: normal
- An operator on an inner product space is called normal if it commutes with its adjoint.
- In other words, $T \in L(V)$ is normal $T T^* = T^* T$.

Every self-adjoint operator is normal, because if $T$ is self-adjoint then $T^* = T$ and hence $T$ commutes with $T^*$.


### 7.20 
Suppose $T \in L(V)$. Then 

$$T \text{is normal} \iff \lvert Tv \rvert = \lvert T^* v \rvert \forall v \in V .$$

Proof:

Note that $T^* T - T T^*$ is self-adjoint. We have

$$
\begin{aligned}
T \text{is normal} &\iff T^* T - T T^* = 0 \\
    &\iff \langle (T^* T - T T^*)v, v \rangle = 0 \forall v \in V \\
    &\iff \langle T^* T v, v \rangle = \langle T T^* v, v \rangle \forall v \in V \\
    &\iff \langle Tv, Tv \rangle = \langle T^* v, T^* v \rangle \forall v \in V \\
    &\iff \lvert Tv \rvert^2 = \lvert T^* v \rvert^2 \forall v \in V \\
    &\iff lvert Tv \rvert = \lvert T^* v \rvert \forall v \in V
\end{aligned}
$$

where the second equivalence follows from 7.16.


### 7.21
Suppose $T \in L(V)$ is normal. Then 

(a) $null T = null T^*$;

(b) $range T = range T^*$;

(c) $V = null T \oplus range T$;

(d) $T - \lambda I$ is normal for every $\lambda \in F$;

(e) if $v \in V$ and $\lambda \in F$, then $Tv = \lambda$ if and only if $T^* v = \overline{\lambda} v$.

Proof:

(a)

Suppose $v \in V$. Then

$$
\begin{aligned}
v \in null T &\iff Tv = 0 \\
    &\iff \lvert Tv \rvert = 0 \\
    &\iff \lvert T^* v \rvert = 0 \\
    &\iff T^* v = 0 \\
    &\iff v \in null T^*
\end{aligned}
$$

where the third equivalence follows from 7.20. Thus $null T = null T^*$.

(b)

We have

$$
\begin{aligned}
range T 
    &= (null T^*)\perp \\
    &= (null T)^\perp \\
    &= range T^*
\end{aligned}
$$

where the first equality comes from 7.6(d), the second equality comes from part (a), and the third equality comes from 7.6(b).

(c)

We have

$$
\begin{aligned}
V &= (null T) \oplus (null T)^\perp \\
    &= null T \oplus range T^* \\
    &= null T \oplus range T
\end{aligned}
$$

where the first equality comes from 6.49, the second equality comes from 7.6, and the third equality comes from part (b).

(d)

Suppose $\lambda \in F$. Then

$$
\begin{aligned}
(T - \lambda I) (T - \lambda I)^* 
    &= (T - \lambda I) (T^* - \overline{\lambda} I) \\
    &= T T^* - \overline{\lambda} T - \lambda T^* + |\lambda|^2 I \\
    &= T^* T - \overline{\lambda} T - \lambda T^* + |\lambda|^2 I \\ 
    &= (T^* - \overline{\lambda} I) (T - \lambda I) \\
    &= (T - \lambda I)^* (T - \lambda I)
\end{aligned}
$$

Thus $T - \lambda I$ commutes with its adjoint. Hence $T - \lambda I$ is normal.

(e)

Suppose $v \in V$ and $\lambda \in F$. Then (d) and 7.20 imply that 

$$\lvert (T - \lambda I) v \rvert = \lvert (T - \lambda I)^* v \rvert = \lvert (T^* - \overline{\lambda} I) v \rvert .$$

Thus 

$$
\begin{aligned}
Tv = \lambda v 
    &\iff (T - \lambda I) v = 0 \\
    &\iff \lvert (T - \lambda I) v \rvert = 0 \\
    &\iff \lvert (T^* - \overline{\lambda} I) v \rvert = 0 \\
    &\iff (T^* - \overline{\lambda} I) v = 0 \\
    &\iff T^* v = \overline{\lambda} v
\end{aligned}    
$$

Hence $Tv = \lambda v$ if and only if $T^* v = \overline{\lambda} v$.


### 7.22
Suppose $T \in L(V)$ is normal. Then eigenvectors of $T$ corresponding to distinct eigenvalues are orthogonal.

Because every self-adjoint operator is normal, the result applies in particular to self-adjoint operators.

Proof:

Suppose $\alpha, \beta$ are distinct eigenvalues of $T$, with corresponding eigenvectors $u, v$. Thus $Tu = \alpha u$ and $Tv = \beta v$. 

From 7.21 we have $T^* v = \overline{\beta} v$. Thus

$$
\begin{aligned}
(\alpha - \beta) \langle u, v \rangle 
    &= \alpha \langle u, v \rangle - \beta \langle u, v \rangle \\
    &= \langle \alpha u, v \rangle - \langle u, \overline{\beta} v \rangle \\
    &= \langle Tu, v \rangle - \langle u, T^* v \rangle \\
    &= \langle Tu, v \rangle - \langle Tu, v \rangle \\
    0
\end{aligned}
$$

Because $\alpha \neq \beta$, the equation above implies that $\langle u, v \rangle = 0$. Thus $u, v$ are orthogonal.


### 7.23
Suppose $F = C$ and $T \in L(V)$. Then $T$ is normal if and only if there exist commuting self-adjoint operators $A$ and $B$ such that $T = A + iB$.





## Exercises

### (1) Suppose $n$ is a positive integer. Define $T \in L(V)$ by $T(z_1, ..., z_n) = (0, z_1, ..., z_{n-1})$. Find a formula for $T^* (z_1, ..., z_n)$.

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



### (10) Suppose $F = C$ and $T \in L(V)$. Prove that $T$ is self-adjoint if and only if $\langle Tv, v \rangle = \langle T^* v, v \rangle$ for all $v \in V$.

$\Rightarrow$
Suppose $T$ is self-adjoint. 

Then $T = T^*$. Thus it follows immediately that $\langle Tv, v \rangle = \langle T^* v, v \rangle$ for all $v \in V$.

$\Leftarrow$
Suppose $\langle Tv, v \rangle = \langle T^* v, v \rangle$ for all $v \in V$. 

Then we have for all $v \in V$,

$$
\begin{aligned}
\langle Tv, v \rangle - \langle T^* v, v \rangle &= 0 \\
\langle Tv - T^* v, v \rangle = 0 \\
\langle (T - T^*) v, v \rangle = 0
\end{aligned}
$$

Since $F= C$ and $T - T^* \in L(V)$, it follows by 7.13 that $T - T^* = 0$. 

We conclude $T = T^*$, and $T$ is self-adjoint.



### (11) Define an operator $S: F^2 \rightarrow F^2$ by $S(w, z) = (-z, w)$. 

Suppose $(z_1, z_2) \in F^2$.

#### (a) Find a formula for $S^*$.

$$
\begin{aligned}
\langle S(z_1, z_2), (w_1, w_2) \rangle &= \langle (-z_2, z_1), (w_1, w_2) \rangle \\
    &= -z_2 \overline{w_1} + z_1 \overline{w_2} \\
    &= z_1 \overline{w_2} + z_2 (-\overline{w_1}) \\
    &= \langle (z_1, z_2), (w_2, -w_1) \rangle
\end{aligned}
$$

Thus we have 

$$S^* (z_1, z_2) = (z_2, - z_1).$$


#### (b) Show that $S$ is normal but not self-adjoint.

Since $S (z_1, z_2) = (-z_2, z_1)$ and $S^* (z_1, z_2) = (z_2, - z_1)$, $S \neq S^*$. 

Thus $S$ is not self-adjoint.

We have 

$$S^* S (z_1, z_2) = S^* (-z_2, z_1) = (z_1, z_2)$$

which is equal to 

$$S S^* (z_1, z_2) = S(z_2, -z_1) = (z_1, z_2)$$

Thus $S$ is normal.


#### (c) Find all eigenvalues of $S$.

We want to find $\lambda \in F$ such that $S(z_1, z_2) = \lambda (z_1, z_2)$ for some nonzero $z_1, z_2 \in V$. Then $\lambda z_1 = -z_2$ and $\lambda z_2 = z_1$. 

We have $\lambda^2 z_2 = -z_2$, and $\lambda^2 = -1$. 

When $F = R$, $S$ has no eigenvalues. 

When $F = C$, $S$ has two eigenvalues, $i$ and $-i$. 



### (12) An operator $B \in L(V)$ is called skew if $B^* = -B$. Suppose that $T \in L(V)$. Prove that $T$ is normal if and only if there exist commuting operators $A$ and $B$ such that $A$ is self-adjoint, $B$ is a skew operator, and $T = A + B$.

$\Rightarrow$
Suppose $T$ is normal. Then $T T^* = T^* T$. Let 

$$A = \frac{T + T^*}{2}$$

$$B = \frac{T - T^*}{2}$$

Then $A + B = T$. We have 

$$A^* = \frac{T^* + T}{2} = A$$

hence $A$ is self-adjoint. We have 

$$-B = - \frac{T - T^*}{2} = \frac{T^* - T}{2} = B^*$$

hence $B$ is skew. We have

$$AB = \frac{TT - T T^* + T^* T - T^* T^*}{4} = \frac{1}{4} (TT - T^* T^*)$$

$$BA = \frac{TT + T T^* - T^* T - T^* T^*}{4} = \frac{1}{4} (TT - T^* T^*)$$

hence $A$ and $B$ commute. 

$\Leftarrow$
Suppose there exist commuting operators $A$ and $B$ such that $A$ is self-adjoint, $B$ is skew, and $T = A+B$. 

Then $T^* = A^* + B^*$. We have 

$$(A+B) (A+B)^* = A A^* + A B^* + B A^* + B B^* = A A - AB + BA - BB = AA - BB$$

$$(A+B)^* (A+B) = A^* A + A^* B + B^* A + B^* B = A A + AB - BA - BB = AA - BB$$

Hence $T T^* = T^* T$, and $T$ is normal.



### (15) Suppose $T \in L(V)$ is invertible. Prove that 

#### (a) $T$ is self-adjoint $\iff$ $T^{-1}$ is self-adjoint.

Suppose $T$ is self-adjoint. Then $T = T^*$. We have

$$T^{-1} = (T^*)^{-1} = (T^{-1})^*$$

Hence $T^{-1}$ is self-adjoint. 

The opposite direction follows from symmetry and the fact that $(T^{-1})^{-1} = T$.


#### (b) $T$ is normal $\iff$ $T^{-1}$ is normal.

Suppose $T$ is normal. Then $T T^* = T^* T$ and $(T T^*)^{-1} = (T^* T)^{-1}$. We have

$$(T T^*)^{-1} = (T^*)^{-1} T^{-1} = (T^{-1})^* T^{-1}$$

where the second equality follows from 7.5. Similarly,

$$(T^* T)^{-1} = T^{-1} (T^*)^{-1} = T^{-1} (T^{-1})^* $$

Hence $T^{-1}$ commutes with its adjoint, and it is normal.

The opposite direction follows from symmetry and the fact that $(T^{-1})^{-1} = T$.



### (16) Suppose $F = R$.

#### (a) Show that the set of self-adjoint operators on $V$ is a subspace of $L(V)$.

Let $U$ be the set of self-adjoint operators. We want to show that it contains the zero operator, it is closed under addition and closed under scalar multiplication.

Consider $0 \in L(V)$. $0v = 0$ for all $v \in V$. We have

$$\langle 0v, w \rangle = \langle v, 0^* w \rangle = 0$$

for all $v, w \in V$. Then $0^* = 0$. Hence the zero operator is self-adjoint.

Suppose $S, T \in L(V)$ are self-adjoint operators. Then 

$$(S+T)^* = S^* + T^* = S + T$$

Hence $S+T$ is self-adjoint. 

Suppose $T \in L(V)$ and $\lambda \in R$. Then

$$(\lambda T)^* = \overline{\lambda} T^* = \lambda T$$

where the second equality follows from the fact that $\lambda \in R$.

Thus $U$ is a subspace of $L(V)$ by 1.34.


#### (b) What is the dimension of the subspace of $L(V)$ in (a) [in terms of $dim V$]?

Suppose $dim V = n$. From 3.72 we have $dim L(V) = (dim V) (dim V) = n^2$. 

Because $L(V)$ is isomorphic with $F^{n, n}$, we can consider $M(T)$ and $M(T^*)$. 

If $T = T^*$, then $M(T^*) = (M(T))^* = M(T)$ from 7.9. And since $F = R$, the conjugate transpose becomes the transpose. Thus the matrix is symmetric. The $n$ diagonal elements and the $\frac{n^2 - n}{2}$ off-diagonal elements are free. Thus there are $\frac{n^2 + n}{2}$ free elements. $dim U = \frac{n^2 + n}{2}$.



### (17) Suppose $F = C$. Show that the set of self-adjoint operators on $V$ is not a subspace of $L(V)$.

Suppose $T \in L(V), T \neq 0$ is self-adjoint. Then $(iT)^* = -iT^* \neq iT$. Hence the set is not closed under scalar multiplication, and therefore is not a subspace of $L(V)$.



### (18) Suppose $dim V \geq 2$. Show that the set of normal operators on $V$ is not a subspace of $L(V)$.

We want to show that the set is not closed under addition.

Suppose $S, T \in L(F^2)$ such that 

$$
M(S) = 
\frac{1}{2}
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}
$$

$$
M(T) = 
\frac{1}{2}
\begin{pmatrix}
0 & 1 \\
-1 & 0
\end{pmatrix}
$$

By hypothesis, $S$ is self-adjoint therefore normal. $T$ is normal.

$$T T^* = 
\frac{1}{4}
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$

Then we have 

$$
A = M(S + T) = 
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
$$

$$
A^* = (M(S + T))^* = 
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix}
$$

Thus 

$$
A A^* = 
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
$$

which is not equal to 

$$
A^* A = 
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
$$

Note that the assumption that $dim V \geq 2$ is needed. If $dim V = 1$, then every $T \in L(V)$ is a scalar multiple of the identity operator, i.e. $\lambda I$. Then its adjoint is $\overline{\lambda} I$. 

$$(\lambda I) (\lambda I)^* = |\lambda|^2 I = (\lambda I)^* (\lambda I)$$

Every operator on $V$ is normal.



### (19) Suppose $T \in L(V)$ and $\lVert T^* v \rVert \leq \lVert Tv \rVert$ for every $v \in V$. Prove that $T$ is normal.

Applying the hypothesis to $T^* \in L(V)$, we have

$$\lVert T^* v \rVert \leq \lVert (T^*)^* v \rVert = \lVert T v \rVert$$

for all $v \in V$. Combined with the hypothesis, we have 

$$\lVert T v \rVert = \lVert T^* v \rVert.$$

By 7.20 $T$ is normal.


### (20) Suppose $P \in L(V)$ is such that $P^2 = P$. Prove that the following are equivalent: (a) $P$ is self-adjoint. (b) $P$ is normal. (c) There is a subspace $U$ of $V$ such that $P = P_U$.

$(a) \rightarrow (b)$

Suppose $P$ is self-adjoint. Then it follows immediately that $P$ is normal.

$(b) \rightarrow (c)$

Suppose $P$ is normal. Then by 7.6 and 7.21, $V = null P \oplus range P$, $null P = null P^* = (range P)^\perp$. 

Hence we have $V = range P \oplus (range P)^\perp$.

Consider $U = range P$. For every $v \in V$, we can write $v = Pv + (v - Pv)$.

We have $Pv \in range P = U$ by definition. 

Since $P^2 = P$ by hypothesis, $P(v - Pv) = Pv - PPv =0$. Hence $(v - Pv) \in null P = U^\perp$.

Thus $v = Pv + (v - Pv)$ where $Pv \in U$ and $(v - Pv) \in U^\perp$. We conclude that $P = P_U$ where $U = range P$.

$(c) \rightarrow (a)$

Suppose there is a subspace $U$ of $V$ such that $P = P_U$. 

Suppose $v \in V$ and $v = u + w$ for $u \in U, w \in U^\perp$. Suppose $x \in V$ such that $x = u' + w'$ where $u' \in U, w' \in U^\perp$. We have

$$
\begin{aligned}
\langle Pv, x \rangle 
    &= \langle u, u'+w' \rangle \\
    &= \langle u, u' \rangle + \langle u, w' \rangle \\
    &= \langle u, u' \rangle 
\end{aligned}    
$$

Since $u \in U, w' \in U^\perp$, $\langle u, w' \rangle = 0$.

Similarly we have

$$
\begin{aligned}
\langle v, Px \rangle 
    &= \langle u+w, u' \rangle \\
    &= \langle u, u' \rangle + \langle w, u' \rangle \\
    &= \langle u, u' \rangle 
\end{aligned}    
$$

Since $u' \in U, w \in U^\perp$, $\langle w, u' \rangle = 0$.

Then 

$$\langle Pv, x \rangle = \langle v, Px \rangle$$

for all $v, x \in V$.

By definition, 

$$\langle Pv, x \rangle = \langle v, P^* x \rangle$$

for all $v, x \in V$. Then 

$$\langle v, Px \rangle = \langle v, P^* x \rangle$$

for all $v, x \in V$. Therefore

$$0 = \langle v, Px \rangle - \langle v, P^* x \rangle = \langle v, Px - P^* x \rangle = \langle v, (P - P^*) x \rangle$$

for all $v, x \in V$. Taking $v = (P - P^*)x$, we have $\langle (P - P^*) x, (P - P^*) x \rangle = 0$ for all $x \in V$. Hence $(P - P^*) x = 0$ for all $x \in V$, and $P - P^* = 0$. 

Thus we conclude $P^* = P$ and $P$ is self-adjoint.



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





--------------------------------------------------------------------------------
# 7B Spectral Theorem

### 7.26
Suppose $T \in L(V)$ is self-adjoint and $b, c \in R$ are such that $b^2 < 4c$. Then

$$T^2 + bT + cI$$

is an invertible operator.

Proof:

Let $v$ be a nonzero vector in $V$. Then

$$
\begin{aligned}
\langle (T^2 + bT + cI) v, v \rangle 
    &= \langle TT v, v \rangle + b \langle Tv, v \rangle + c \langle v, v \rangle \\
    &= \langle Tv, T^* v \rangle + b \langle Tv, v \rangle + c \lvert v \rvert^2 \\
    &= \langle Tv, Tv \rangle + b \langle Tv, v \rangle + c \lvert v \rvert^2 \\
    &\geq \lvert Tv \rvert^2 - |b| \lvert Tv \rvert \lvert v \rvert + c \lvert v \rvert^2 \\
    &= (\lvert Tv \rvert - \frac{|b| \lvert v \rvert}{2})^2 + (c - \frac{b^2}{4}) \lvert v \rvert^2 \\
    &> 0
\end{aligned}
$$

The first inequality follows from Cauchy-Schwartz inequality (6.14).

$$b \langle Tv, v \rangle \leq |b| |\langle Tv, v \rangle| \leq |b| \lvert Tv \rvert \lvert v \rvert .$$

Thus

$$-|b| \lvert Tv \rvert \lvert v \rvert \leq b \langle Tv, v \rangle .$$

The last inequality implies that $(T^2 + bT + cI) v \neq 0$. Thus $T^2 + bT + cI$ is injective. 

Since $V$ is finite-dimensional (standing assumption of this chapter), $T^2 + bT + cI$ is invertible by 3.65.


### 7.27
Suppose $T \in L(V)$ is self-adjoint. Then the minimal polynomial of $T$ equals $(z - \lambda_1) ... (z - \lambda_m)$ for some $\lambda_1, ..., \lambda_m \in R$.

Proof:

First suppose $F = C$. The zeros of the minimal polynomial of $T$ are the eigenvalues of $T$ by 5.27. All eigenvalues of $T$ are real by 7.12. Thus the second version of thd fundamental theorem of algebra tells us that the minimal polynomial of $T$ has the desired form.

Now suppose $F = R$. By the factorization of a polynomial over $R$ (4.16), there exist $\lambda_1, ..., \lambda_m \in R$, and $b_1, ..., b_N, c_1, ..., c_N \in R$ with $b_k^2 < 4c_k$ for each $k$ such that the minimal polynomial of $T$ equals 

$$(7.28) (z - \lambda_1) ... (z - \lambda_m) (z^2 + b_1 z+ c_1) ... (z^2 + b_N z + c_N) ;$$

here either $m$ or $N$ might equal 0, meaning that there are no terms of the corresponding form. Now

$$(T - \lambda_1 I) ... (T - \lambda_m I) (T^2 + b_1 T + c_1 I) ... (T^2 + b_N T + c_N I) = 0 .$$

If $N > 0$, then we could multiply both sides of the equation above on the right by the inverse of $T^2 + b_N T + c_N I$ (which is an invertible operator by 7.26) to obtain a polynomial expression of $T$ that equals 0. The corresponding polynomial would have degree two less than the degree of 7.28, violating the minimality of the degree of the polynomial with this property. Thus we must have $N = 0$, which means that the minimal polynomial in 7.28 has the form $(z - \lambda_1) ... (z - \lambda_m)$, as desired.


### 7.29 Real spectral theorem
Suppose $F = R$ and $T \in L(V)$. Then the following are equivalent.

(a) $T$ is self-adjoint.

(b) $T$ has a diagonal matrix with respect to some orthonormal basis of $V$.

(c) $V$ has an orthonormal basis consisting of eigenvectors of $T$.

Proof:

First suppose (a) holds, so $T$ is self-adjoint. Our results on minimal polynomials, specifically 6.37 and 7.27, imply that $T$ has an upper-triangular matrix with respect to some orthonormal basis of $V$. With respect to this orthonormal basis, the matrix of $T^*$ is the transpose of the matrix of $T$. However, $T^* = T$. Thus the transpose of the matrix of $T$ equals the matrix of $T$. Because the matrix of $T$ is upper-triangular, this means that all entries of the matrix above and below the diagonal are 0. Hence the matrix of $T$ is a diagonal matrix with respect to the orthonormal basis. Thus (a) implies (b).

Conversely, now suppose (b) holds, so $T$ has a diagonal matrix with respect to some orthonormal basis of $V$. That diagonal matrix equals its transpose. Thus with respect to this basis, the matrix of $T^*$ equals the matrix of $T$. Hence $T^* = T$, proving that (b) implies (a). 

The equivalence of (b) and (c) follows from the definitions (or see 5.55).


### 7.31 Complex spectral theorem
Suppose $F = C$ and $T \in L(V)$. Then the following are equivalent.

(a) $T$ is normal.

(b) $T$ has a diagonal matrix with respect to some orthonormal basis of $V$.

(c) $V$ has an orthonormal basis consisting of eigenvectors of $T$.

Proof:

First suppose (a) holds, so $T$ is normal. By Schur's theorem (6.38), there is an orthonormal basis $e_1, ..., e_n$ of $V$ with respect to which $T$ has an upper-triangular matrix. Thus we can write 

$$
M(T, (e_1, ..., e_n)) = 
\begin{pmatrix}
a_{1, 1} & ... & a_{1, n} \\
... \\
0 & ... & a_{n, n}
\end{pmatrix}
$$

The matrix of $T^*$ (with respect to the same basis) is obtained by taking the conjugate transpose of the matrix of $T$.

$$
M^* (T, (e_1, ..., e_n)) = 
\begin{pmatrix}
\overline{a_{1, 1}} & 0 & ... \\
\overline{a_{1, 2}} & \overline{a_{2, 2}} & ... \\
... \\
\overline{a_{1, n}} & \overline{a_{2, n}} & ... \\
\end{pmatrix}
$$

We will show that $M$ is actually a diagonal matrix.

We see from the matrix $M$ and $M^*$ that

$$\lvert Te_1 \rvert^2 = \lvert a_{1, 1} e_1 \rvert^2 = |a_{11}|^2 ,$$

$$\lvert T^* e_1 = \overline{a_{1, 1}} e_1 + ... + \overline{a_{1, n}} e_n \rvert^2 = |a_{1, 1}|^2 + ... + |a_{1, n}|^2 .$$

Because $T$ is normal, $\lvert Te_1 \rvert = \lvert T^* e_1 \rvert$ by 7.20. Thus the two equations above imply that all entries in the first row of $M$, except possibly the first entry $a_{1, 1}$, equal 0.

$$\lvert Te_2 \rvert^2 = \lvert a_{1, 2} e_1 + a_{2, 2} e_2 \rvert^2 = \lvert a_{2, 2} e_2 \rvert^2 = |a_{2, 2}|^2$$

(because $a_{1, 2} = 0$ shown earlier), and 

$$\lvert T^* e_2 = \overline{a_{2, 2}} e_2 + ... + \overline{a_{2, n}} e_n \rvert^2 = |a_{2, 2}|^2 + ... + |a_{2, n}|^2 .$$

Because $T$ is normal, $\lvert Te_2 \rvert = \lvert T^* e_2 \rvert$. Thus the two equations above imply that all entries in the second row of $M$, except possibly the diagonal entry $a_{2, 2}$, equal 0.

Continuing in this fashion, we see that all nondiagonal entries in the matrix $M$ equal 0. Thus (b) holds, completing the proof that (a) implies (b).

Now suppose (b) holds, so $T$ has a diagonal matrix with respect to some orthonormal basis of $V$. The matrix of $T^*$ (with respect to the same basis) is obtained by taking the conjugate transpose of the matrix of $T$; hence $T^*$ also has a diagonal matrix. Any two diagonal matrices commute; thus $T$ commutes with $T^*$, which means $T$ is normal. Thus (a) holds, completing the proof that (b) implies (a).

The equivalence of (b) and (c) follows from the definitions (also see 5.55).




## Exercises

### (1) Prove that a normal operator on a complex inner product space is self-adjoint if and only if all its eigenvalues are real.


### (2) Suppose $F = C$. Suppose $T \in L(V)$ is normal and has only one eigenvalue. Prove that $T$ is a scalar multiple of the identity operator.


### (3) Suppose $F = C$ and $T \in L(V)$ is normal. Prove that the set of eigenvalues of $T$ is contained in $\\{0, 1\\}$ if and only if there is a subspace $U$ of $V$ such that $T = P_U$.


### (4) Prove that a normal operator on a complex inner product space is skew (meaning it equals the negative of its adjoint) if and only if all its eigenvalues are purely imaginary (meaning that they have real part equal to 0).


### (5)


### (13)


### (14)


### (15)


### (19)


### (20)





--------------------------------------------------------------------------------
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

Proof:

We will prove that (a) $\Leftarrow$ (b) $\Leftarrow$ (c) $\Leftarrow$ (d) $\Leftarrow$ (e) $\Leftarrow$ (f) $\Leftarrow$ (a).

First suppose (a) holds, so that $T$ is positive, which implies that $T$ is self-adjoint (by the definition of positive operator). 

To prove the other condition in (b), suppose $\lambda$ is an eigenvalue of $T$. Let $v$ be an eigenvector of $T$ corresponding to $\lambda$. Then 

$$0 \leq \langle Tv, v \rangle = \langle \lambda v, v \rangle = \lambda \langle v, v \rangle .$$

Since $\langle v, v \rangle \geq 0$, $\lambda$ is a nonnegative number. Hence (b) holds, showing that (a) implies (b).

Now suppose (b) holds, so that $T$ is self-adjoint and all eigenvalues of $T$ are nonnegative. By the spectral theorem (7.29, 7.31), there is an orthonormal basis $e_1, ..., e_n$ of $V$ consisting of eigenvectors of $T$. Let $\lambda_1, ..., \lambda_n$ be the eigenvalues of $T$ corresponding to $e_1, ..., e_n$; thus each $\lambda_k$ is a nonnegative number. The matrix of $T$ with respect to $e_1, ..., e_n$ is the diagonal matrix with $\lambda_1, ..., \lambda_n$ on the diagonal, which shows that (b) implies (c).

Now suppose (c) holds. Suppose $e_1, ..., e_n$ is an orthonormal basis of $V$ such that the matrix of $T$ with respect to this basis is a diagonal matrix with nonnegative numbers $\lambda_1, ..., \lambda_n$ on the diagonal. The linear map lemma (3.4) implies that there exists $R \in L(V)$ such that 

$$R e_k = \sqrt{\lambda_k} e_k$$

for each $k = 1, ..., n$. We verify that $R$ is a positive operator. For any $v \in V$, $v = \langle v, e_1 \rangle e_1 + ... + \langle v, e_n \rangle e_n$. 

$$
\begin{aligned}
\langle Rv, v \rangle &= 
    \langle R(\langle v, e_1 \rangle e_1 + ... + \langle v, e_n \rangle e_n), v \rangle \\
    &= \langle \langle v, e_1 \rangle R e_1 + ... + \langle v, e_n \rangle R e_n, v \rangle \\
    &= \langle \langle v, e_1 \rangle \sqrt{\lambda_1} e_1 + ... + \langle v, e_n \rangle \sqrt{\lambda_n} e_n, \langle v, e_1 \rangle e_1 + ... + \langle v, e_n \rangle e_n \rangle \\
    &= |\langle v, e_1 \rangle|^2 \sqrt{\lambda_1} + ... + |\langle v, e_n \rangle|^2 \sqrt{\lambda_n} \\
    &\geq 0
\end{aligned}$$

If $F = C$, $\langle Rv, v \rangle \in R \forall v \in V$. By 7.14 $R$ is self-adjoint. If $F = R$, by definition $V$ has an orthonormal basis consisting of eigenvectors of $R$. By the real spectral theorem (7.29), $R$ is self-adjoint.   

Furthermore, $R^2 e_k = \lambda_k e_k = T e_k$ for each $k$, which implies that $R^2 = T$. Thus $R$ is a positive square root of $T$. Hence (d) holds, which shows that (c) implies (d).

Every positive operator is self-adjoint (by definition of positive operator). Thus (d) implies (e).

Now suppose (e) holds, meaning that there exists a self-adjoint operator $R$ on $V$ such that $T = R^2$. Then $T = R^* R$ (because $R^* = R$). Hence (e) implies (f).

Finally, suppose (f) holds. Let $R \in L(V)$ be such that $T = R^* R$. Then 

$$T^* = (R^* R)^* = R^* (R^*)^* = R^* R = T.$$

Hence $T$ is self-adjoint. To complete the proof that (a) holds, note that 

$$\langle Tv, v \rangle = \langle R^* Rv, v \rangle = \langle Rv, Rv \rangle \geq 0$$

for every $v \in V$. Thus $T$ is positive, showing that (f) implies (a).


### 7.39
Every positive operator on $V$ has a unique positive square root.

Proof:

Suppose $T \in L(V)$ is positive. Suppose $v \in V$ is an eigenvector of $T$. Hence there exists a real number $\lambda >= 0$ such that $Tv = \lambda v$. 

Let $R$ be a positive square root of $T$. We will prove that $Rv = \sqrt{\lambda} v$. This will imply that the behavior of $R$ on the eigenvectors of $T$ is uniquely determined. Because there is a basis of $V$ consisting of eigenvectors of $T$ (by the spectral theorem), this will imply that $R$ is uniquely determined.

To prove that $Rv = \sqrt{\lambda} v$, note that the spectral theorem asserts that there is an orthonormal basis $e_1, ..., e_n$ of $V$ consisting of eigenvectors of $R$. Because $R$ is a positive operator, all its eigenvalues are nonnegative. Thus there exist nonnegative numbers $\lambda_1, ..., \lambda_n$ such that $R e_k = sqrt{\lambda_k} e_k$ for each $k = 1, ..., n$.

Because $e_1, ..., e_n$ is a basis of $V$, we can write 

$$v = a_1 e_1 + ... + a_n e_n$$

for some numbers $a_1, ..., a_n \in F$. Thus

$$Rv = a_1 \sqrt{\lambda_1} e_1 + ... a_n \sqrt{\lambda_n} e_n.$$

Hence 

$$\lambda v = Tv = R^2 v = a_1 \lambda_1 e_1 + ... + a_n \lambda_n e_n.$$

The equation above implies that 

$$a_1 \lambda e_1 + ... + a_n \lambda e_n = a_1 \lambda_1 e_1 + ... + a_n \lambda_n e_n.$$

Thus $a_k (\lambda - \lambda_k) = 0$ for each $k = 1, ..., n$. Hence

$$v = \sum_{k: \lambda_k = \lambda} a_k e_k.$$

Thus 

$$Rv = \sum_{k: \lambda_k = \lambda} a_k \sqrt{\lambda} e_k = \sqrt{\lambda} v$$

as desired.


### 7.40 Notation
For $T$ a positive operator, $\sqrt{T}$ denotes the unique positive square root of $T$.


### 7.43
Suppose $T$ is a positive operator on $V$ and $v \in V$ is such that $\langle Tv, v\rangle  = 0$. Then $Tv = 0$.





## Exercises

### (1)

### (2)

### (3)

### (4)

### (5)

### (6)

### (7)

### (9)

### (10)




