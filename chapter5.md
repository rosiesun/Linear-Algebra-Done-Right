Linear Algebra Done Right - Chapter 5 <br>
Eigenvalues and Eigenvectors
================
Rosie Sun <br>
2026-04-21


# 5A Invariant Subspaces

### 5.1 Definition: operator
A linear map from a vector space to itself is called an operator.


### 5.2 Definition: invariant subspace
Suppose $T \in L(V)$. A subspace $U$ of $V$ is called invariant under $T$ if $Tu \in U$ for every $u \in U$.


### 5.5 Definition: eigenvalue
Suppose $T \in L(V)$. A number $\lambda \in F$ is called an eigenvalue of $T$ if there exists $v \in V$ such that $v \neq 0$ and $Tv = \lambda v$.


### 5.7
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $\lambda \in F$. Then the following are equivalent. 

- $\lambda$ is an eigenvalue of $T$.
- $T - \lambda I$ is not injective.
- $T - \lambda I$ is not surjective.
- $T - \lambda I$ is not invertible.


### 5.8 Definition: eigenvector
Suppose $T \in L(V)$ and $\lambda \in F$ is an eigenvalue of $T$. A vector $v \in V$ is called an eigenvector of $T$ corresponding to $\lambda$ if $v \neq 0$ and $Tv = \lambda v$.


### 5.11 
Suppose $T \in L(V)$. Then every list of eigenvectors of $T$ corresponding to distinct eigenvalues of $T$ is linearly independent.

Proof: 

Suppose the desired result is false. 

Then there exists a smallest positive integer $m$ such that there exists a linearly dependent list $v_1,...,v_m$ of eigenvectors of $T$ corresponding to distinct eigenvalues $\lambda_1,...,\lambda_m$ of $T$ (note that $m \geq 2$ because an eigenvector is by definition nonzero). 

Thus there exist $a_1,...,a_m \in F$, none of which are 0 (because of the minimality of $m$), such that 

$$a_1 v_1 + ... + a_m v_m = 0$$

Applying $T - \lambda_m I$ to both sides of the equation, getting

$$a_1 (\lambda_1 - \lambda_m) v_1 + ... + a_{m-1} (\lambda_{m-1} - \lambda_m) v_{m-1} = 0$$

Because the eigenvalues $\lambda_1,...,\lambda_m$ are distinct, none of the coefficients above equal 0. Thus $v_1,...,v_{m-1}$ is a linearly dependent list of $m-1$ eigenvectors of $T$ corresponding to distinct eigenvalues, contradicting the minimality of $m$. 

This contradiction completes the proof.


### 5.12
Suppose $V$ is finite-dimensional. Then each operator on $V$ has at most $dim V$ distinct eigenvalues.

Proof:

Let $T \in L(V)$. Suppose $\lambda_1, ..., \lambda_m$ are distinct eigenvalues of $T$. Let $v_1, ..., v_m$ be corresponding eigenvectors. Then 5.11 implies that the list $v_1, ..., v_m$ is linearly independent. Thus $m \leq dim V$ (by 2.22), as desired.


### 5.13 Notation
Suppose $T \in L(V)$ and $m$ is a positive integer.

- $T^m \in L(V)$ is defined by $T^m = T ... T$ ($m$ times).
- $T^0$ is defined to be the identity operator $I$ on $V$.
- If $T$ is invertible with inverse $T^{-1}$, then $T^{-m} \in L(V)$ is defined by $T^{-m} = (T^{-1})^m$.


### 5.14
Suppose $T \in L(V)$ and $p \in P(F)$ is a polynomial given by 

$$p(z) = a_0 + a_1 z + a_2 z^2 + ... + a_m z^m$$

for all $z \in F$. Then $p(T)$ is the operator on $V$ defined by

$$p(T) = a_0 I + a_1 T + a_2 T^2 + ... + a_m T^m$$


### 5.16 Definition: product of polynomials
If $p, q \in P(F)$, then $pq \in P(F)$ is the polynomial defined by

$$(pq)(z) = p(z) q(z)$$

for all $z \in F$.


### 5.17
Suppose $p, q \in P(F)$ and $T \in L(V)$. Then

- $(pq)(T) = p(T) q(T)$
- $p(T) q(T) = q(T) p(T)$



### 5.18
Suppose $T \in L(V)$ and $p \in P(F)$. Then $null p(T)$ and $range p(T)$ are invariant under $T$.

Proof:

Suppose $u \in null p(T)$. Then $p(T)u = 0$. Thus 

$$(p(T))Tu = (p(T)T)u = (Tp(T))u = T(p(T)u) = T0 = 0$$

Hence $Tu \in null p(T)$. Thus $null p(T)$ is invariant under $T$, as desired.

Suppose $u \in range p(T)$. Then there exists $v \in V$ such that $p(T)v = u$. Thus 

$$Tu = T(p(T)v) = (p(T)T)v = p(T)(Tv)$$

Hence $Tu \in range p(T)$. Thus $range p(T)$ is invariant under $T$, as desired.




## Exercises

### (1) Suppose $T \in L(V)$ and $U$ is a subspace of $V$. 

#### (a) Prove that if $U \subseteq null T$, then $U$ is invariant under $T$.

Let $u \in U$. Then $u \in U \subseteq null T$. Thus $Tu=0$. Since $0$ is in any subspace, $Tu \in U$. Therefore $U$ is invariant under $T$.

#### (b) Prove that if $range T \subseteq U$, thten $U$ is invariant under $T$.

Let $u \in U$. Then $Tu \in range T \subseteq U$. Therefore $U$ is invariant under $T$.



### (2) Suppose that $T \in L(V)$ and $V_1,...,V_m$ are subspaces of $V$ invariant under $T$. Prove that $V_1 + ... + V_m$ is invariant under $T$.

Let $v \in V_1 + ... + V_m$. Then we can write $v = v_1 + ... + v_m$ for some $v_1 \in V_1, ..., v_m \in V_m$. Then $Tv = T(v_1 + ... + v_m) = Tv_1 + ... + Tv_m$. By assumption, $V_1,...,V_m$ are invariant under $T$, so $Tv_1 \in V_1, ..., Tv_m \in V_m$. Thus $Tv \in V_1 + ... + V_m$, and we conclude that $V_1 + ... + V_m$ is invariant under $T$.



### (4) Prove or give a counterexample: If $V$ is finite-dimensional and $U$ is a subspace of $V$ that is invariant under every operator on $V$, then $U=\\{0\\}$ or $U=V$.

Suppose $U \neq \\{0\\}$. Let $u \in U, u \neq 0$. We can decompose $V$ such that $V = span(u) \oplus W$. 

For any $v \in V$, define the linear operator $T$ such that 

$$Tu = v$$

$$Tw = 0, w \in W$$

By assumption, $u \in U$ implies $Tu \in U$. Since $Tu = v$, $v \in U$. But $v \in V$ was arbitrary, so we conclude $U = V$.



### (5) Suppose $T \in L(R^2)$ is defined by $T(x,y) = (-3y, x)$. Find the eigenvalues of $T$.

There are no real eigenvalues.



### (6) Define $T \in L(F^2)$ by $T(w,z) = (z,w)$. Find all eigenvalues and eigenvectors of $T$.

Eigenvalue 1, eigenvectors $\\{(w,z) \in R^2: w=z\\}$

Eigenvalue -1, eigenvectors $\\{(w,z) in R^2: w = -z\\}$.



### (7) Define $T \in L(F^3)$ by $T(z_1,z_2,z_3) = (2z_2, 0, 5z_3)$. Find all eigenvalues and eigenvectors of $T$.

Eigenvalue 5, eigenvectors $span(z_3)$.

Eigenvalue 0, eigenvectors $span(z_1)$.



### (8) Suppose $P \in L(V)$ is such that $P^2 = P$. Prove that if $\lambda$ is an eigenvalue of $P$, then $\lambda = 0$ or $\lambda = 1$.

Suppose $\lambda$ is an eigenvalue of $P$. Then $Pv = \lambda v$ for some nonzero $v \in V$. Applying $P$ to both sides, we have 

$$PPv = P lambda v = \lambda Pv = \lambda (\lambda v) = \lambda^2 v$$

Since $P^2 = P$, we also have 

$$PPv = Pv = \lambda v$$

$$\lambda^2 v = \lambda v$$

Rearranging, we have

$$\lambda (\lambda - 1) v = 0$$

Since $v \neq 0$, we must have $\lambda (\lambda - 1) = 0$. Thus $\lambda = 1$ or $\lambda = 0$.



### (9)

### (10)

### (11)

### (12) Suppose $V = U \oplus W$, where $U$ and $W$ are nonzero subspaces of $V$. Define $P \in L(V)$ by $P(u+w) = u$ for each $u \in U, w \in W$. Find all eigenvalues and eigenvectors of $P$.

Eigenvalue 1, eigenvectors $u \in U, u \neq 0$.

Eigenvalue 0, eigenvectors $w \in W, w \neq 0$.



### (13) Suppose $T \in L(V)$. Suppose $S \in L(V)$ is invertible.

#### (a) Prove that $T$ and $S^{-1} T S$ have the same eigenvalues.

Suppose $\lambda$ is an eigenvalue of $T$ corresponding to some eigenvector $v \in V$. Then $Tv = \lambda v$. 

Since $S$ is invertible, there is some $u \in V$ such that $Su = v$. 

$$S^{-1} T Su = S^{-1} T v = S^{-1} (\lambda v) = \lambda S^{-1} v = \lambda u$$

Therefore $\lambda$ is an eigenvalue of $S^{-1} T S$.


#### (b) What is the relationship between the eigenvectors of $T$ and the eigenvectors of $S^{-1} T S$?

If $v$ is an eigenvector of $T$, then $S^{-1}v$ is an eigenvector of $S^{-1} T S$.



### (14) Give an example of an operator on $R^4$ that has no (real) eigenvalues.

$$T(x_1, x_2, x_3, x_4) = (-x_2, x_1, -x_4, x_3)$$



### (15) Suppose $V$ is finite-dimensional, $T \in L(V)$, and $\lambda \in F$. Show that $\lambda$ is an eigenvalue of $T$ if and only if $\lambda$ is an eigenvalue of the dual operator $T' \in L(V')$.

$\Rightarrow$
Suppose $\lambda \in F$ is an eigenvalue of $T$. Then $T - \lambda I$ is not surjective by 5.7. From 3.129, we have $T' - \lambda I'$ is not injective. Thus $\lambda$ is an eigenvalue of $T'$.

$\Leftarrow$
Suppose $\lambda \in F$ is an eigenvalue of $T'$. Then $T' - \lambda I'$ is not surjective by 5.7. From 3.131, we have $T - \lambda I$ is not injective. Thus $\lambda$ is an eigenvalue of $T$.



### (16) Suppose $v_1, ..., v_n$ is a basis of $V$ and $T \in L(V)$. Prove that if $\lambda$ is an eigenvalue of $T$, then $|\lambda| \leq n max { |M(T)_{j,k} }$ where $1 \leq 1, j \leq n$, $M(T)_{j,k}$ denotes the entry in row j, column k of the matrix of $T$ with respect to the basis $v_1, ..., v_n$.

Suppose $\lambda \in F$ is an eigenvalue of $T$. Suppose $v \in V, v \neq 0$ is the corresponding eigenvector of $T$. Then $Tv = \lambda v$. Since $v_1, ..., v_n$ is a basis of $V$, we can write $v = a_1 v_1 + ... + a_n v_n$ for some $a_1, ..., a_n \in F$. Then 

$$Tv = a_1 Tv_1 + ... + a_n Tv_n$$

and 

$$\lambda v = \lambda a_1 v_1 + ... + \lambda a_n v_n.$$

From 3.31, the definition of $M(T)$, we have

$$Tv_k = M_{1,k} v_1 + ... + M_{n,k} v_n$$

So we have 

$$
\begin{aligned}
Tv &= a_1 (M_{1,1} v_1 + ... + M_{n,1} v_n) + ... + a_n (M_{1,n} v_1 + ... + M_{n,n} v_n) \\
&= a_1 M_{1,1} v_1 + ... + a_n M_{1,n} v_1 + ... + a_1 M_{n,1} v_n + ... + a_n M_{n,n} v_n \\
&= (\sum_{k=1}^n a_k M_{1,k}) v_1 + ... + (\sum_{k=1}^n a_k M_{n,k}) v_n
\end{aligned}
$$

Because $v_1, ..., v_n$ is a basis, the linear combination is unique. 

Therefore, for each row j, where $j = 1,...,n$,

$$a_j \lambda = \sum_{k=1}^n a_k M_{j,k}$$

Since $v$ is an eigenvector, $v \neq 0$. Therefore at least one coefficient is nonzero. Pick $a_{j'}$ such that 

$$|a_{j'}| = max_{j} |a_j| .$$

Consider the equation

$$a_{j'} \lambda = \sum_{k=1}^n a_k M_{j', k}$$

Using the triangle inequality, we have

$$
\begin{aligned}
|a_{j'}| |\lambda| 
    &= |a_{j'} \lambda| \\
    &= | \sum_{k=1}^n a_k M_{j', k} | \\
    &\leq \sum_{k=1}^n |a_k| |M_{j', k}|
\end{aligned}
$$

Let $M'$ be such that $|M'| = max_{j,k} |M_{j,k}|$. Then 

$$\sum_{k=1}^n |a_k| |M_{j', k}| \leq \sum_{k=1}^n |a_{j'}| |M'| = n |a_{j'}| |M'|$$

Combining the two inequalities, we have

$$|a_{j'}| |\lambda| \leq n |a_{j'}| |M'| .$$

Since we showed earlier $|a_{j'}| \neq 0$, we can divide it from both sides. Thus we have

$$|\lambda| \leq n |M'| .$$



### (21) Suppose $T \in L(V)$ is invertible.

#### (a) Suppose $\lambda \in F$ with $\lambda \neq 0$. Prove that $\lambda$ is an eigenvalue of $T$ if and only if $1/\lambda$ is an eigenvalue of $T^{-1}$.

$\Rightarrow$
Let $\lambda$ be an eigenvalue of $T$ corresponding to some $v \in V$. Then $Tv = \lambda v$. Applying $T^{-1}$ to both sides, we have

$$T^{-1} T v = T^{-1} \lambda v$$

$$v = \lambda T^{-1} v$$

$$T^{-1} v = 1/\lambda v$$

Thus $\lambda$ is an eigenvalue of $T^{-1}$.

$\Leftarrow$
Let $1/\lambda$ be an eigenvalue of $T^{-1}$ corresponding to some $v \in V$. Then $T^{-1}v = 1/\lambda v$. Applying $T$ to both sides, we have

$$T T^{-1}v = T (1/\lambda) v$$

$$v = 1/\lambda T v$$

$$T v = \lambda v$$

Thus $\lambda$ is an eigenvalue of $T$.


#### (b) Prove that $T$ and $T^{-1}$ have the same eigenvectors.

From the equations from (a), they have the same eigenvectors.



### (22) Suppose $T \in L(V)$ and there exist nonzero vectors $u$ and $w$ in $V$ such that $Tu = 3w$ and $Tw = 3u$. Prove that 3 or -3 is an eigenvalue of $T$.

Suppose $u, w \in V$ and $u, w \neq 0$. We have

$$T(u + w) = Tu + Tw = 3w + 3u = 3(u + w) .$$

If $u + w \neq 0$, then 3 is an eigenvalue of $T$ and the corresponding eigenvector is $u+w$.

If $u + w = 0$, then $u = -w$ and $w = -u$. We have 

$$Tu = 3(-u) = -3u$$ 

and

$$Tw = 3(-w) = -3w .$$

Thus -3 is an eigenvalue of $T$ and the corresponding eigenvectors are $u$ and $w$.



### (23) Suppose $V$ is finite-dimensional and $S,T \in L(V)$. Prove that $ST$ and $TS$ have the same eigenvalues.

Let $\lambda$ be an eigenvalue of $ST$ corresponding to some $v \in V, v \neq 0$. Then 

$$STv = \lambda v$$. 

Applying $T$ to both sides, we have 

$$TSTv = T \lambda v$$

$$TS(Tv) = \lambda (Tv)$$

Since $v \neq 0$, $Tv=0$ if $\lambda = 0$.

If $\lambda = 0$, then $null ST \neq \\{0\\}$. We have $TS(Tv) = 0$. Then $Tv \in null TS$. $\lambda$ is an eigenvalue of $TS$.

If $\lambda \neq 0$, then $TS(Tv) = \lambda (Tv)$ implies that $Tv$ is an eigenvector of $TS$ with eigenvalue of $\lambda$.

The other direction follows by switching the order of $S$ and $T$.



### (24) Suppose $A$ is an n-by-n matrix with entries in $F$. Define $T \in L(F^n)$ by $Tx = Ax$, where elements of $F^n$ are thought of as n-by-1 column vectors.

#### (a) Suppose the sum of the entries in each row of $A$ equals 1. Prove that 1 is an eigenvalue of $T$.

Suppose $e_1, ..., e_n$ is the standard basis of $F^n$. Consider $x = e_1 + ... + e_n, x \neq 0$. Then using matrix multiplication, we have

$$
A  
\begin{pmatrix}
1 \\
.. \\
1 
\end{pmatrix}
= 
\begin{pmatrix}
\sum_{k=1}^n A_{1,k} * 1\\
... \\
\sum_{k=1}^n A_{n,k} * 1
\end{pmatrix}
=
\begin{pmatrix}
1 \\
... \\
1
\end{pmatrix}
$$

Hence 1 is an eigenvalue and $x = e_1 + ... + e_n$ is the corresponding eigenvector.


#### (b) Suppose the sum of the entries in each column of $A$ equals 1. Prove that 1 is an eigenvalue of $T$.

From 3.132 we have $M(T') = (M(T))^t$. Consider $A^t = M(T')$. Then the sum of the entries of each row of $A^t$ equals 1. 

Then 1 is an eigenvalue of $T'$ from part (a).

From exercise 15, we showed that $\lambda$ is an eigenvalue of $T$ if and only if $\lambda$ is an eigenvalue of $T'$. Thus we conclude 1 is an eigenvalue of $T$.



### (25) Suppose $T \in L(V)$ and $u, w$ are eigenvectors of $T$ such that $u+w$ is also an eigenvector of $T$. Prove that $u$ and $w$ are eigenvectors of $T$ corresponding to the same eigenvalue.

Since $u, w$ are eigenvectors of $T$, there is some $\lambda_1, \lambda_2 \in F$ such that $Tu = \lambda_1 u$ and $Tw = \lambda_2 w$.

Since $u+w$ is an eigenvector of $T$, some is some $\lambda_3 \in F$ such that $T(u+w) = \lambda_3 (u+w)$.

Assume towards contradiction that $\lambda_1 \neq \lambda_2$. We have 

$$T(u+w) = \lambda_3 u + \lambda_3 w$$

$$T(u+w) = Tu + Tw = \lambda_1 u + \lambda_2 w$$

$$(\lambda_1 - \lambda_3) u + (\lambmda_2 - \lambda_3) w = 0$$

By 5.11, every list of eigenvectors of $T$ corresponding to distinct eigenvalues of $T$ is linearly independent. By 2.15, $\lambda_1 - \lambda_3 = 0$ and $\lambda_2 - \lambda_3 = 0$. Thus $\lambda_1 = \lambda_3 = \lambda_2$. But this is a contradiction. 

Therefore we conclude that $\lambda_1 = \lambda_2$.



### (26) Suppose $T \in L(V)$ is such that every nonzero vector in $V$ is an eigenvector of $T$. Prove that $T$ is a scalar multiple of the identity operator.

Let $u, w \in V, u, w \neq 0$. Then $u, w$ are eigenvectors of $T$. 

$Tu = \lambda_1 u$ and $Tw = \lambda_2 w$.

If $u+w \neq 0$, $u+w$ is an eigenvector of $T$. From exercise (25), $u, w, u+w$ have the same eigenvalue $\lambda$. 

If $u+w = 0$, $w = -u$. We have $Tw = -Tu = -\lambda_1 u$. We also have $Tw = \lambda_2 w = -\lambda_2 u$. $-\lambda_1 u = -\lambda_2 u$, since $u \neq 0$, $\lambda_1 = \lambda_2$.

Therefore every vector in $V$ has the same eigenvalue. We conclude that $T = \lambda I$.



### (27) Suppose that $V$ is finite-dimensional and $k \in \\{1,...,dimV - 1\\}$. Suppose $T \in L(V)$ is such that every subspace of $V$ of dimension $k$ is invariant under $T$. Prove that $T$ is a scalar multiple of the identity operator.

Suppose $dim V = n$.

If $k=1$, then every 1-dimensional subspace $U$ is invariant under $T$. For any $u \in U$, $Tu \in U$. Then $Tu = \lambda u$ for some $\lambda \in F$. Then $u$ is an eigenvector of $T$. Since every 1-dimensional subspace $U$ is invariant, every nonzero vector is an eigenvector. We can apply exercise (26) and conclude that $T$ is a scalar multiple of the identity operator.

If $k \neq 1$, assume towards contradiction that there exists $v \in V$ such that $span(v)$ is not invariant under $T$. Then $Tv \notin span(v)$, so $v, Tv$ are linearly independent. Construct two k-dimensional subspaces 

$$U_1 = span(v, Tv, u_3,...,u_k)$$

$$U_2 = span(v, u_2, u_3, ..., u_k)$$

such that $Tv \notin U_2$. This is possible because $k < n$.

By hypothesis, $U_1$ and $U_2$ are invariant under $T$. Since $v \in U_2$, $Tv \in U_2$. But this is a contradiction. Therefore we conclude that every 1-dimensional subspace is invariant under $T$. We can apply exercise (26) and conclude $T$ is a scalar multiple of the identity operator.



### (28) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that $T$ has at most $1 + dim range T$ distinct eigenvalues.

By 5.12, $T$ has at most $dim V$ distinct eigenvalues. 

If $dim null T = 0$, then $dim V = dim range T$, so $T$ has at most $dim range T$ eigenvalues.

If $dim null T \neq 0$, then 0 is an eigenvalue of $T$. $range T$ is invariant under $T$ by 5.4. Applying 5.12 to the restriction $T:range T \rightarrow range T$, $T|_{range T}$ has at most $dim range T$ distinct eigenvaluges. Therefore $T$ has at most $1 + dim range T$ eigenvalues.



### (31) Give an example of $T \in L(R^2)$ such that $T^4 = -I$.


### (32) Suppose $T \in L(V)$ has no eigenvalues and $T^4 = I$. Prove that $T^2 = -I$.


### (33) Suppose $T \in L(V)$ and $m$ is a positive integer.

#### (a) Prove that $T$ is injective if and only if $T^m$ is injective.

$\Rightarrow$
Suppose $T$ is injective. 

First we want to show that compositions of injective maps are injective. Let $T_1, T_2 \in L(V)$ be injective linear maps. Suppose $T_1 T_2 v = 0$. Then $T_2 v = 0$ (from the injectivity of $T_1$). Then we have $v = 0$ (from the injectivity of $T_2$). Thus $T_1 T_2$ is injective. 

We can apply what we just showed to $T^m$ and conclude that $T^m$ is injective.

$\Leftarrow$
Suppose $T^m$ is injective. Then $null T^m = \\{0\\}$. 

Suppose $Tv = 0$. Applying $T$ m times, we have $T^m v = 0$. Since $T^m$ is injective, $v = 0$. Thus $T$ is injective.


#### (b) Prove that $T$ is surjective if and only if $T^m$ is surjective.

$\Rightarrow$
Suppose $T$ is surjective.

First we want to show that compositions of surjective maps are surjective. Let $T_1, T_2 \in L(V)$ be surjective linear maps. Let $w \in V$. Since $T_1$ is surjective, there exists $u \in V$ such that $T_1 u = w$. Since $T_2$ is surjective, there exists $v \in V$ such that $T_2 v = u$. Then $T_1 T_2 v = T_1 u = w$. Therefore $w \in range (T_1 T_2)$. Hence $T_1 T_2$ is surjective.

We can apply what we just showed to $T^m$ and conclude that $T^m$ is surjective.

$\Leftarrow$
Suppose $T^m$ is surjective. Then $range T^m = V$.

Let $v \in V$. Then there exists some $u \in V$ such that $T^m u = v$. We can write $T (T^{m-1} u) = v$. Thus $v \in range T$. We conclude that $T$ is surjective.



### (34) Suppose $V$ is finite-dimensional and $v_1,...,v_m \in V$. Prove that the list $v_1,...,v_m$ is linearly independent if and only if there exists $T \in L(V)$ such that $v_1,...,v_m$ are eigenvectors of $T$ corresponding to distinct eigenvalues.

$\Leftarrow$
Suppose there exists $T \in L(V)$ such that $v_1,...,v_m$ are eigenvectors of $T$ corresponding to distinct eigenvalues. 

Then by 5.11, $v_1,...,v_m$ are linearly independent. 

$\Rightarrow$
Suppose $v_1,...,v_m$ is linearly independent. 

Extend to a basis $v_1,...,v_m, w_1,...,w_n$ of $V$. Define $T \in L(V)$ such that $Tv_i = \lambda_i v_i, i=1,...,m$, $\lambda_i$ all distinct. $Tw_j = 0, j = 1,...,n$. 



### (37) Suppose $V$ is finite-dimensional and $T \in L(V)$. Define $A \in L(L(V))$ by $A(S) = TS$ for each $S \in L(V)$. Prove that the set of eigenvalues of $T$ equals the set of eigenvalues of $A$.


### (38) Suppose $V$ is finite-dimensional, $T \in L(V)$, and $U$ is a subspace of $V$ invariant under $T$. The quotient operator $T/U \in L(V/U)$ is defined by $(T/U)(v + U) = Tv + U$ for each $v \in V$. 

#### (a) Show that the definition of $T/U$ makes sense (which requires using the condition that $U$ is invariant under $T$) and show that $T/U$ is an operator on $V/U$.

First we want to show that the definition of $T/U$ makes sense. 

Suppose $v_1 + U, v_2 + U \in V/U$ and $v_1 + U = v_2 + U$. Then by 3.101 $v_1 - v_2 \in U$. Since $U$ is invariant under $T$, $T(v_1 - v_2) \in U$. Thus $Tv_1 - Tv_2 \in U$, and $Tv_1 + U = Tv_2 + U$ by 3.101. Then we have

$$(T/U) (v_1 + U) = Tv_1 + U = Tv_2 + U = (T/U) (v_2 + U).$$

Hence the definition makes sense.

Next we want to show that $T/U$ is a linear map. 

Suppose $v_1 + U, v_2 + U \in V/U$. Then 

$$
\begin{aligned}
(T/U) ( (v_1 + U) + (v_2 + U) ) &= (T/U) ((v_1 + v_2) + U) \\
    &= T(v_1 + v_2) + U \\
    &= (Tv_1 + Tv_2) + U \\
    &= (Tv_1 + U) + (Tv_2 + U) \\
    &= (T/U)(v_1 + U) + (T/U)(v_2 + U)
\end{aligned}
$$

Suppose $v + U \in V/U, \lambda \in F$. Then 

$$
\begin{aligned}
(T/U) (\lambda (v+U)) &= (T/U) (\lambda v + U) \\
    &= T(\lambda v) + U \\
    &= (\lambda Tv) + U \\
    &= \lambda (Tv + U) \\
    &= \lambda ((T/U) (v + U))
\end{aligned}
$$

Thus $T/U$ satisfies additivity and homogeneity. Since $(T/U): V/U \rightarrow V/U$, $T/U$ is an operator on $V/U$.


#### (b) Show that each eigenvalue of $T/U$ is an eigenvalue of $T$.

Suppose $\lambda \in F$ is an eigenvalue of $T/U$. Then there exists $v + U \in V/U$, $v + U \neq 0 + U$ such that 

$$(T/U)(v + U) = \lambda (v+ U).$$

Then we have

$$Tv + U = \lambda v + U.$$

Thus $v \notin U$ and 

$$Tv - \lambda v = (T - \lambda I) v \in U.$$

Assume towards contradiction that $\lambda$ is not an eigenvalue of $T$. Then $T - \lambda I$ is injective by 5.7.

Note that $U$ is invariant under $T - \lambda I$ since for any $u \in U$, $(T - \lambda I) u = Tu - \lambda u \in U$. 

Consider the restriction $(T - \lambda I)|_U: U \rightarrow U$. Then $(T - \lambda I)|_U$ is injective. Since $V$ is finite-dimensional, $U$ is finite-dimensional, and thus $(T - \lambda I)|_U$ is surjective from $U$ onto $U$. 

Since $Tv - \lambda v \in U$, there exists some $w \in U$ such that $(T - \lambda I) w = (T - \lambda I) v$. Then $(T - \lambda I)|_U (v - w) = 0$. Since $T - \lambda I$ is injective, $v - w = 0$. However this is a contradiction since $v \notin U$.



### (39) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that $T$ has an eigenvalue if and only if there exists a subspace of $V$ of dimension $dim V - 1$ that is invariant under $T$.









--------------------------------------------------------------------------------
# 5B The Minimal Polynomial

### 5.19
Every operator on a finite-dimensional nonzero complex vector space has an eigenvalue.

Proof:

Suppose $V$ is a finite-dimensional complex vector space of dimension $n>0$ and $T \in L(V)$. Choose $v \in V, v \neq 0$. Then

$$v, Tv, T^2v, ..., T^n v$$

is not linearly independent, because $dim V = n$ and this list has length $n+1$.

Thus there exists a nonconstant polynomial $p$ of smalllest degree such that 

$$p(T)v = 0$$

By 4.12, there exists $\lambda \in C$ such that $p(\lambda)=0$. Hence there exists a polynomial $q \in P(C)$ such that 

$$p(z) = (z-\lambda) q(z)$$

for every $z \in C$ by 4.6. This implies (using 5.17) that 

$$0 = p(T)v = (T-\lambda I) (q(T)v)$$

Because $q$ has smaller degree than $p$, we know that $q(T)v \neq 0$. Thus teh equation above implies that $\lambda$ is an eigenvalue of $T$ with eigenvector $q(T)v$.


### 5.21 Definition: monic polynomial
A monic polynomial is a polynomial whose highest-degree coefficient equals 1.


### 5.22
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then there is a unique monic polynomial $p \in P(F)$ of smallest degree such that $p(T) = 0$. Furthermore, $deg p \leq deg V$.

Proof:

If $dim V = 0$, then $I$ is the zero operator on $V$ and thus we take $p$ to be the constant polynomial 1.

Now use induction on $dim V$. Thus assume that $dim V > 0$ and that the desired result is true for all operators on all vector spaces of smaller dimension.

Let $u \in V$ be such that $u \neq 0$. The list $u, Tu, ..., T^{dim V} u$ has length $dim V + 1$ and thus is linearly dependent. By 2.19, there is a smallest positive integer $m \leq dim V$ such that $T^m u$ is a linear combination of $u, Tu, ..., T^{m-1} u$. Thus there exist scalars $c_0, c_1,...,c_{m-1}$ such that 

$$c_0 u + c_1 Tu + ... + c_{m-1} T^{m-1} u + T^m u = 0$$

Define a monic polynomial $q \in P_m(F)$ by

$$q(z) = c_0 + c_1 z + ... + c_{m-1} z^{m-1} + z^m$$

Then $q(T)u=0$.

If $k$ is a nonnegative integer, then 

$$q(T)(T^k u) = T^k (q(T)u) = T^k (0) = 0$$

2.19 shows that $u, Tu, ..., T^{m-1} u$ is linearly independent. Thus the equation above implies that $dim null q(T) \geq m$. Hence

$$dim range q(T) = dim V - dim null q(T) \leq dim V - m$$

Because $range q(T)$ is invariant under $T$ by 5.18, we can apply our induction hypothesis to the operator $T|_{range q(T)}$ on the vector space $range q(T)$. Thus there is a monic polynomial $s \in P(F)$ with 

$$deg s \leq dim V - m$$

and 

$$s(T|_{range q(T)}) = 0$$

Hence for all $v \in V$ we have 

$$(sq(T)) v = (s(T) q(T)) v = s(T) (q(T)v) = 0$$

because $q(T)v \in range q(T)$ and $s(T)|_{range q(T)} = s(T|_{range q(T)}) = 0$.

Thus $sq$ is a monic polynomial such that $deg sq \leq dim V$ and and $(sq)(T) = 0$.

The section above shows that there is a monic polynomial of degree at most $dim V$ that when applied to $T$ gives the 0 operator. 

Thus there is a monic polynomial of smallest degree with this property, completing the existence part of this result.

Let $p \in P(F)$ be a monic polynomial of smallest degree such that $p(T)=0$. To prove the uniqueness part of the result, suppose $r \in P(F)$ is a monic polynomial of the same degree as $p$ and $r(T) = 0$. Then $(p-r)(T) = 0$ and also $deg (p-r) < deg p$. If $p-r$ were not equal to 0, then we could divide $p-r$ by the coefficient of the highest-order term in $p-r$ to get a monic polynomial (of smaller degree than $p$) that when applied to $T$ gives the 0 operator. Thus $p-r=0$, as desired.


### 5.24 Definition: minimal polynomial
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then the minimal polynomial of $T$ is the unique monic polynomial $p \in P(F)$ of smallest degree such that $p(T) = 0$.


### 5.27
Suppose $V$ is finite-dimensional and $T \in L(V)$.

- The zeros of the minimal polynomial of $T$ are the eigenvalues of $T$.
- If $V$ is a complex vector space, then the minimal polynomial of $T$ has the form 

$$(z - \lambda_1) ... (z - \lambda_m) $$

where $\lambda_1, ..., \lambda_m$ is a list of all eigenvalues of $T$, possibly with repetitions.

Proof:

Let $p$ be the minimal of $T$.

First suppose $\lambda \in F$ is a zero of $p$. Then $p$ can be written in the form 

$$p(z) = (z-\lambda) q(z)$$

where $q$ is a monic polynomial with coefficients in $F$. Because $p(T)=0$, we have 

$$0 = ((T-\lambda)q(T))v = (T-\lambda) (q(T)v)$$

for all $v \in V$. Because $deg q = (deg p) - 1$ and $p$ is the minimal polynomial of $T$, there exists at least one vector $v \in V$ such that $q(T)v \neq 0$. The equation above implies that $\lambda$ is an eigenvalue of $T$, as desired.

To prove that every eigenvalue of $T$ is a zero of $p$, now suppose $\lambda \in F$ is an eigenvalue of $T$. Thus there exists $v \in V, v \neq 0$ such that $Tv = \lambda v$. Repeated applications of $T$ to both sides of this equation show that $T^k v = \lambda^k v$ for every nonnegative integer $k$. Applying $p(T)$, we have

$$p(T)v = (a_0 I + a_1 T + ... + T^m)v =(a_0 v + a_1 \lambda v + ... + \lambda^m v) = p(\lambda) v$$

Because $p$ is the minimal polynomial of $T$, we have $p(T)v=0$. Hence the equation above implies that $p(\lambda)=0$. Thus $\lambda$ is a zero of $p$, as desired.


### 5.29
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $q \in P(F)$. Then $q(T) = 0$ if and only if $q$ is a polynomial multiple of the minimal polynomial of $T$.

Proof:

Let $p$ denote the minimal polynomial of $T$.

$\Rightarrow$
First suppose $q(T)=0$. By the division algorithm for polynomials 4.9, there exist polynomials $s, r \in P(F)$ such that $q = ps + r$ and $deg r < deg p$. We have

$$0 = q(T) = p(T)s(T) + r(T) = r(T)$$

The equation above implies that $r=0$ (otherwise, dividing $r$ by its highest-degree coefficient would produce a monic polynomial that when applied to $T$ gives 0; this polynomial would have a smaller degree than the minimal polynomial, which would be a contradiction). 

Thus we have $q = ps$. Hence $q$ is a polynomial multiple of $p$, as desired.

$\Leftarrow$
Suppose $q$ is a polynomial multiple of $p$. Thus there exists a polynomial $s \in P(F)$ such that $q = ps$. We have 

$$q(T) = p(T)s(T) = 0 s(T) = 0$$

as desired.


### 5.31
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $U$ is a subspace of $V$ that is invariant under $V$. Then the minimal polynomial of $T$ is a polynomial multiple of the minimal polynomial of $T|_{U}$.

Proof:

Suppose $p$ is the minimal polynomial of $T$. Thus $p(T)v = 0$ for all $v \in V$. 

In particular, $p(T)u = 0$ for all $u \in U$.

Thus $p(T|_U) = 0$. Now 5.29, applied to the operator $T|_U$ in place of $T$, implies that $p$ is a polynomial multiple of the minimal polynomial of $T|_U$.


### 5.32
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ is not invertible if and only if the constant term of the minimal polynomial of $T$ is 0.

Proof:

Suppose $T \in L(V)$ and $p$ is the minimal polynomial of $T$. Then 

$T$ is not invertible $\iff$ 0 is an eigenvalue of $T$ 

$\iff$ 0 is a zero of $p$ $\iff$ the constant term of $p$ is 0


### 5.33
Suppose $F = R$ and $V$ is finite-dimensional. Suppose also that $T \in L(V)$ and $b, c \in R$ with $b^2 < 4c$. Then $dim null (T^2 + bT + cI)$ is an even number.

Proof:

Recall that $null (T^2 + bT + cI)$ is invariant under $T$ by 5.18. By replacing $V$ with $null (T^2 + bT + cI)$ and replacing $T$ with $T$ restricted to $null (T^2 + bT + cI)$, we can assume that $T^2 + bT + cI = 0$; we now need to prove that $dim V$ is even.

Suppose $\lambda \in R$ and $v \in V$ are such that $Tv = \lambda v$. Then 

$$0 = (T^2 + bT + cI)v = (\lambda^2 + b \lambda + c) v = ((\lambda+b/2)^2 + c - b^2/4)v$$

Since $b^2 < 4c$, the term in the parentheses above is a positive number. Thus the equation above implies that $v=0$. Hence we have show that $T$ has no eigenvectors.

Let $U$ be a subspace of $V$ that is invariant under $T$, and has the largest dimension among all subspaces of $V that are invariant under $T$ and have even dimension. 

If $U=V$, then we are done; otherwise assume there exists $w \in V$ such that $w \notin U$.

Let $W = span(w, Tw)$. Then $W$ is invariant under $T$ because $Tw \in W$, $T(Tw) = -bTw - cw$. Furthermore, $dim W = 2$, because otherwise $w$ would be an eigenvalue of $T$.

$$dim (U+W) = dim U + dim W - dim (U \cap W) = dim U + 2$$

where $U \cap W = \\{0\\}$, because otherwise $U \cap W$ would be a one-dimensional subspace of $V$ that is invariant under $T$, which is impossible because $T$ has no eigenvectors.

Because $U+W$ is invariant under $T$, the equation above shows that there exists a subspace of $V$ invariant under $T$ of even dimension larger than $dim U$. Thus the assumption that $U \neq V$ was incorrect. Hence $V$ has even dimension.


### 5.34
Every operator on an odd-dimensional vector space has an eigenvalue.

Proof:

Suppose $F=R$ and $V$ is finite-dimensional. Let $dim V = n$, and suppose $n$ is an odd number. Let $T \in L(V)$.

We will use induction on $n$ in steps of size two to show that $T$ has an eigenvalue. 

To get started, note that the desired result holds if $dim V = 1$ because then every nonzero vector in $V$ is an eigenvector of $T$.

Now suppose $n \geq 3$ and the desired result holds for all operators on all odd-dimensional vector spaces of dimension less than $n$.

Let $p$ denote the minimal polynomial of $T$. 

If $p$ is a polynomial multiple of $(x-\lambda)$ for some $\lambda \in R$, then $\lambda$ is an eigenvalue of $T$ by 5.27, and we are done

Thus we can assume that there exist $b, c \in R$ such that $b^2 < 4c$ and $p$ is a polynomial multiple of $x^2 + bx + c$ (4.16).

There exists a monic polynomial $q \in P(R)$ such that $p(x) = q(x) (x^2 + bx + c)$ for all $x \in R$. Now 

$$0 = p(T) = (q(T))(T^2 + bT + cI)$$

which means $q(T) = 0$ on $range (T^2 + bT + cI)$. Because $deg q < deg p$ and $p$ is the minimal polynomial of $T, this implies that $range (T^2 + bT + cI) \neq V$.

By 3.21, 

$$dim V = dim null (T^2 + bT + cI) + dim range (T^2 + bT + cI)$$

Because $dim V$ is odd by hypothesis, and $dim null (T^2 + bT + cI)$ is even by 5.33, the equation above shows that $dim range (T^2 + bT + cI)$ is odd.

Hence $range (T^2 + bT + cI)$ is a subspace of $V$ that is invariant under $T$ by 5.18, and has odd dimension less than $dim V$. Our induction hypothesis now implies that $T$ restricted to $range (T^2 + bT + cI)$ has an eigenvalue, which means that $T$ has an eigenvalue.




## Exercises

### (10) Suppose $V is finite-dimensional, $T \in L(V)$, and $v \in V$. Prove that $span(v, Tv, ..., T^m v) = span(v, Tv, ..., T^{dim V -1} v)$ for all integers $m \geq dim V - 1$.

Let $dim V = n$. If $m = n-1$ then the case is trivial. Consider $m = n$.

$(v, Tv, ..., T^m v)$ is a list of length $n+1$, so they are linearly dependent in $V$. By 2.19, there exists a $k \in \\{1,...,n\\}$ such that 

$$T^k v= a_0 v + a_1 Tv + ... + a_{k-1} T^{k-1}v$$. 

Applying $T$ to both sides, we have 

$$T T^k v = a_0 Tv + a_1 T^2 v + ... + a_{k-1} T^k v \in span(v, Tv, ..., T^{k-1}v)$$

Similarly, for $m=n+1, n+2$, we can find such a $k$ and applying $T$ repeatedly shows that the span does not grow.

Therefore $span(v, Tv, ..., T^m v) = span(v, Tv, ..., T^{dim V -1} v)$ for all integers $m \geq dim V - 1$. 






--------------------------------------------------------------------------------
# 5C Upper-Triangular Matrices

### 5.39
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Then the following are equivalent.

- The matrix of $T$ with respect to $v_1,...,v_n$ is upper triangular. 
- $span (v_1,...,v_k)$ is invariant under $T$ for each $k = 1,...,n$.
- $Tv_k \in span (v_1,...,v_k)$ for each $k = 1,...,n$

Proof:

First suppose (a) holds. To prove that (b) holds, suppose $k \in \\{1,..,n\\}$. 

If $j \in \\{1,...,n\\}$, then $Tv_j \in span(v_1,...,v_j)$ because the matrix of $T$ with respect to $v_1,...,v_n$ is upper triangular. 

Because $span(v_1,...,v_j) \subseteq span(v_1,...,v_k)$ if $j \leq k$, we see that $Tv_j \in span(v_1,...,v_k)$ for each $j \in \\{1,...,k\\}$. THus $span(v_1,...,v_k)$ is invariant under $T$, completing the proof that (a) implies (b).

Now suppose (b) holds, so $span(v_1,...,v_k)$ is invariant under $T$ for each $k=1,...,n$. In particular, $Tv_k \in span(v_1,...,v_k)$ for each $k=1,...,n$. Thus (b) implies (c).

Now suppose (c) holds, so $Tv_k \in span(v_1,...,v_k)$ for each $k=1,...,n$. This means that when writing each $Tv_k$ as a linear combination of the basis vectors $v_1,...,v_n$, we need to use only the vectors $v_1,...,v_k$. Hence all entries under the diagonal of $M(T)$ are 0. Thus $M(T)$ is an upper-triangular matrix, copmleting the proof (c) implies (a).

We have shown that (a) $\Rightarrow$ (b) $\Rightarrow$ (c) $\Rightarrow$ (a), which shows that (a), (b), and (c) are equivalent.


### 5.40
Suppose $T \in L(V)$ and $V$ has a basis with respect to which $T$ has an upper triangular matrix with diagonal entries $\lambda_1,...,\lambda_n$. Then

$$(T - \lambda_1 I) ... (T - \lambda_n I) = 0$$

Proof:

Let $v_1,...,v_n$ denote a basis of $V$ with respect to which $T$ has an upper-triangular matrix with diagonal entries $\lambda_1,...,\lambda_n$. Then $Tv_1 = \lambda_1 v_1$, which means that $(T - \lambda_1 I) v_1 = 0$, which implies that 

$$(T-\lambda_1 I) ... (T - \lambda_m I) v_1 = 0$$

for $m = 1,...,n$, using the commutativity of each $T - \lambda_j I$ with each $T - \lambda_k I$. 

Note that 

$$(T - \lambda_2 I) v_2 = Tv_2 - \lambda_2 v_2 = a_1 v_1 + \lambda_2 v_2 - \lambda_2 v_2 \in span(v_1)$$

Thus 

$$(T - \lambda_1 I) (T - \lambda_2 I) v_2 = 0$$

by the previous paragraph, which implies that 

$$(T - \lambda_1 I) ... (T - \lambda_m I) v_2 = 0$$

for $m=2,...,n$, using the commutativity of each $T - \lambda_j I$ with each $T - \lambda_k I$. 

Note that 

$$(T - \lambda_3 I) v_3 = T v_3 - \lambda_3 v_3 = a_1 v_1 + a_2 v_2 + \lambda_3 v_3 - \lambda_3 v_3 \in span(v_1, v_2)$$

Thus by the previous paragraph, 

$$(T-\lambda_1 I)(T-\lambda_2 I)(T-\lambda_3 I)v_3 = 0$$

which implies that 

$$(T-\lambda_1 I)... (T-\lambda_m I)v_3 = 0$$

for $m=3,...,n$, using the commutativity of each $T - \lambda_j I$ with each $T - \lambda_k I$. 

Continuing this pattern, we see that $(T-\lambda_1 I)...(T-\lambda_n I)v_k = 0$ for each $k=1,...,n$. Thus $(T-\lambda_1 I)...(T-\lambda_n I)$ is the 0 operator because it is 0 on each vector in a basis of $V$.


### 5.41
Suppose $T \in L(V)$ has an upper-triangular matrix with respect to some basis of $V$. Then the eigenvalues of $T$ are precisely the entries on the diagonal of that upper-triangular matrix.

Proof:

Suppose $v_1,...,v_n$ is a basis of $V$ with respect to which $T$ has an upper-triangular matrix. Because $Tv_1 = \lambda_1 v_1$, we see that $\lambda_1$ is an eigenvalue of $T$.

Suppose $k = \{{2,...,n\}}$. Then $(T-\lambda_k I) v_k \in span(v_1,...,v_{k-1})$. Thus $T-\lambda_k I$ maps $span(v_1,...,v_k)$ into $span(v_1,...,v_{k-1})$. 

Beacuse $dim span(v_1,...,v_k) = k$ and $dim span(v_1,...,v_{k-1}) = k-1$, this implies that $T-\lambda_k I$ restricted to $span(v_1,...,v_k)$ is not injective, by 3.22. Thus there exists $v \in span(v_1,...,v_k)$ such that $v \neq 0, (T-\lambda_k I)v=0$. Thus $\lambda_k$ is an eigenvalue of $T$. Hence we have shown that every entry on the diagonal of $M(T)$ is an eigenvalue of $T$.

To prove $T$ has no other eigenvalues, let $q$ be the polynomial defined by $q(z)=(z-\lambda_1)...(z-\lambda_n)$. Then $q(T)=0$ by 5.40. Hence $q$ is a polynomial multiple of the minimal polynomial of $T$, by 5.29. Thus every zero of the minimal polynomial of $T$ is a zero of $q$. Because the zeros of the minimal polynomial of $T$ are the eigenvalues of $T$, by 5.27, this implies that every eigenvalue of $T$ is a zero of $q$. Hence the eigenvalues of $T$ are all contained in the list $\lambda_1,...,\lambda_n$.


### 5.44
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$.

Proof:

$\Rightarrow$
First suppose $T$ has an upper-triangular matrix with respect to some basis of $V$. Let $\alpha_1,...,\alpha_n$ denote the diagonal entries of that matrix. 

Define a polynomial $q \in P(F)$ by $q(z) = (z-\alpha_1)...(z-\alpha_n)$. Then $q(T)=0$, by 5.40. Hence $q$ is a polynomial multiple of the minimal polynomial of $T$, by 5.29. Thus the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$ with $\\{\lambda_1,...,\lambda_m\\} \subseteq \\{\alpha_1,...,\alpha_n\\}$.

$\Leftarrow$
Suppose the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$. 

We will use induction on m.

To get started, if $m=1$, then $z-\lambda_1$ is the minimal polynomial of $T$, which implies that $T=\lambda_1 I$, which implies that the matrix of $T$ with respect to any basis of $V$ is upper triangular.

Now suppose $m > 1$, and the desired result holds for all smaller positive integers.

Let $U = range (T - \lambda_m I)$. Then $U$ is invariant under $T$ by 5.18. Thus $T|_U$ is an operator on $U$.

If $u \in U$, then $(T-\lambda_m I)v = u$ for some $v \in V$ and

$$(T-\lambda_1 I)...(T-\lambda_{m-1})u = (T-\lambda_1 I)...(T-\lambda_m I)v = 0$$

Hence $(z-\lambda_1)...(z-\lambda_{m-1})$ is a polynomial multiple of the minimal polynomial of $T|_U$, by 5.29. Thus the minimal polynomial of $T|_U$ is the product of at most $m-1$ terms of the form $z-\lambda_k$.

By our induction hypothesis, there is a basis $u_1,...,u_M$ of $U$ with respect to which $T|_U$ has an upper-triangular matrix.

Thus for each $k \in \\{1,...,M\\}$, we have, using 5.39,

$$Tu_k = (T|_U) u_k \in span (u_1,...,u_k)$$

Extend $u_1,...,u_M$ to a basis $u_1,...,u_M, v_1,...,v_N$ of $V$. 

If $k \in \\{1,...,N\\}$, then 

$$Tv_k = (T - \lambda_m I) v_k + \lambda_m v_k$$

The definition of $U$ shows that $(T-\lambda_m I)v_k \in U = span(u_1,...,u_M)$. Thus the equation above shows that 

$$Tv_k \in span(u_1,...,u_M,v_1,...,v_k)$$

We conclude, using 5.39, that $T$ has an upper-triangular matrix with respect to the basis $u_1,...,u_M, v_1,...,v_N$ of $V$.


### 5.47
Suppose $V$ is a finite-dimensional complex vector space and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some basis of $V$.

Proof:

The desired result follows from 5.44 and the second version of the fundamental theorem of algebra (4.13).




## Exercises

### (1) Prove or give a counterexample: If $T \in L(V)$ and $T^2$ has an upper-triangular matrix with respect to some basis of $V$, then $T$ has an upper-triangular matrix with respect to some basis of $V$.


### (2) Suppose $A$ and $B$ are upper-triangular matrices of the same size, with $\alpha_1, ..., \alpha_n$ on the diagonal of $A$ and $\beta_1, ..., \beta_n$ on the diagonal of $B$.

#### (a) Show that $A + B$ is an upper-triangular matrix with $\alpha_1 + \beta_1, ..., \alpha_n + \beta_n$ on the diagonal.

#### (b) Show that $AB$ is an upper-triangular matrix with $\alpha_1 \beta_1, ..., \alpha_n \beta_n$ on the diagonal.


### (3) 

### (4)

### (5)

### (6)

### (8)

### (9)





--------------------------------------------------------------------------------
# 5D Diagonalizable Operators

### 5.48 Definition: diagonal matrix
A diagonal matrix is a square matrix that is 0 everywhere except possibly on the diagonal.


### 5.50 Definition: diagonalizable
An operator on $V$ is called diagonalizable if the operator has a diagonal matrix with respect to some basis of $V$.


### 5.52 Definition: eigenspace
Suppose $T \in L(V)$ and $\lambda \in F$. The eigenspace of $T$ corresponding to $\lambda$ is the subspace $E(\lambda, T)$ of $V$ defined by

$$E(\lambda, T) = null (T - \lambda I) = \\{v \in V: Tv = \lambda v\\}$$

Hence $E(\lambda, T)$ is the set of all eigenvectors of $T$ corresponding to $\lambda$, along with the 0 vector.


### 5.54
Suppose $T \in L(V)$ and $\lambda_1,...,\lambda_m$ are distinct eigenvalues of $T$. Then 

$$E(\lambda_1, T) + ... + E(\lambda_m, T)$$

is a direct sum. Furthermore, if $V$ is finite-dimensional, then 

$$dim E(\lambda_1, T) + ... + dim E (\lambda_m, T) \leq dim V$$.

Proof:

To show that $E(\lambda_1, T) + ... + E(\lambda_m, T)$ is a direct sum, suppose $v_1 + ... + v_m = 0$, where each $v_k$ is in $E(\lambda_k, T)$. Because eigenvectors corresponding to distinct eigenvalues are linearly independent, by 5.11, this implies that each $v_k$ equals 0. Thus $E(\lambda_1, T) + ... + E(\lambda_m, T)$ is a direct sum by 1.45, as desired.

Now suppose $V$ is finite-dimensional. Then 

$$dim E(\lambda_1, T) + ... + dim E(\lambda_m, T) = dim (E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)) \leq dim V$$

where the first line follows from 3.94 and the second line follows from 2.37.


### 5.55
Suppose $V$ is finite-dimensional and $T \in L(V)$. Let $\lambda_1,...,\lambda_m$ denote the distinct eigenvalues of $T$. Then the following are equivalent:

(a) $T$ is diagonalizable.
(b) $V$ has a basis consisting of eigenvectors of $T$.
(c) $V = E(\lambda_1,T) \oplus ... \oplus E(\lambda_m, T)$
(d) $dim V = dim E(\lambda_1, T) + ... + dim E(\lambda_m, T)$.

Proof:

An operator $T \in L(V)$ has a diagonal matrix with respect to a basis $v_1,...,v_n$ of $V$ if and only if $Tv_k = \lambda_k v_k$ for each $k$. Thus (a) and (b) are equivalent.

Suppose (b) holds; thus $V$ has a basis consisting of eigenvectors of $T$. Hence every vector in $V$ is a linear combination of eigenvectors of $T$, which implies that $V = E(\lambda_1, T) + ... + E(\lambda_m, T)$. 5.54 shows that (c) holds, proving that (b) implies (c).

That (c) implies (d) follows immediately from 3.94.

Suppose (d) holds; thus $dim V = dim E(\lambda_1, T) + ... + E(\lambda_m, T)$. Choose a basis of each $E(\lambda_k, T)$; put all these bases together to form a list $v_1,...,v_n$ of eigenvectors of $T$, where $dim V = n$.

To show that this list is linearly independent, suppose $a_1 v_1 + ... + a_n v_n = 0$, where $a_1,...,a_n \in F$. 

For each $k = 1,...,m$, let $u_k$ denote the sum of all the terms $a_j v_j$ such that $v_j \in E(\lambda_k, T)$. Thus each $u_k$ is in $E(\lambda_k, T)$, and $u_1+...+u_m=0$. 

Because eigenvectors corresponding to distinct eigenvalues are linearly independent (5.11), this implies that each $u_k$ equals 0. 

Because each $u_k$ is a sum of terms $a_j v_j$ where the $v_j$'s were chosen to be a basis of $E(\lambda_k, T)$, this implies that all $a_j$'s equal 0. Thus $v_1,...,v_n$ is linearly independent and hence is a basis of $V$ by 2.38. 

Thus (d) implies (b), completing the proof.


### 5.58
Suppose $V$ is finite-dimensional and $T \in L(V)$ has $dim V$ distinct eigenvalues. Then $T$ is diagonalizable.

Proof:

Suppose $T$ has distinct eigenvalues $\lambda_1,...,\lambda_{dim V}$. For each $k$, let $v_k \in V$ be an eigenvector corresponding to the eigenvalue $\lambda_k$. Because eigenvectors corresponding to distinct eigenvalues are linearly independent (5.11), $v_1,...,v_{dim V}$ is linearly independent.

A linearly independent list of $dim V$ vectors in $V$ is a basis of $V$ (2.38); thus $v_1,...,v_{dim V}$ is a basis of $V$. With respect to this basis consisting of eigenvectors, $T$ has a diagonal matrix.


### 5.62
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m \in F$.

$\Rightarrow$
Suppose $T$ has diagonalizable. Thus there is a basis $v_1,...,v_n$ of $V$ consisting of eigenvectors of $T$.

Let $\lambda_1,...,\lambda_m$ be the distinct eigenvalues of $T$. Then for each $v_j$, there exists $\lambda_k$ with $(T-\lambda_k I) v_j = 0$. Thus 

$$(T-\lambda_1 I)...(T-\lambda_m I) v_j = 0$$

which implies that the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$.

$\Leftarrow$
Suppose the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m \in F$. Thus

$$(T-\lambda_1 I)...(T-\lambda_m I)=0$$

We will prove that $T$ is diagonalizable by induction on $m$.

To get started, suppose $m=1$. Then $T-\lambda_1 I = 0$, which means that $T$ is a scalar multiple of the identity operator, which implies that $T$ is diagonalizable.

Now suppose $m>1$ and the desired result holds for all smaller values of $m$.

The subspace $range (T-\lambda_m I)$ is invariant under $T$ (5.18). Thus $T$ restricted to $range (T-\lambda_m I)$ is an operator on $range (T-\lambda_m I)$.

If $u \in range(T-\lambda_m I)$, then $(T-\lambda_m I)v = u$ for some $v \in V$, and 

$$(T-\lambda_1 I)...(T-\lambda_{m-1} I)u = (T-\lambda_1 I)...(T-\lambda_m I)v = 0$$

Hence $(z-\lambda_1)...(z-\lambda_{m-1})$ is a polynomial multiple of the minimal polynomial of $T$ restricted to $range (T-\lambda_m I)$ by 5.29. 

Thus by our induction hypothesis, there is a basis of $range (T-\lambda_m I)$ consisting of eigenvectors of $T$.

Suppose $u \in range(T-\lambda_m I) \cap null (T-\lambda_m I)$. Then $Tu = \lambda_m u$. 

$$0 = (T-\lambda_1 I)...(T-\lambda_{m-1} I) u = (\lambda_m - \lambda_1)...(\lambda_m - \lambda_{m-1}) u$$

Because $\lambda_1,...,\lambda_m$ are distinct, the equation above implies that $u=0$. Hence $range (T-\lambda_m I) \cap null (T-\lambda_m I) = \\{0\\}$.

Thus $range (T-\lambda_m I) + null (T-\lambda_m I)$ is a direct sum by 1.46, whose dimension is $dim V$, by 3.94 and 3.21. Hence $range (T-\lambda_m I) \oplus null (T-\lambda_m I) = V$.

Every nonzero vector in $null (T-\lambda_m I)$ is an eigenvector of $T$ with eigenvalue $\lambda_m$.

Earlier in this proof we saw that there is a basis of $range (T-\lambda_m I)$ consisting of eigenvectors of $T$. Adjoining to that basis a basis of $null (T-\lambda_m I)$ gives a basis of $V$ consisting of eigenvectors of $T$. The matrix of $T$ with respect to this basis is a diagonal matrix, as desired.


### 5.65
Suppose $T \in L(V)$ is diagonalizable and $U$ is a subspace of $V$ that is invariant under $T$. Then $T|_U$ is a diagonalizable operator on $U$.


### 5.66 Definition: Gershgorin disks
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Let $A$ denote the matrix of $T$ with respect to this basis. A gershgorin disk of $T$ with respect to the basis $v_1,...,v_n$ is a set of the form 

$$\\{z \in F: |z-A_{j,j}| \leq \sum^n_{k=1, k \neq j} |A_jk| \\}$$

where $j \in \\{1,...,n\\}$.


### 5.67
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Then each eigenvalue of $T$ is contained in some Gershgorin disk of $T$ with respect to the basis $v_1,...,v_n$.




## Exercises

### (1) Suppose $V$ is a finite-dimensional complex vector space and $T \in L(V)$.

#### (a) Prove that if $T^4 = I$, then $T$ is diagonalizable.

Suppose $T^4 = I$. Then we have $T^4 - I = 0$. 

Thus $p(z) = z^4 - 1$ is a polynomial multiple of the minimal polynomial of $T$ by 5.29. 

We can factor 

$$p(z) = (z + i) (z - i) (z + 1) (z - 1).$$

By 5.62, $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z - \lambda_1) ... (z - \lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m$. 

Since $p(z)$ is a polynomial multiple of the minimal polynomial, the minimal polynomial satisfies the condition of 5.62. 

Hence $T$ is diagonalizable. 


#### (b) Prove that if $T^4 = T$, then $T$ is diagonalizable.

Suppose $T^4 = T$. Then we have $T^4 - T = 0$. 

Thus $p(z) = z^4 - z$ is a polynomial multiple of the minimal polynomial of $T$ by 5.29. 

We can factor 

$$p(z) = (z - 0) (z - 1) (z- ( (-1+i \sqrt{3})/2)) (z- ( (-1-i \sqrt{3})/2)) .$$ 

By 5.62, $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m$. 

Since $p(z)$ is a polynomial multiple of the minimal polynomial, the minimal polynomial satisfies the condition of 5.62. 

Hence $T$ is diagonalizable. 


#### (c) Give an example of an operator $T \in L(C^2)$ such that $T^4 = T^2$ and $T$ is not diagonalizable.

$$
\begin{pmatrix} 
0 & 1 \\ 
0 & 0 
\end{pmatrix}
$$

We verify that $T^4 = T^2 = 0$. 

0 is the only eigenvalue, and $E(0, T) = span(0,1)$. $dim E(0,T) < dim V = 2$. Hence $T$ is not diagonalizable by 5.55.



### (2) Suppose $T \in L(V)$ has a diagonal matrix $A$ with respect to some basis of $V$. Prove that if $\lambda \in F$, then $\lambda$ appears on the diagonal of $A$ precisely $dim E(\lambda, T)$ times.

Suppose $dim V = n$. Let $v_1,...,v_n$ be the basis with respect to which $T$ has a diagonal matrix. 

$Tv_i = \lambda_i v_i, i=1,...,n$, where $\lambda_i$'s are the diagonal entries of $A$.

Let $\lambda \in F$. Let $I_\lambda = \\{i: \lambda_i = \lambda \\}$ be the indices where $\lambda$ appears on the diagonal. Let $d$ be the number of times $\lambda$ appears.

We want to show that $\\{v_i: i \in I_\lambda \\}$ is a basis of $E(\lambda, T)$.

Since $Tv_i = \lambda v_i, i \in I_\lambda$, $v_i \in E(\lambda, T)$.

$v_i, i \in I_\lambda$'s are linearly independent because they are subset of the basis $v_1,...,v_n$.

Let $u \in E(\lambda, T)$. $u = a_1 v_1 + ... + a_n v_n$ for some $a_1,...,a_n$.

$(T-\lambda I) u = 0 = \sum_{i=1}^n a_i (\lambda_i - \lambda) v_i, i \notin I_\lambda$.

For $i \in I_\lambda$, $\lambda_i = \lambda$ so those terms disappear. 

For $i \notin I_\lambda$, $\lambda_i \neq \lambda$, which forces $a_i = 0$. 

So $u = \sum_{i \in I_\lambda} a_i v_i$. Therefore $v_i: i \in I_\lambda$ spans $E(\lambda, T)$.

Thus $\\{v_i: i \in I_\lambda \\}$ is a basis of $E(\lambda, T)$. 

$dim E(\lambda, T) = d$, and $\lambda$ appears on the diagonal $d$ times.



### (3) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that if the operator $T$ is diagonalizable, then $V = null T \oplus range T$.

Suppose $T \in L(V)$ is diagonalizable. We want to show that $V = null T \oplus range T$. 

First we will show that $null T + range T$ is a direct sum, and then we will show that it is equal to $V$.

Suppose $v_1, ..., v_n$ is a basis of $V$ with respect to which $T$ has a diagonal matrix. Let $\lambda_1, ..., \lambda_n$ be the corresponding eigenvalues. 

Suppose $u \in null T \cap range T$. Then $Tu = 0$ and $Tv = u$ for some $v \in V$. 

We can write $u = a_1 v_1 + ... + a_n v_n$ for some $a_1, ..., a_n \in F$, and $v = b_1 v_1 + ... + b_n v_n$ for some $b_1, ..., b_n \in F$. 

We have

$$
\begin{aligned}
Tu &= T(a_1 v_1 + ... + a_n v_n) \\
    &= a_1 Tv_1 + ... + a_n Tv_n \\
    &= a_1 \lambda_1 v_1 + ... a_n \lambda_n v_n \\
    &= 0
\end{aligned}
$$

Since $v_1, ..., v_n$ is a basis, $a_1 \lambda_1 = ... = a_n \lambda_n = 0$.

We also have

$$
\begin{aligned}
Tv &= T(b_1 v_1 + ... + b_n v_n) \\
    &= b_1 \lambda_1 v_1 + ... b_n \lambda_n v_n \\
    &= u \\
    &= a_1 v_1 + ... a_n v_n
\end{aligned}
$$

Since $v_1, ..., v_n$ is abasis, $b_i \lambda_i = a_i, i = 1, ..., n$.

Assume towards contradiction that $a_i \neq 0$ for some $i \in \\{1,...,n\\}$. 

Since $a_i \lambda_i = 0$, $\lambda_i = 0$. Then $b_i \lambda_i = 0$. But $b_i \lambda_i = a_i \neq 0$, which is a contradiction.

Therefore we conclude $a_1 = ... = a_n = 0$, so $u = 0$. 

Thus $null T \cap range T = \\{0\\}$. By 1.46, $null T + range T$ is a direct sum. 

We have

$$dim (null T \oplus range T) = dim null T + dim range T = dim V$$ 

where the first equality follows from 3.94 and the second equality follows from the fundamental theorem of linear maps (3.21).

Hence $V = null T \oplus range T$ by 2.39.



### (4) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that the following are equivalent. (a) $V = null T \oplus range T$. (b) $V = null T + range T$. (c) $null T \cap range T = \\{0\\}$.

If (a) holds, then (c) holds from 1.46.

Suppose (c) holds. We have 

$$
\begin{aligned}
dim (null T + range T) 
    &= dim null T + dim range T - dim (null T \cap range T) \\
    &= dim null T + dim range T - 0 \\
    &= dim V
\end{aligned}
$$

Therefore $null T + range T = V$ by 2.39, and (b) holds.

Suppose (b) holds. Since $V = null T + range T$, 

$$
\begin{aligned}
dim V &= dim (null T + range T) \\
    &= dim null T + dim range T - dim (null T \cap range T) \\
    &= dim V - dim (null T \cap range T)
\end{aligned}
$$

Therefore $dim (null T \cap range T) = 0$, and (c) holds. (b) and (c) together implies that (a) holds.



### (5) Suppose $V$ is a finite-dimensional complex vector space and $T \in L(V)$. Prove that $T$ is diagonalizable if and only if $V = null (T-\lambda I) \oplus range (T-\lambda I)$ for every $\lambda \in C$.

$\Rightarrow$
Suppose $T$ is diagonalizable. 

By 5.55, $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$ for some distinct eigenvalues $\lambda_1, ..., \lambda_m$.

Let $\lambda \in C$.

Case 1: $\lambda$ is not an eigenvalue. 

Then $T - \lambda I$ is invertible by 5.7. Thus $T$ is injective and surjective by 3.63. We have $range (T - \lambda I) = V$ and $null (T-\lambda I) = \\{0\\}$. 

Therefore 

$$V = null (T-\lambda I) \oplus range (T-\lambda I).$$

Case 2: $\lambda$ is an eigenvalue.

Suppose $\lambda = \lambda_i$ for some $i \in \\{1, ..., m\\}$. Then $null (T - \lambda I) = E(\lambda_i, T)$. 

Let $w \in range (T - \lambda I)$. Then $w = (T - \lambda I) v$ for some $v \in V$. 

Since $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$, we can write $v = e_1 + ... + e_m$, where $e_k \in E(\lambda_k,T), k = 1, ..., m$. 

$$
\begin{aligned}
w &= (T - \lambda I) v \\
    &= (T - \lambda I)(e_1 + ... + e_m) \\
    &= (T - \lambda I) e_1 + ... + (T - \lambda I) e_m \\
    &= (\lambda_1 e_1 - \lambda e_1) + ... + (\lambda_m e_m - \lambda e_m) \\
    &= \sum_{k=1}^m (\lambda_k - \lambda) e_k \\
    &= sum_{k \neq i} (\lambda_k - \lambda) e_k
\end{aligned}
$$

Therefore $w$ can be written as a sum of all the other eigenspaces except $E(\lambda_i, T)$, and

$$range (T-\lambda I) \subseteq E(\lambda_1, T) \oplus ... \oplus E(\lambda_{i-1}, T) \oplus E(\lambda_{i+1}, T) \oplus ... \oplus E(\lambda_m, T) .$$

Note that 

$$
\begin{aligned}
dim range (T-\lambda I) 
    &= dim V - dim null (T - \lambda I) \\
    &= dim V - dim E(\lambda, T) \\
    &= dim E(\lambda_1, T) \oplus ... \oplus E(\lambda_{i-1}, T) \oplus E(\lambda_{i+1}, T) \oplus ... \oplus E(\lambda_m, T)
\end{aligned}
$$

Hence we have

$$range (T-\lambda I) = E(\lambda_1,T) \oplus ... \oplus E(\lambda_{i-1}, T) \oplus E(\lambda_{i+1}, T) \oplus ... \oplus E(\lambda_m, T)$$

Putting everything together, we conclude

$$
\begin{aligned}
V &= E (\lambda_i, T) \oplus range (T - \lambda I) \\
    &= null (T - \lambda_i I) \oplus range (T - \lambda I) \\
    &= null (T - \lambda I) \oplus range (T - \lambda I)
\end{aligned}
$$

$\Leftarrow$
Suppose $V = null (T-\lambda I) \oplus range (T-\lambda I)$ for every $\lambda \in C$. 

We want to show that $T$ is diagonalizable. We use induction on $dim V$.

Base case: $dim V = 1$. Every vector in $V$ is an eigenvector, so $T$ is trivially diagonalizable.

Inductive step: suppose $dim V > 1$ and the desired result holds for all vector spaces of smaller dimension.

Note that $T$ has at least one eigenvalue by 5.19. Let $\lambda$ be an eigenvalue of $T$.

Let $U = range (T - \lambda I)$. Note that $U$ is invariant under $T$ by 5.18.

We want to show that for every $\mu \in C$, 

$$U = null (T|_U - \mu I) \oplus range (T|_U - \mu I).$$

By hypothesis, we have

$$V = null (T - \mu I) \oplus range (T - \mu I)$$

Note that 

$$null (T|_U - \mu I) = null (T - \mu I) \cap U$$

and

$$range (T|_U - \mu I) = (T - \mu I) (U) \subseteq range (T - \mu I).$$

We can see that 

$$null (T|_U - \mu I) \cap range (T|_U - \mu I) = \\{0\\} .$$

By the fundamental theorem of linear maps (3.21),

$$dim U = dim null (T|_U - \mu I) + dim range (T|_U - \mu I).$$

Thus 

$$U = null (T|_U - \mu I) \oplus range (T|_U - \mu I).$$

Since $dim U < dim V$ and $U$ satisfies the condition in the hypothesis, $T|_U$ is diagonalizable. 

By hypothesis we have

$$V = null (T - \lambda I) \oplus range (T - \lambda I) = E(\lambda, T) \oplus U.$$

Adding the eigenvector in $E(\lambda, T)$ to the eigenbasis in $U$ gives us a basis of $V$ which are the eigenvectors of $T$. Hence $T$ is diagonalizable.



### (6) Suppose $T \in L(F^5)$ and $dim E(8,T) = 4$. Prove that $T-2I$ or $T-6I$ is invertible.

Assume towards contradiction that both $T-2I$ and $T-6I$ are not invertible. 

Then $T-2I$ and $T-6I$ are not injective, by 3.65. $null (T-2I) \neq \\{0\\}, null (T-6I) \neq \\{0\\}$. There exists some $u, w \in V$ such that $(T-2I)u = 0$ and $(T-6I)w = 0$. Therefore $u$ is an eigenvector corresponding to eigenvalue 2, and $w$ is an eigenvector corresponding to eigenvalue 6. 

$$dim E(2,T) + dim E(6,T) + dim E(8,T) = \leq dim V = 5$$

by 5.54 and

$$dim E(2,T) + dim E(6,T) + dim E(8,T) \geq 1 + 1 + 4 = 6$$

which is a contradiction. Thus we conclude $T-2I$ or $T-6I$ is invertible.



### (8)

### (13)


### (16) Suppose that $T \in L(V)$ is diagonalizable. Let $\lambda_1, ..., \lambda_m$ denote the distinct eigenvalues of $T$. Prove that a subspace $U$ of $V$ is invariant under $T$ if and only if there exist subspaces $U_1, ..., U_m$ of $V$ such that $U_k \subseteq E(\lambda_k, T)$ for each $k$ and $U = U_1 \oplus ... \oplus U_m$.

$\Leftarrow$
Suppose there exist subspaces $U_1, ..., U_m$ of $V$ such that $U_k \subseteq E(\lambda_k, T)$ for each $k$ and $U = U_1 \oplus ... \oplus U_m$.

Suppose $u \in U$. Then $u = u_1 + ... + u_m \in U_1 \oplus ... \oplus U_m$. 

$$
\begin{aligned}
Tu &= T(u_1 + ... + u_m) \\
    &= Tu_1 + ... + Tu_m \\
    &= \lambda_1 u_1 + ... + \lambda_m u_m \\
    &\in U_1 \oplus ... \oplus U_m \\
    &= U
\end{aligned}    
$$

where the third equality follows because $u_k \in U_k \subseteq E(\lambda_k, T)$ is an eigenvector.

Hence $U$ is invariant under $T$.

$\Rightarrow$
Suppose $U$ is invariant under $T$.

Define $U_k = U \cap E(\lambda_k, T)$ for $k = 1, ..., m$. The intersection of two subspaces is a subspace.

By 5.11 eigenvectors corresponding to distinct eigenvalues are linearly independent, thus $U_1 + ... + U_m$ is a direct sum. 

By construction, $U_k \subseteq U$, thus $U_1 \oplus ... \oplus U_m \subseteq U$. 

Now we want to show that $U \subseteq U_1 \oplus ... \oplus U_m$.

Suppose $u \in U$. Since $T$ is diagonalizable, $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$ by 5.55. We can write 

$$u = u_1 + ... + u_m$$

where

$$u_k \in E(\lambda_k, T), k = 1, ..., m.$$

For each $k = 1, ..., m$, define a polynomial 

$$p_k(z) = \frac{q_k(z)}{s_k}$$

where 

$$q_k(z) = \prod_{j \neq k} (z - \lambda_j) $$

and

$$s_k = \prod_{j \neq k} (\lambda_k - \lambda_j) .$$

Since $\lambda_1, ..., \lambda_k$ are distinct eigenvalues, $s_k \neq 0$.

By 5.17, the order does not matter in taking products of polynomials of a single operator. Since $u_k \in E(\lambda_k, T)$, $(T - \lambda_k) u_k = 0$. Thus $q_k(T)$ is used to eliminate the $u_j$ terms where $j \neq k$.

$$
\begin{aligned}
q_k(T) u 
    &= q_k(T) (u_1 + ... + u_m) \\
    &= q_k(T) u_1 + ... + q_k(T) u_m \\
    &= \sum_{k=1}^m \prod_{j \neq k} (T - \lambda_j) u_k \\
    &= \prod_{j \neq k} (T - \lambda_j) u_k
    &= q_k(T) u_k
\end{aligned}
$$

Once we isolate $u_k$, we see that 

$$q_k(T) u_k = \prod_{j \neq k} (T - \lambda_j) v_k = \prod_{j \neq k} (\lambda_k - \lambda_j) u_k$$

thus the definition of $q_k(z)$ and $s_k$ make sense and

$$p_k(T) u = u_k.$$

Since $U$ is invariant, $Tu \in U$. We claim that $U$ is invariant under $p(T)$ for any polynomial $p$. Note that $U$ is invariant under powers of $T$ ($T^a$ for positive interger $a$). Since $U$ is a subspace, it is closed under addition and scalar multiplication. Thus 

$$u_k = p_k(T) u \in U.$$ 

Since $u_k \in E(\lambda_k, T)$ and $u_k \in U$, 

$$u_k \in U \cap E(\lambda_k, T) = U_k.$$

Hence we have written $u = u_1 + ... + u_m$ where $u_k \in U_k$, $k = 1, ..., m$. 

We have $U \subseteq U_1 \oplus ... \oplus U_m$, and we conclude 

$$U = U_1 \oplus ... \oplus U_m$$

where $U_k \subseteq E(\lambda_k, T)$.


### (17)

### (20)

### (22)




--------------------------------------------------------------------------------
# 5E Commuting Operators



### 5.74


### 5.75


### 5.76


### 5.78


### 5.80


### 5.81


