Linear Algebra Done Right - Chapter 7 Operators on Inner Product Spaces <br> 
7C Positive Operators
================
Rosie Sun <br> 
2026-06-01


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

(f) $T = R^\ast R$ for some $R \in L(V)$.

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

Now suppose (e) holds, meaning that there exists a self-adjoint operator $R$ on $V$ such that $T = R^2$. Then $T = R^\ast R$ (because $R^\ast = R$). Hence (e) implies (f).

Finally, suppose (f) holds. Let $R \in L(V)$ be such that $T = R^\ast R$. Then 

$$T^\ast = (R^\ast R)^\ast = R^\ast (R^\ast)^\ast = R^\ast R = T.$$

Hence $T$ is self-adjoint. To complete the proof that (a) holds, note that 

$$\langle Tv, v \rangle = \langle R^\ast Rv, v \rangle = \langle Rv, Rv \rangle \geq 0$$

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

$$
\begin{aligned}
\lambda v &= a_1 \lambda e_1 + ... + a_n \lambda e_n \\
\lambda v &= a_1 \lambda_1 e_1 + ... + a_n \lambda_n e_n \\
(a_1 \lambda e_1 + ... + a_n \lambda e_n) - (a_1 \lambda_1 e_1 + ... + a_n \lambda_n e_n) &= 0 \\
a_1 (\lambda - \lambda_1) e_1 + ... + a_n (\lambda - \lambda_n) e_n &= 0
\end{aligned}
$$

Since $e_1, ..., e_n$ is a basis, $a_1 (\lambda - \lambda_1) = ... = a_n (\lambda - \lambda_n) = 0$. Thus $a_k (\lambda - \lambda_k) = 0$ for each $k = 1, ..., n$. If $\lambda - \lambda_k = 0$, then $a_k$ could be zero or nonzero. If $\lambda - \lambda_k \neq 0$, then $a_k = 0$. Therefore, we can remove the indices where we know for sure $a_k = 0$, or equivalently, $\lambda \neq \lambda_k$, from the sum:

$$v = \sum_{k: \lambda_k = \lambda} a_k e_k.$$

Thus 

$$
\begin{aligned}
Rv &= \sum_{k: \lambda_k = \lambda} a_k R e_k \\
    &= \sum_{k: \lambda_k = \lambda} a_k \sqrt{\lambda_k} \\
    &= \sum_{k: \lambda_k = \lambda} a_k \sqrt{\lambda} e_k \\
    &= \sqrt{\lambda} \sum_{k: \lambda_k = \lambda} a_k e_k \\
    &= \sqrt{\lambda} v
\end{aligned}
$$

as desired.


### 7.40 Notation
For $T$ a positive operator, $\sqrt{T}$ denotes the unique positive square root of $T$.


### 7.43
Suppose $T$ is a positive operator on $V$ and $v \in V$ is such that $\langle Tv, v\rangle  = 0$. Then $Tv = 0$.

Proof:

We have

$$
\begin{aligned}
0 &= \langle Tv, v \rangle \\
    &= \langle \sqrt{T} \sqrt{T} v, v \rangle \\
    &= \langle \sqrt{T} v, \sqrt{T} v \rangle \\
    &= \lvert \sqrt{T} v \rvert^2 
\end{aligned}
$$

Hence $\sqrt{T} v = 0$. Thus $Tv = \sqrt{T} (\sqrt{T} v) = 0$, as desired.




## Exercises

### (1) Suppose $T \in L(V)$. Prove that if both $T$ and $-T$ are positive operators, then $T = 0$.

Suppose $T$ and $-T$ are positive operators. Then 

$$\langle Tv, v \rangle \geq 0$$

and

$$\langle (-T)v, v \rangle = - \langle Tv, v \rangle \geq 0$$

for all $v \in V$. 

From the two inequalities we conclude

$$\langle Tv, v \rangle = 0$$

for all $v \in V$.

Since $T$ is positive, hence self-adjoint (by definition), $T = 0$ by 7.16.



### (2) Suppose $T \in L(F^4)$ is the operator whose matrix (with respect to the standard basis) is $M$ (below). Show that $T$ is an invertible positive operator.

$$
M =
\begin{pmatrix}
    2 & -1 & 0 & 0 \\
    -1 & 2 & -1 & 0 \\
    0 & -1 & 2 & -1 \\
    0 & 0 & -1 & 2
\end{pmatrix}
$$

First note that the matrix is real symmetric, thus $T$ is self-adjoint.

Suppose $(z_1, z_2, z_3, z_4) \in F^4$. We have

$$
\begin{aligned}
\langle T(z_1, z_2, z_3, z_4), (z_1, z_2, z_3, z_4) \rangle 
    &= 
    \langle 
        \begin{pmatrix}
            2 z_1 - z_2 \\
            -z_1 + 2z_2 - z_3 \\
            -z_2 + 2z_3 - z_4 \\
            -z_3 + 2z_4
        \end{pmatrix}
        ,
        \begin{pmatrix}
            z_1 \\
            z_2 \\
            z_3 \\
            z_4
        \end{pmatrix}
    \rangle 
    \\
    &= (2z_1 - z_2) \overline{z_1} + (-z_1 + 2z_2 - z_3) \overline{z_2} + (-z_2 + 2z_3 - z_4) \overline{z_3} + (-z_3 + 2z_4) \overline{z_4} \\
    &= 2 |z_1|^2 - 2 Re(\overline{z_1} z_2) + 2 |z_2|^2 - 2 Re(\overline{z_2} z_3) + 2 |z_3|^2 - 2 Re(\overline{z_3} z_4) + 2 |z_4|^2 \\
    &= |z_1 - z_2|^2 + |z_2 - z_3|^2 + |z_3 - z_4|^2 + |z_1|^2 + |z_4|^2 \\
    &\geq 0
\end{aligned}
$$

Hence $T$ is a positive operator.

Next we want to show that $T$ is invertible.

Suppose $Tv = 0$ for some $v = (z_1, z_2, z_3, z_4) \in F^4$. 

Then $\langle Tv, v \rangle = 0$, and 

$$|z_1 - z_2|^2 + |z_2 - z_3|^2 + |z_3 - z_4|^2 + |z_1|^2 + |z_4|^2 = 0.$$

Then $z_1 = 0$, $z_4 = 0$, which implies $z_2 = z_3 = 0$. Thus $v = 0$. 

Therefore $T$ is injective. By 3.65, $T$ is invertible.



### (3) Suppose $n$ is a positive integer and $T \in L(F^n)$ is the operator whose matrix (with respect to the standard basis) consists of all 1's. Show that $T$ is a positive operator.

First note that $T$ is self-adjoint because the matrix is real symmetric.

Suppose $z = (z_1, ..., z_n) \in F^n$. We have

$$
\begin{aligned}
\langle Tz, z \rangle 
&= 
\langle
    \begin{pmatrix}
    z_1 + ... + z_n \\
    ... \\
    z_1 + ... + z_n 
    \end{pmatrix}
    ,
    \begin{pmatrix}
    z_1 \\
    ... \\
    z_n 
    \end{pmatrix}
\rangle 
\\
&= \overline{z_1} (z_1 + ... + z_n) + ... + \overline{z_n} (z_1 + ... + z_n) \\
&= \overline{z_1 + ... + z_n} (z_1 + ... + z_n) \\
&= |z_1 + ... + z_n|^2 \\
&\geq 0
\end{aligned}
$$

Hence $T$ is a positive operator.



### (4) Suppose $n$ is an integer with $n > 1$. Show that there exists an n-by-n matrix $A$ such that all of the entries of $A$ are positive numbers and $A = A^\ast$, but the operator on $F^n$ whose matrix (with respect to the standard basis) equals $A$ is not a positive operator.

Consider the 2-by-2 matrix

$$
A = 
\begin{pmatrix}
1 & 2 \\
2 & 1
\end{pmatrix}
$$



### (5) Suppose $T$ is self-adjoint. Prove that $T$ is a positive operator if and only if for every orthonormal basis $e_1, ..., e_n$ of $V$, all entries on the diagonal of $M(T, (e_1, ..., e_n))$ are nonnegative numbers.

$\Rightarrow$
Suppose $T$ is a positive operator. Then $\langle Tv, v \rangle \geq 0$ for all $v \in V$.

For $k = 1, ..., n$, we have 

$$T e_k = \langle Te_k, e_1 \rangle e_1 + ... + \langle Te_k, e_n \rangle e_n$$

by the definition of the matrix 3.31 and 6.30.

The diagonal entries of $M(T, (e_1, ..., e_n))$ are $\langle Te_k, e_k \rangle$ for $k = 1, ..., n$. 

Since $\langle Tv, v \rangle \geq 0$ for all $v \in V$, the diagonal entries of $M(T, (e_1, ..., e_n))$ are nonnegative. 

$\Leftarrow$
Suppose for every orthonormal basis $e_1, ..., e_n$ of $V$, all entries on the diagonal of $M(T, (e_1, ..., e_n))$ are nonnegative numbers.

Since $T$ is self-adjoint, by the spectral theorem (7.31) $T$ has a diagonal matrix with respect to some orthonormal basis of $V$. 

By assumption, the diagonal entries of this matrix are nonnegative. Note that the diagonal entries of this matrix are the eigenvalues of $T$. Thus we conclude that the eigenvalues of $T$ are nonnegative. 

By 7.38(b), $T$ is a positive operator.



### (6) Prove that the sum of two positive operators on $V$ is a positive operator.

Suppose $S, T \in L(V)$ are positive operators. Then $S, T$ are self-adjoint.

We have 

$$(S + T)^\ast = S^\ast + T^\ast = S + T.$$

Thus $S + T$ is self-adjoint.

By execise (5) applied to $S$ and $T$, for every orthonormal basis $e_1, ..., e_n$ of $V$, all entries on the diagonal of $M(T, (e_1, ..., e_n))$ and $M(S, (e_1, ..., e_n))$ are nonnegative numbers.

Then for any orthonormal basis $e_1, ..., e_n$ of $V$, we have

$$M(S+T, (e_1, ..., e_n)) = M(S, (e_1, ..., e_n)) + M(T, (e_1, ..., e_n)).$$

The diagonal entries of $M(S+T)$ are equal to the sum of diagonal entries of $M(S)$ and the diagonal entries of $M(T)$. Thus the diagonal entries of $M(S+T)$ are nonnegative. 

Since $S + T$ is self-adjoint, and for all orthonormal basis of $V$, the diagonal entries of $M(S+T)$ are nonnegative, exercise (5) implies that $S+T$ is a positive operator.



### (7) Suppose $S \in L(V)$ is an invertible positive operator and $T \in L(V)$ is a positive operator. Prove that $S + T$ is invertible.

Since $S, T$ are positive operators, $\langle Sv, v \rangle \geq 0$ and $\langle Tv, v \rangle \geq 0$ for all $v \in V$.

Suppose $(S + T)v = 0$ for some $v \in V$. 

We have 

$$
\begin{aligned}
0 &= \langle (S + T)v, v \rangle \\
    &= \langle Sv + Tv, v \rangle \\
    &= \langle Sv, v \rangle + \langle Tv, v \rangle
\end{aligned}
$$

Thus $\langle Sv, v \rangle = 0$ and $\langle Tv, v \rangle = 0$.

By 7.43, $Sv = 0$. Since $S$ is invertible, it is injective by 3.65. Thus $v = 0$. 

Therefore $S + T$ is injective. By 3.65, it is invertible.



### (9) Suppose $T \in L(V)$ is a positive operator and $S \in L(W, V)$. Prove that $S^\ast TS$ is a positive operator on $W$.

Since $T$ is positive, $T$ is self-adjoint. We have 

$$(S^\ast TS)^\ast = S^\ast T^\ast (S^\ast)^\ast = S^\ast T S.$$

Thus $S^\ast TS$ is self-adjoint.

Since $T$ is positive, $\langle Tv, v \rangle \geq 0$ for all $v \in V$.

Suppose $w \in W$. We have

$$
\begin{aligned}
\langle (S^\ast TS)w, w \rangle 
    &= \langle S^\ast (TSw), w \rangle \\
    &= \langle (TS)w, Sw \rangle \\
    &= \langle T(Sw), (Sw) \rangle \\
    &\geq 0
\end{aligned}
$$

where the inequality follows because $Sw \in V$ so the assumption that $T$ being a positive operator applies.

Hence $S^\ast TS$ is a positive operator.



### (10) Suppose $T$ is a positive operator on $V$. Suppose $v, w \in V$ are such that $Tv = w$ and $Tw = v$. Prove that $v = w$.

Since $T$ is a positive operator, by 7.38 all eigenvalues of $T$ are nonnegative.

We have

$$T(v - w) = Tv - Tw = w - v = -1 (v - w).$$

If $v - w \neq 0$, then -1 would be an eigenvalue of $T$ which contradicts the fact that $T$ is positive. Thus $v - w = 0$. 



### (11) Suppose $T$ is a positive operator on $V$ and $U$ is a subspace of $V$ invariant under $T$. Prove that $T|_U \in L(U)$ is a positive operator on $U$.

Since $T$ is a positive operator on $V$, $T$ is self-adjoint. 

By exercise (19) from Section 7B, $T|_U \in L(U)$ is self-adjoint.

We have

$$\langle T|_U u, u \rangle = \langle Tu, u \rangle \geq 0$$

for all $u \in U$.

Hence $T|_U$ is a positive operator on $U$.



### (13)


### (16)


### (18)


### (20)


### (22)


### (24)

