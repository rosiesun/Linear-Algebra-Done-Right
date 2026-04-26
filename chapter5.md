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

### 5.12
Suppose $V$ is finite-dimensional. Then each operator on $V$ has at most $dim V$ distinct eigenvalues.

### 5.13 Notation
Suppose $T \in L(V)$ and $m$ is a positive integer.

- $T^m \in L(V)$ is defined by $T^m = T ... T$ ($m$ times).
- $T^0$ is defined to be the identity operator $I$ on $V$.
- If $T$ is invertible with inverse $T^{-1}$, then $T^{-m} \in L(V)$ is defined by

$$T^{-m} = (T^{-1})^m$$

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



## Exercises

#### (1) Suppose $T \in L(V)$ and $U$ is a subspace of $V$. 
(a) Prove that if $U \subseteq null T$, then $U$ is invariant under $T$.

Let $u \in U$. Then $u \in U \subseteq null T$. Thus $Tu=0$. Since $0$ is in any subspace, $Tu \in U$. Therefore $U$ is invariant under $T$.

(b) Prove that if $range T \subseteq U$, thten $U$ is invariant under $T$.

Let $u \in U$. Then $Tu \in range T \subseteq U$. Therefore $U$ is invariant under $T$.


#### (2) Suppose that $T \in L(V)$ and $V_1,...,V_m$ are subspaces of $V$ invariant under $T$. Prove that $V_1 + ... + V_m$ is invariant under $T$.
Let $v \in V_1 + ... + V_m$. Then we can write $v = v_1 + ... + v_m$ for some $v_1 \in V_1, ..., v_m \in V_m$. Then $Tv = T(v_1 + ... + v_m) = Tv_1 + ... + Tv_m$. By assumption, $V_1,...,V_m$ are invariant under $T$, so $Tv_1 \in V_1, ..., Tv_m \in V_m$. Thus $Tv \in V_1 + ... + V_m$, and we conclude that $V_1 + ... + V_m$ is invariant under $T$.


#### (4) Prove or give a counterexample: If $V$ is finite-dimensional and $U$ is a subspace of $V$ that is invariant under every operator on $V$, then $U=\\{0\\}$ or $U=V$.
Suppose $U \neq \\{0\\}$. Let $u \in U, u \neq 0$. We can decompose $V$ such that $V = span(u) \oplus W$. 

For any $v \in V$, define the linear operator $T$ such that 

$$Tu = v$$

$$Tw = 0, w \in W$$

By assumption, $u \in U$ implies $Tu \in U$. Since $Tu = v$, $v \in U$. But $v \in V$ was arbitrary, so we conclude $U = V$.


#### (5) Suppose $T \in L(R^2)$ is defined by $T(x,y) = (-3y, x)$. Find the eigenvalues of $T$.
There are no real eigenvalues.


#### (6) Define $T \in L(F^2)$ by $T(w,z) = (z,w)$. Find all eigenvalues and eigenvectors of $T$.
Eigenvalue 1, eigenvectors $\\{(w,z) \in R^2: w=z\\}$
Eigenvalue -1, eigenvectors $\\{(w,z) in R^2: w = -z\\}$.


#### (7) Define $T \in L(F^3)$ by $T(z_1,z_2,z_3) = (2z_2, 0, 5z_3)$. Find all eigenvalues and eigenvectors of $T$.
Eigenvalue 5, eigenvectors $span(z_3)$.
Eigenvalue 0, eigenvectors $span(z_1)$.


#### (8) Suppose $P \in L(V)$ is such that $P^2 = P$. Prove that if $\lambda$ is an eigenvalue of $P$, then $\lambda = 0$ or $\lambda = 1$.
Suppose $\lambda$ is an eigenvalue of $P$. Then $Pv = \lambda v$ for some nonzero $v \in V$. Applying $P$ to both sides, we have 

$$PPv = P lambda v = \lambda Pv = \lambda (\lambda v) = \lambda^2 v$$

Since $P^2 = P$, we also have 

$$PPv = Pv = \lambda v$$

$$\lambda^2 v = \lambda v$$

Rearranging, we have

$$\lambda (\lambda - 1) v = 0$$

Since $v \neq 0$, we must have $\lambda (\lambda - 1) = 0$. Thus $\lambda = 1$ or $\lambda = 0$.


#### (12) Suppose $V = U \oplus W$, where $U$ and $W$ are nonzero subspaces of $V$. Define $P \in L(V)$ by $P(u+w) = u$ for each $u \in U, w \in W$. Find all eigenvalues and eigenvectors of $P$.
Eigenvalue 1, eigenvectors $u \in U, u \neq 0$.
Eigenvalue 0, eigenvectors $w \in W, w \neq 0$.


#### (13) Suppose $T \in L(V)$. Suppose $S \in L(V)$ is invertible.
(a) Prove that $T$ and $S^{-1} T S$ have the same eigenvalues.

Suppose $\lambda$ is an eigenvalue of $T$ corresponding to some eigenvector $v \in V$. Then $Tv = \lambda v$. 

Since $S$ is invertible, there is some $u \in V$ such that $Su = v$. 

$$S^{-1} T Su = S^{-1} T v = S^{-1} (\lambda v) = \lambda S^{-1} v = \lambda u$$

Therefore $\lambda$ is an eigenvalue of $S^{-1} T S$.

(b) What is the relationship between the eigenvectors of $T$ and the eigenvectors of $S^{-1} T S$?

If $v$ is an eigenvector of $T$, then $S^{-1}v$ is an eigenvector of $S^{-1} T S$.


#### (14) Give an example of an operator on $R^4$ that has no (real) eigenvalues.
$$T(x_1, x_2, x_3, x_4) = (-x_2, x_1, -x_4, x_3)$$


#### (15) Suppose $V$ is finite-dimensional, $T \in L(V)$, and $\lambda \in F$. Show that $\lambda$ is an eigenvalue of $T$ if and only if $\lambda$ is an eigenvalue of the dual operator $T' \in L(V')$.


#### (21) Suppose $T \in L(V)$ is invertible.
(a) Suppose $\lambda \in F$ with $\lambda \neq 0$. Prove that $\lambda$ is an eigenvalue of $T$ if and only if $1/\lambda$ is an eigenvalue of $T^{-1}$.

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

(b) Prove that $T$ and $T^{-1}$ have the same eigenvectors.

From the equations from (a), they have the same eigenvectors.


#### (23) Suppose $V$ is finite-dimensional and $S,T \in L(V)$. Prove that $ST$ and $TS$ have the same eigenvalues.
Let $\lambda$ be an eigenvalue of $ST$ corresponding to some $v \in V, v \neq 0$. Then 

$$STv = \lambda v$$. 

Applying $T$ to both sides, we have 

$$TSTv = T \lambda v$$

$$TS(Tv) = \lambda (Tv)$$

Since $v \neq 0$, $Tv=0$ if $\lambda = 0$.

If $\lambda = 0$, then $null ST \neq \\{0\\}$. We have $TS(Tv) = 0$. Then $Tv \in null TS$. $\lambda$ is an eigenvalue of $TS$.

If $\lambda \neq 0$, then $TS(Tv) = \lambda (Tv)$ implies that $Tv$ is an eigenvector of $TS$ with eigenvalue of $\lambda$.

The other direction follows by switching the order of $S$ and $T$.


#### (25) Suppose $T \in L(V)$ and $u, w$ are eigenvectors of $T$ such that $u+w$ is also an eigenvector of $T$. Prove that $u$ and $w$ are eigenvectors of $T$ corresponding to the same eigenvalue.
Since $u, w$ are eigenvectors of $T$, there is some $\lambda_1, \lambda_2 \in F$ such that $Tu = \lambda_1 u$ and $Tw = \lambda_2 w$.

Since $u+w$ is an eigenvector of $T$, some is some $\lambda_3 \in F$ such that $T(u+w) = \lambda_3 (u+w)$.

Assume towards contradiction that $\lambda_1 \neq \lambda_2$. We have 

$$T(u+w) = \lambda_3 u + \lambda_3 w$$

$$T(u+w) = Tu + Tw = \lambda_1 u + \lambda_2 w$$

$$(\lambda_1 - \lambda_3) u + (\lambmda_2 - \lambda_3) w = 0$$

By 5.11, every list of eigenvectors of $T$ corresponding to distinct eigenvalues of $T$ is linearly independent. By 2.15, $\lambda_1 - \lambda_3 = 0$ and $\lambda_2 - \lambda_3 = 0$. Thus $\lambda_1 = \lambda_3 = \lambda_2$. But this is a contradiction. 

Therefore we conclude that $\lambda_1 = \lambda_2$.


#### (26) Suppose $T \in L(V)$ is such that every nonzero vector in $V$ is an eigenvector of $T$. Prove that $T$ is a scalar multiple of the identity operator.
Let $u, w \in V, u, w \neq 0$. Then $u, w$ are eigenvectors of $T$. 

$Tu = \lambda_1 u$ and $Tw = \lambda_2 w$.

If $u+w \neq 0$, $u+w$ is an eigenvector of $T$. From exercise (25), $u, w, u+w$ have the same eigenvalue $\lambda$. 

If $u+w = 0$, $w = -u$. We have $Tw = -Tu = -\lambda_1 u$. We also have $Tw = \lambda_2 w = -\lambda_2 u$. $-\lambda_1 u = -\lambda_2 u$, since $u \neq 0$, $\lambda_1 = \lambda_2$.

Therefore every vector in $V$ has the same eigenvalue. We conclude that $T = \lambda I$.


#### (27) Suppose that $V$ is finite-dimensional and $k \in \\{1,...,dimV - 1\\}$. Suppose $T \in L(V)$ is such that every subspace of $V$ of dimension $k$ is invariant under $T$. Prove that $T$ is a scalar multiple of the identity operator.

Suppose $dim V = n$.

If $k=1$, then every 1-dimensional subspace $U$ is invariant under $T$. For any $u \in U$, $Tu \in U$. Then $Tu = \lambda u$ for some $\lambda \in F$. Then $u$ is an eigenvector of $T$. Since every 1-dimensional subspace $U$ is invariant, every nonzero vector is an eigenvector. We can apply exercise (26) and conclude that $T$ is a scalar multiple of the identity operator.

If $k \neq 1$, assume towards contradiction that there exists $v \in V$ such that $span(v)$ is not invariant under $T$. Then $Tv \notin span(v)$, so $v, Tv$ are linearly independent. Construct two k-dimensional subspaces 

$$U_1 = span(v, Tv, u_3,...,u_k)$$

$$U_2 = span(v, u_2, u_3, ..., u_k)$$

such that $Tv \notin U_2$. This is possible because $k < n$.

By hypothesis, $U_1$ and $U_2$ are invariant under $T$. Since $v \in U_2$, $Tv \in U_2$. But this is a contradiction. Therefore we conclude that every 1-dimensional subspace is invariant under $T$. We can apply exercise (26) and conclude $T$ is a scalar multiple of the identity operator.


#### (28) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that $T$ has at most $1 + dim range T$ distinct eigenvalues.
By 5.12, $T$ has at most $dim V$ distinct eigenvalues. 

If $dim null T = 0$, then $dim V = dim range T$, so $T$ has at most $dim range T$ eigenvalues.

If $dim null T \neq 0$, then 0 is an eigenvalue of $T$. $range T$ is invariant under $T$ by 5.4. Applying 5.12 to the restriction $T:range T \rightarrow range T$, $T|_{range T}$ has at most $dim range T$ distinct eigenvaluges. Therefore $T$ has at most $1 + dim range T$ eigenvalues.


#### (31) Give an example of $T \in L(R^2)$ such that $T^4 = -I$.


#### (32) Suppose $T \in L(V)$ has no eigenvalues and $T^4 = I$. Prove that $T^2 = -I$.


#### (33) Suppose $T \in L(V)$ and $m$ is a positive integer.

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


#### (34) Suppose $V$ is finite-dimensional and $v_1,...,v_m \in V$. Prove that the list $v_1,...,v_m$ is linearly independent if and only if there exists $T \in L(V)$ such that $v_1,...,v_m$ are eigenvectors of $T$ corresponding to distinct eigenvalues.
$\Leftarrow$
Suppose there exists $T \in L(V)$ such that $v_1,...,v_m$ are eigenvectors of $T$ corresponding to distinct eigenvalues. Then by 5.11, $v_1,...,v_m$ are linearly independent. 

$\Rightarrow$
Suppose $v_1,...,v_m$ is linearly independent. Extend to a basis $v_1,...,v_m, w_1,...,w_n$ of $V$. Define $T \in L(V)$ such that $Tv_i = \lambda_i v_i, i=1,...,m$, $\lambda_i$ all distinct. $Tw_j = 0, j = 1,...,n$. 





# 5B The Minimal Polynomial

### 5.19
Every operator on a finite-dimensional nonzero complex vector space has an eigenvalue.


### 5.21 Definition: monic polynomial
A monic polynomial is a polynomial whose highest-degree coefficient equals 1.


### 5.22
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then there is a unique monic polynomial $p \in P(F)$ of smallest degree such that $p(T) = 0$. Furthermore, $deg p \leq deg V$.


### 5.24 Definition: minimal polynomial
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then the minimal polynomial of $T$ is the unique monic polynomial $p \in P(F)$ of smallest degree such that $p(T) = 0$.


### 5.27
Suppose $V$ is finite-dimensional and $T \in L(V)$.

- The zeros of the minimal polynomial of $T$ are the eigenvalues of $T$.
- If $V$ is a complex vector space, then the minimal polynomial of $T$ has the form 

$$(z - \lambda_1) ... (z - \lambda_m) $$

where $\lambda_1, ..., \lambda_m$ is a list of all eigenvalues of $T$, possibly with repetitions.


### 5.29
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $q \in P(F)$. Then $q(T) = 0$ if and only if $q$ is a polynomial multiple of the minimal polynomial of $T$.


### 5.31
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $U$ is a subspace of $V$ that is invariant under $V$. Then the minimal polynomial of $T$ is a polynomial multiple of the minimal polynomial of $T|_{U}$.


### 5.32
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ is not invertible if and only if the constant term of the minimal polynomial of $T$ is 0.


### 5.33
Suppose $F = R$ and $V$ is finite-dimensional. Suppose also that $T \in L(V)$ and $b, c \in R$ with $b^2 < 4c$. Then $dim null (T^2 + bT + cI)$ is an even number.


### 5.34
Every operator on an odd-dimensional vector space has an eigenvalue.


## Exercises





# 5C Upper-Triangular Matrices

### 5.39
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Then the following are equivalent.

- The matrix of $T$ with respect to $v_1,...,v_n$ is upper triangular. 
- $span (v_1,...,v_k)$ is invariant under $T$ for each $k = 1,...,n$.
- $Tv_k \in span (v_1,...,v_k)$ for each $k = 1,...,n$

### 5.40
Suppose $T \in L(V)$ and $V$ has a basis with respect to which $T$ has an upper triangular matrix with diagonal entries $\lambda_1,...,\lambda_n$. Then

$$(T - \lambda_1 I) ... (T - \lambda_n I) = 0$$

### 5.41
Suppose $T \in L(V)$ has an upper-triangular matrix with respect to some basis of $V$. Then the eigenvalues of $T$ are precisely the entries on the diagonal of that upper-triangular matrix.

### 5.44
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$.

### 5.47
Suppose $V$ is a finite-dimensional complex vector space and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some basis of $V$.



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

### 5.55
Suppose $V$ is finite-dimensional and $T \in L(V)$. Let $\lambda_1,...,\lambda_m$ denote the distinct eigenvalues of $T$. Then the following are equivalent:

- $T$ is diagonalizable.
- $V$ has a basis consisting of eigenvectors of $T$.
- $V = E(\lambda_1,T) \oplus ... \oplus E(\lambda_m, T)$
- $dim V = dim E(\lambda_1, T) + ... + dim E(\lambda_m, T)$.

### 5.58
Suppose $V$ is finite-dimensional and $T \in L(V)$ has $dim V$ distinct eigenvalues. Then $T$ is diagonalizable.

### 5.62
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m \in F$.

### 5.65
Suppose $T \in L(V)$ is diagonalizable and $U$ is a subspace of $V$ that is invariant under $T$. Then $T|_U$ is a diagonalizable operator on $U$.

### 5.66 Definition: Gershgorin disks
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Let $A$ denote the matrix of $T$ with respect to this basis. A gershgorin disk of $T$ with respect to the basis $v_1,...,v_n$ is a set of the form 

$$\\{z \in F: |z-A_{j,j}| \leq \sum^n_{k=1, k \neq j} |A_jk| \\}$$

where $j \in \\{1,...,n\\}$.

### 5.67
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Then each eigenvalue of $T$ is contained in some Gershgorin disk of $T$ with respect to the basis $v_1,...,v_n$.


# 5E Commuting Operators



