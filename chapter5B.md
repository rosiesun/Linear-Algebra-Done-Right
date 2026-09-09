Linear Algebra Done Right - Chapter 5 Eigenvalues and Eigenvectors <br>
5B The Minimal Polynomial
================
Rosie Sun <br>
2026-04-21


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

