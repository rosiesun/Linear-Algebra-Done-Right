Linear Algebra Done Right - Chapter 7 Operators on Inner Product Spaces <br> 
7B Spectral Theorem
================
Rosie Sun <br> 
2026-06-01


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
    &= \langle Tv, T^\ast v \rangle + b \langle Tv, v \rangle + c \lvert v \rvert^2 \\
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

First suppose (a) holds, so $T$ is self-adjoint. Our results on minimal polynomials, specifically 6.37 and 7.27, imply that $T$ has an upper-triangular matrix with respect to some orthonormal basis of $V$. With respect to this orthonormal basis, the matrix of $T^\ast$ is the transpose of the matrix of $T$. However, $T^\ast = T$. Thus the transpose of the matrix of $T$ equals the matrix of $T$. Because the matrix of $T$ is upper-triangular, this means that all entries of the matrix above and below the diagonal are 0. Hence the matrix of $T$ is a diagonal matrix with respect to the orthonormal basis. Thus (a) implies (b).

Conversely, now suppose (b) holds, so $T$ has a diagonal matrix with respect to some orthonormal basis of $V$. That diagonal matrix equals its transpose. Thus with respect to this basis, the matrix of $T^\ast$ equals the matrix of $T$. Hence $T^\ast = T$, proving that (b) implies (a). 

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

The matrix of $T^\ast$ (with respect to the same basis) is obtained by taking the conjugate transpose of the matrix of $T$.

$$
M^\ast (T, (e_1, ..., e_n)) = 
\begin{pmatrix}
\overline{a_{1, 1}} & 0 & ... \\
\overline{a_{1, 2}} & \overline{a_{2, 2}} & ... \\
... \\
\overline{a_{1, n}} & \overline{a_{2, n}} & ... \\
\end{pmatrix}
$$

We will show that $M$ is actually a diagonal matrix.

We see from the matrix $M$ and $M^\ast$ that

$$\lvert Te_1 \rvert^2 = \lvert a_{1, 1} e_1 \rvert^2 = |a_{11}|^2 ,$$

$$\lvert T^\ast e_1 = \overline{a_{1, 1}} e_1 + ... + \overline{a_{1, n}} e_n \rvert^2 = |a_{1, 1}|^2 + ... + |a_{1, n}|^2 .$$

Because $T$ is normal, $\lvert Te_1 \rvert = \lvert T^\ast e_1 \rvert$ by 7.20. Thus the two equations above imply that all entries in the first row of $M$, except possibly the first entry $a_{1, 1}$, equal 0.

$$\lvert Te_2 \rvert^2 = \lvert a_{1, 2} e_1 + a_{2, 2} e_2 \rvert^2 = \lvert a_{2, 2} e_2 \rvert^2 = |a_{2, 2}|^2$$

(because $a_{1, 2} = 0$ shown earlier), and 

$$\lvert T^\ast e_2 = \overline{a_{2, 2}} e_2 + ... + \overline{a_{2, n}} e_n \rvert^2 = |a_{2, 2}|^2 + ... + |a_{2, n}|^2 .$$

Because $T$ is normal, $\lvert Te_2 \rvert = \lvert T^\ast e_2 \rvert$. Thus the two equations above imply that all entries in the second row of $M$, except possibly the diagonal entry $a_{2, 2}$, equal 0.

Continuing in this fashion, we see that all nondiagonal entries in the matrix $M$ equal 0. Thus (b) holds, completing the proof that (a) implies (b).

Now suppose (b) holds, so $T$ has a diagonal matrix with respect to some orthonormal basis of $V$. The matrix of $T^\ast$ (with respect to the same basis) is obtained by taking the conjugate transpose of the matrix of $T$; hence $T^\ast$ also has a diagonal matrix. Any two diagonal matrices commute; thus $T$ commutes with $T^\ast$, which means $T$ is normal. Thus (a) holds, completing the proof that (b) implies (a).

The equivalence of (b) and (c) follows from the definitions (also see 5.55).




## Exercises

### (1) Prove that a normal operator on a complex inner product space is self-adjoint if and only if all its eigenvalues are real.

Suppose $T \in L(V)$ and $F = C$.

$\Rightarrow$
Suppose $T$ is a self-adjoint operator. 

Then all its eigenvalues are real by 7.12.

$\Leftarrow$
Suppose $T$ is a normal operator with all real eigenvalues. 

By the spectral theorem (7.31), $V$ has an orthonormal basis consisting of eigenvectors of $T$. Let $e_1, ..., e_n$ be the orthonormal basis consisting of eigenvectors. Let $\lambda_1, ..., \lambda_n$ be the corresponding eigenvalues.

For any $v \in V$, we can write $v = a_1 e_1 + ... + a_n e_n$ for some $a_1, ..., a_n \in F$. We have

$$
\begin{aligned}
\langle Tv, v \rangle 
    &= \langle T(a_1 e_1 + ... + a_n e_n), a_1 e_1 + ... + a_n e_n \rangle \\
    &= \langle a_1 \lambda_1 e_1 + ... + a_n \lambda_n e_n, a_1 e_1 + ... + a_n e_n \rangle \\
    &= \lambda_1 a_1 \overline{a_1} \langle e_1, e_1 \rangle + ... + \lambda_n a_n \overline{a_n} \langle e_n, e_n \rangle \\
    &= \lambda_1 |a_1|^2 + ... + \lambda_n |a_n|^2 \\
    &\in R
\end{aligned}
$$

By 7.14, $T$ is self-adjoint.



### (2) Suppose $F = C$. Suppose $T \in L(V)$ is normal and has only one eigenvalue. Prove that $T$ is a scalar multiple of the identity operator.

Let $\lambda$ be the (only) eigenvalue of $T$.

By the spectral theorem 7.31, $V$ has an orthonormal basis consisting of eigenvectors of $T$. Let $e_1, ..., e_n$ be the orthonormal basis consisting of eigenvectors of $T$. 

We have $Te_k = \lambda e_k, k = 1, ..., n$. Since $Te_k$ is a scalar multiple of each basis vector, by linearity, $T$ is a scalar multiple of the identity operator.



### (3) Suppose $F = C$ and $T \in L(V)$ is normal. Prove that the set of eigenvalues of $T$ is contained in $\\{0, 1\\}$ if and only if there is a subspace $U$ of $V$ such that $T = P_U$.

$\Rightarrow$
Suppose the eigenvalues of $T$ are contained in {0, 1}. 

By the spectral theorem (7.31), $T$ is diagonalizable. By 5.55, $V = E(1, T) \oplus E(0, T)$. 

By 7.22, eigenvectors of $T$ corresponding to distinct eigenvalues are orthogonal, so $E(0, T) = E(1, T)^\perp$. Let $U = E(1, T)$, $U^\perp = (E(1, T))^\perp = E(0, T)$.

For any $v \in V$, we can write $v = u + w$, where $u \in U$ and $w \in U^\perp$.  We have 

$$Tv = T(u + w) = Tu + Tw = 1u + 0w = u.$$ 

Thus $T = P_U$.

$\Leftarrow$
Suppose there is a subspace $U$ of $V$ such that $T = P_U$. We have $V = U \oplus U^\perp$.

Let $e_1, ..., e_n$ be the orthonormal basis of $U$ and $f_1, ..., f_m$ be the orthonormal basis of $U^\perp$. 

$$Te_k = = P_U e_k = e_k = 1 e_k, k = 1, ..., n$$ 

and 

$$Tf_j = P_U f_j = 0 = 0 f_j, j = 1, ..., m.$$ 

The behavior of $T$ is completely determined by its action on the basis. Thus the eigenvalues of $T$ are contained in {0, 1}.



### (4) Prove that a normal operator on a complex inner product space is skew (meaning it equals the negative of its adjoint) if and only if all its eigenvalues are purely imaginary (meaning that they have real part equal to 0).

Suppose $T \in L(V)$ and $F = C$.

$\Rightarrow$
Suppose $T$ is a normal operator and $T$ skew ($T = - T^\ast$). 

Suppose $\lambda$ is an eigenvalue of $T$, and suppose $v \in V$ is the corresponding eigenvector. Then $Tv = \lambda v$. 

By 7.21 $T^\ast v = \overline{\lambda} v$. By hypothesis $T$ is skew so $Tv = T^\ast v$. Combining the equations, we have 

$$\lambda v = - \overline{\lambda} v .$$

Since $v \neq 0$, $\lambda = -\overline{\lambda}$. 

Suppose $\lambda = a + bi$ for some $a, b \in R$. Then $a + bi = - (a - bi) = bi - a$. Thus $a = 0$. 

We conclude the eigenvalues are purely imaginary.

$\Leftarrow$
Suppose $T$ is a normal operator and all its eigenvalues are purely imaginary. 

By 7.31, $V$ has an orthonormal basis consisting of eigenvectors of $T$. Let $e_1, ..., e_n$ be the orthonormal basis consisting of eigenvectors of $T$. Let $\lambda_1, ..., \lambda_n$ be the corresponding eigenvalues. 

Since the eigenvalues are purely imaginary, $\lambda_k = b_k i, b_k \in R, k = 1, ..., n$.

By 7.21, 

$$T^\ast e_k = \overline{\lambda_k} e_k = (-b_k i) e_k = - \lambda_k e_k = - T e_k.$$

Since this equality applies to each basis, by linearity, $T^\ast v = - Tv$ for all $v \in V$.

Hence $T^\ast = - T$ and $T$ is skew.



### (5)


### (8) Suppose $F = C$ and $T \in L(V)$. Prove that $T$ is normal if and only if every eigenvector of $T$ is also an eigenvector of $T^\ast$.

$\Rightarrow$
Suppose $T$ is normal. 

Suppose $v \in V, v \neq 0$ is an eigenvector of $T$. By 7.21, $v$ is an eigenvector of $T^\ast$.

$\Leftarrow$
Suppose every eigenvector of $T$ is also an eigenvector of $T^\ast$.

Suppose $v \in V, v \neq 0$ is an eigenvector of $T$. Then $Tv = \lambda v$ for some $\lambda \in F$, and $T^\ast v = \alpha v$ for some $\alpha \in F$. We have

$$
\begin{aligned}
\langle Tv, v \rangle 
    &= \langle \lambda v, v \rangle \\
    &= \lambda \langle v, v \rangle \\
    &= \lambda \lvert v \rvert^2
\end{aligned}
$$

We also have

$$
\begin{aligned}
\langle Tv, v \rangle 
    &= \langle v, T^\ast v \rangle \\
    &= \langle v, \alpha v \rangle \\
    &= \overline{\alpha} \langle v, v \rangle \\
    &= \overline{\alpha} \lvert v \rvert^2
\end{aligned}
$$

From the two equations above, we have 

$$\lambda \lvert v \rvert^2 = \overline{\alpha} \lvert v \rvert^2 .$$

Since $v \neq 0$, $\lvert v \rvert^2 \neq 0$. Thus $\overline{\alpha} = \lambda$, or $\alpha = \overline{\lambda}$.

By Schur's theorem (6.38), $T$ has an upper-triangular matrix with respect to some orthonormal basis $e_1, ..., e_n$. By 5.41, The eigenvalues of $T$ are the entries on the diagonal of the matrix. Thus we have 

$$
M(T, (e_1, ..., e_n)) = 
\begin{pmatrix}
\lambda_1 & a_{12} & ... & ... & a_{1n} \\
0 & \lambda_2 & a_{23} & ... & a_{2n} \\
... \\
0 & ... & ... & ... & \lambda_n 
\end{pmatrix}
$$

From the matrix, we have

$$T e_1 = \lambda e_1$$

and 

$$T^\ast e_1 = \overline{\lambda_1} e_1 + \overline{a_{12}} e_2 + ... + \overline{a_{1n}} e_n .$$

We also have 

$$T^\ast e_1 = \overline{\lambda_1} e_1$$

since $e_1$ is an eigenvector of $T$ and $T^\ast$. 

Since $e_1, ..., e_n$ is a basis, the equations imply that all entries in the first row of $M(T)$, except possibly $\lambda_1$, equal 0.

From the matrix, we have

$$T e_2 = \lambda_2 e_2$$

since $a_{12} = 0$ shown above, and 

$$T^\ast e_2 = \overline{\lambda_2} e_2 + \overline{a_{23}} e_3 + ... + \overline{a_{2n}} e_n .$$

We also have

$$T^\ast e_2 = \overline{\lambda_2} e_2 $$

since $e_2$ is an eigenvector of $T$ and thus an eigenvector of $T^\ast$.

The equations imply that in the second row of the matrix, except possibly $\lambda_2$, equal 0.

Continuing in this fashion, we see that all nondiagonal entries in the matrix equal 0. 

Hence $T$ has a diagonal matrix with respect to an orthonormal basis in $V$. By the spectral theorem (7.31), $T$ is normal.



### (13)


### (14) Suppose $F = R$ and $T \in L(V)$. Prove that $T$ is self-adjoint if and only if all pairs of eigenvectors corresponding to distinct eigenvalues of $T$ are orthogonal and $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$, where $\lambda_1, ..., \lambda_m$ denote the distinct eigenvalues of $T$.

$\Rightarrow$
Suppose $T$ is self-adjoint. It follows that $T$ is normal.

By 7.22, eigenvectors of $T$ corresponding to distinct eigenvalues of $T$ are orthogonal.

By the spectral theorem (7.29), $V$ has an orthonormal basis consisting of eigenvectors of $T$. By 5.55, $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$.

$\Leftarrow$
Suppose all pairs of eigenvectors corresponding to distinct eigenvalues of $T$ are orthogonal and $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$, where $\lambda_1, ..., \lambda_m$ denote the distinct eigenvalues of $T$.

For $j = 1, ..., m$, suppose $dim E (\lambda_j, T) = k_j$. Let $v_{j, 1}, ..., v_{j, k_j}$ be a basis of $E (\lambda_j, T)$. Apply the Gram-Schmidt procedure to each eigenspace to obtain an orthonormal basis $e_{j, 1}, ..., e_{j, k_j}$. Within each eigenspace, $e_{j, 1}, ..., e_{j, k_j}$ is an orthonormal basis. Since we applied the Gram-Schmidt procedure inside each eigenspace, $e_{j, 1}, ..., e_{j, k_j}$ are eigenvectors corresponding to eigenvalue $\lambda_j$. 

Together, $e_{j, k}, j = 1, ..., m, k = 1, ..., k_j$ is an orthonormal basis of $V$ consisting of eigenvectors of $T$. By 7.29, $T$ is self-adjoint.



### (15) Suppose $F = C$ and $T \in L(V)$. Prove that $T$ is normal if and only if all pairs of eigenvectors corresponding to distinct eigenvalues of $T$ are orthogonal and $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$, where $\lambda_1, ..., \lambda_m$ denote the distinct eigenvalues of $T$.

$\Rightarrow$
Suppose $T$ is normal.

By 7.22, eigenvectors of $T$ corresponding to distinct eigenvalues of $T$ are orthogonal.

By the spectral theorem (7.31), $V$ has an orthonormal basis consisting of eigenvectors of $T$. By 5.55, $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$.

$\Leftarrow$
Suppose all pairs of eigenvectors corresponding to distinct eigenvalues of $T$ are orthogonal and $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$, where $\lambda_1, ..., \lambda_m$ denote the distinct eigenvalues of $T$.

For $j = 1, ..., m$, suppose $dim E (\lambda_j, T) = k_j$. Let $v_{j, 1}, ..., v_{j, k_j}$ be a basis of $E (\lambda_j, T)$. Apply the Gram-Schmidt procedure to each eigenspace to obtain an orthonormal basis $e_{j, 1}, ..., e_{j, k_j}$. Within each eigenspace, $e_{j, 1}, ..., e_{j, k_j}$ is an orthonormal basis. Since we applied the Gram-Schmidt procedure inside each eigenspace, $e_{j, 1}, ..., e_{j, k_j}$ are eigenvectors corresponding to eigenvalue $\lambda_j$. 

Together, $e_{j, k}, j = 1, ..., m, k = 1, ..., k_j$ is an orthonormal basis of $V$ consisting of eigenvectors of $T$. By 7.31, $T$ is normal.



### (19) Suppose $T \in L(V)$ is self-adjoint and $U$ is a subspace of $V$ that is invariant under $T$.

#### (a) Prove that $U^\perp$ is invariant under $T$.

In 7A we proved that $U$ is invariant under $T$ $\iff$ $U^\perp$ is invariant under $T^\ast$. 

Since $T$ is self-adjoint, $T = T^\ast$, so $U^\perp$ is invariant under $T$.


#### (b) Prove that $T|_U \in L(U)$ is self-adjoint.

Suppose $u, w \in U$. We have 

$$
\begin{aligned}
\langle T|_U u, w \rangle 
    &= \langle Tu, w \rangle \\
    &= \langle u, T^\ast w \rangle \\
    &= \langle u, Tw \rangle \\
    &= \langle u, T|_U w
\end{aligned}
$$

for all $u, w \in U$. The first and last equality follow because $U$ is $T$-invariant so we can interchange $T$ and $T|_U$; the third equality follows because $T$ is self-adjoint. 

Hence $T|_U \in L(U)$ is self-adjoint.


#### (c) Prove that $T|_{U^\perp} \in L(U^\perp)$ is self-adjoint.

Since $U^\perp$ is invariant under $T$ (shown in part a), we can use the same argument as part b to show that $T|_{U^\perp} \in L(U^\perp)$ is self-adjoint.



### (20) Suppose $T \in L(V)$ is normal and $U$ is a subspace of $V$ that is invariant under $T$. Note: This exercise can be used to give yet another proof of the complex spectral theorem (use induction on $dim V$ and the result that $T$ has an eigenvector).

#### (b) Prove that $U$ is invariant under $T^\ast$.

We will prove (b) first then use (b) to show (a).

Suppose $e_1, ..., e_m$ is an orthonormal basis of $U$. We can extend to an orthonormal basis $e_1, ..., e_m, e_{m+1}, ..., e_{n}$ of $V$ by 6.36. 

We have 

$$
M(T, (e_1, ..., e_m, e_{m+1}, ..., e_n)) =
\begin{pmatrix}
a_{1,1} & ... & a_{1,m} & a_{1, m+1} & ... & b_{1,n} \\
a_{2,1} & ... \\
... \\
a_{m,1} & ... & a_{m,m} & ... \\
... \\
0 & ... & ... 
\end{pmatrix}
$$

Since $U$ is invariant under $T$, $Te_k$ has no terms in $e_{m+1}, ..., e_n$. We can write

$$Te_k = a_{1,k} e_1 + ... a_{m,k} e_m .$$

Similarly, we can write 

$$T^\ast e_k = \overline{a_{k,1}} e_1 + ... + \overline{a_{k,m}} e_m + \overline{a_{k, m+1}} e_{m+1} + ... + \overline{a_{k, n}} e_n .$$

Since $T$ is normal, 

$$\lvert Te_k \rvert^2 = \lvert T^\ast e_k \rvert^2$$

and 

$$\sum_{k=1}^m \lvert Te_k \rvert^2 = \sum_{k=1}^m \lvert T^\ast e_k \rvert^2 .$$

We have

$$LHS = \sum_{k=1}^m \sum_{j=1}^m |a_{j, k}|^2$$

and

$$
\begin{aligned}
RHS 
    &= \sum_{k=1}^m (\sum_{j=1}^m |a_{k, j}|^2 + \sum_{j=m+1}^n |a_{k, j}|^2 ) \\
    &= (\sum_{k=1}^m \sum_{j=1}^m |a_{k, j}|^2) + (\sum_{k=1}^m \sum_{j=m+1}^n |a_{k, j}|^2 )
\end{aligned}
$$

Note that the first half of the RHS is just a relabeling of the LHS. We have

$$LHS = LHS + \sum_{k=1}^m \sum_{j=m+1}^n |a_{k, j}|^2.$$

Thus the nonnegative double sum $\sum_{k=1}^m \sum_{j=m+1}^n |a_{k, j}|^2$ equals 0, forcing each $a_{k, m+1}, ..., a_{k, n}$ to be 0. Hence

$$T^\ast e_k = \overline{a_{k,1}} e_1 + ... + \overline{a_{k,m}} e_m,$$

and we conclude that $U$ is invariant under $T^\ast$.


#### (a) Prove that $U^\perp$ is invariant under $T$.

Suppose $v \in U^\perp, u \in U$. We have

$$\langle Tv, u \rangle = \langle v, T^\ast u \rangle = 0$$

where the second equality follows from part b above (i.e. $U$ is invariant under $T^\ast$).

Thus $Tv$ is orthogonal to $U$, and $Tv \in U^\perp$. Hence $U^\perp$ is invariant under $T$.


#### (c) Prove that $(T|_U)^\ast = (T^\ast)|_U$.

Suppose $u, w \in U$. We have, for all $u \in U$, 

$$
\begin{aligned}
\langle T|_U u, w \rangle 
    &= \langle Tu, w \rangle \\
    &= \langle u, T^\ast w \rangle \\
    &= \langle u, (T^\ast)|_U w \rangle
\end{aligned}
$$

where the third equality follows from the fact that $U$ is invariant under $T^\ast$.

Hence $(T|_U)^\ast = (T^\ast)|_U$.


#### (d) Prove that $T|_U \in L(U)$ and $T|{U^\ast} \in L(U^\perp)$ are normal operators.

Suppose $v \in U$. 

Since $T \in L(V)$ is normal, $T T^\ast v = T^\ast T v$. We have

$$(T|_U) (T|_U)^\ast v = (T|_U) (T^\ast)|_U v = T T^\ast v$$

where the first equality follows form part (c) and the second equality follows from the fact that $U$ is invariant under $T$ and $T^\ast$,

and similarly

$$(T|_U)^\ast (T|_U) v = (T^\ast)|_U (T|_U) v = T^\ast T v.$$

Thus $(T|_U) (T|_U)^\ast v = (T|_U)^\ast (T|_U) v$, and $T|_U \in L(U)$ is normal.

We can use the same argument to show that $T|{U^\ast} \in L(U^\perp)$ is normal.

