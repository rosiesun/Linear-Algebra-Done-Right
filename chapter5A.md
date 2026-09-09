Linear Algebra Done Right - Chapter 5 Eigenvalues and Eigenvectors <br>
5A Invariant Subspaces
================
Rosie Sun <br>
2026-04-21


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


