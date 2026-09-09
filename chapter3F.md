Linear Algebra Done Right - Chapter 3 Linear Maps <br>
3F Duality
================
Rosie Sun <br>
2026-04-02


### 3.108 Definition: linear functional
A linear functional on $V$ is a linear map from $V$ to $F$. In other words, a linear functional is an element of $L(V, F)$.


### 3.110 Definition: dual space
The dual space of $V$, denoted by $V'$, is the vector space of all linear functionals on $V$. In other words, $V' = L(V, F)$.


### 3.111 
Suppose $V$ is finite-dimensional. Then $V'$ is also finite-dimensional and $dim V' = dim V$.

Proof:

By 3.72 we have 

$$dim V' = dim L(V,F) = (dim V) (dim F) = dim V$$


### 3.112 Definition: dual basis
If $v_1,...,v_n$ is a basis of $V$, then the dual basis of $v_1,...,v_n$ is the list $\phi_1,...,\phi_n$ of elements of $V'$, where each $\phi_j$ is the linear functional on $V$ such that $\phi_j(v_k) = 1$ if $k=j$, $\phi_j(v_k) = 0$ if $k \neq j$.


### 3.114
Suppose $v_1,...,v_n$ is a basis of $V$ and $\phi_1,...,\phi_n$ is the dual basis. Then

$$v = \phi_1(v) v_1 + ... + \phi_n(v) v_n$$

for each $v \in V$.

Proof:

Suppose $v \in V$. Then there exist $c_1,...,c_n \in F$ such that

$$v = c_1 v_1 + ... + c_n v_n$$

If $j \in \\{1,...,n\\}$, then applying $\phi_j$ to both sides of the equation above gives 

$$\phi_j(v) = c_j$$

Substituting the values for $c_1,...,c_n$ given by the equation shows that $v = \phi_1(v) v_1 + ... + \phi_n(v) v_n$.


### 3.116
Suppose $V$ is finite-dimensional. Then the dual basis of a basis of $V$ is a basis of $V'$.

Proof:

Suppose $v_1,...,v_n$ is a basis of $V$. Let $\phi_1,...,\phi_n$ denote the dual basis. 

To show that $\phi_1,...,\phi_n$ is a linearly independent list of elements of $V'$, suppose $a_1,...,a_n \in F$ are such that 

$$a_1 \phi_1 + ... a_n \phi_n = 0$$

$$(a_1 \phi_1 + ... + a_n \phi_n) (v_k) = a_k$$

for each $k=1,...,n$. Thus $a_1=...=a_n=0$. Hence $\phi_1,...,\phi_n$ is linearly independent. 

Because $\phi_1,...,\phi_n$ is a linearly independent list in $V'$ whose length equals $dim V'$ by 3.111, we can conclude that $\phi_1,...,\phi_n$ is a basis of $V'$ by 2.38.


### 3.118 Definition: dual map
Suppose $T \in L(V,W)$. The dual map of $T$ is the linear map $T' \in L(W', V')$ defined for each $\phi \in W'$ by

$$T'(\phi) = \phi \circ T$$


### 3.120
Suppose $T \in L(V,W)$. Then

(a) $(S+T)' = S' + T'$ for all $S \in L(V,W)$

(b) $(\lambda T)' = \lambda T'$ for all $\lambda \in F$

(c) $(ST)' = T'S'$ for all $S \in L(W,U)$

Proof (c):

Suppose $\phi \in U'$. Then 

$$(ST)'(\phi) = \phi \circ (ST) = (\phi \circ S) \circ T = T' (\phi \circ S) = T'(S'(\phi)) = (T' S') (\phi)$$

The equation above shows that $(ST)'(\phi) = (T' S')(\phi)$ for all $\phi \in U'$. Thus $(ST)' = T'S'$.


### 3.121 Definition: annihilator
For $U \subseteq V$, the annihilator of $U$, denoted by $U^0$, is defined by

$$U^0 = \\{\phi \in V': \phi(u) = 0 for all u \in U\\}$$


### 3.124
Suppose $U \subseteq V$. Then $U^0$ is a subspace of $V'$.

Proof:

Note that $0 \in U^0$ (here 0 is the zero linear functional on $V$) because the zero linearl functional applied to every vector in $U$ equals $0 \in F$.

Suppose $\phi, \psi \in U^0$. Thus $\phi, \psi \in V'$ and $\phi(u) = \psi(u) = 0$ for every $u \in U$. If $u \in U$, then 

$$(\phi + \psi)(u) = \phi(u) + \psi(u) = 0 + 0 = 0$$

Thus $\phi + \psi \in U^0$.

Similarly, $U^0$ is closed under scalar multiplication. Thus 1.34 implies that $U^0$ is a subspace of $V'$.


### 3.125
Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$. Then 

$$dim U^0 = dim V - dim U$$

Proof:

Let $i \in L(U,V)$ be the inclusion map defined by $i(u) = u$ for each $u \in U$. Thus $i'$ is a linear map from $V'$ to $U'$. The fundamental theorem of linear maps applied to $i'$ shows that 

$$dim V' = dim null i' + dim range i'$$

Since 

$$null i' = \\{\phi \in V': i'(\phi) = \phi \circ i = 0\\}$$ 

and 

$$U^0 = \\{\phi \in V': \phi(u) = 0 \forall u \in U\\}$$

$null i' = U^0$. And we have $dim V' = dim V$. 

So we can rewrite the dimension equation above as

$$dim V = dim U^0 + dim range i'$$

If $\phi \in U'$, then $\phi$ can be extended to a linear functional $\psi$ on $V$. The definition of $i'$ shows that $i'(\psi) = \phi$. Thus $\phi \in range i'$, which implies that $range i' = U'$. Hence 

$$dim range i' = dim U' = dim U$$

and we have

$$dim V = dim U^0 + dim U$$

as desired.


### 3.127
Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$. Then

(a) $U^0 = \\{0\\} \iff U = V$

(b) $U^0 = V' \iff U = \\{0\\}$

Proof:

(a) We have

$$U^0 = \\{0\\} \iff dim U^0 = 0 \iff dim U = dim V \iff U = V$$

where the second equivalence follows from 3.125 and the third equivalence follows from 2.39.

(b) Similarly, we have

$$U^0 = V' \iff dim U^0 = dim V' \iff dim U^0 = dim V \iff dim U = 0 \iff U = \\{0\\}$$

where one direction of the first equivalence follows from 2.39, the second equivalence follows from 3.111, and the third equivalence follows from 3.125.


### 3.128
Suppose $V$ and $W$ are finite-dimensional and $T \in L(V,W)$. THen

(a) $null T' = (range T)^0$

(b) $dim null T' = dim null T + dim W - dim V$

Proof:

(a) $\subseteq$
Suppose $\phi \in null T'$. Thus $T'(\phi) = \phi \circ T = 0$. Hence

$$0 = (\phi \circ T) v = \phi(Tv)$$ 

for every $v \in V$. Thus $\phi \in (range T)^0$. This implies that $null T' \subseteq (range T)^0$.

$\supseteq$
Suppose $\phi \in (range T)^0$. Thus $\phi(Tv) = 0$ for every $v \in V$. Hence $0 = \phi \circ T = T'(\phi)$. In other words, $\phi \in null T'$, which shows that $(range T)^0 \subseteq null T'$, completing the proof.

(b) We have

$$dim null T' = dim (range T)^0 = dim W - dim range T = dim W - (dim V - dim null T) = dim null T + dim W - dim V$$

where the first equality comes from (a), the second equality comes from 3.125, and the third equality comes from the fundamental theorem of linear maps.


### 3.129
Suppose $V$ and $W$ are finite-dimensional and $T \in L(V, W)$. Then $T$ is surjective $\iff$ $T'$ is injective.

Proof:

$T$ is surjective $\iff$ $range T = W \iff (range T)^0 = \\{0\\} \iff null T' = \\{0\\} \iff$ $T'$ is injective

where the second equivalence comes from 3.127(a) and the third equivalence comes from 3.128(a).


### 3.130
Suppose $V$ and $W$ are finite-dimensional and $T \in L(V, W)$. Then

(a) $dim range T' = dim range T$

(b) $range T' = (null T)^0$

Proof:

(a) We have

$$dim range T' = dim W' - dim null T' = dim W - dim (range T)^0 = dim range T$$

where the first equality comes from 3.21, the second equality comes from 3.111 and 3.128(a), and the third equality comes from 3.125.

(b) Suppose $\phi \in range T'$. Thus there exists $\psi \in W'$ such that $\phi = T'(\psi)$. If $v \in null T$, then 

$$\phi(v) = (T'(\psi)) v = (\psi \circ T) v = \psi (Tv) = \psi (0) = 0$$

Hence $\phi \in (null T)^0$. This implies that $range T' \subseteq (null T)^0$.

We will complete the proof by showing that $range T'$ and $(null T)^0$ have the same dimension. 

$$dim range T' = dim range T = dim V - dim null T = dim (null T)^0$$

where the first equality comes from (a), the second equality comes from 3.21, and the third equality comes from 3.125.


### 3.131
Suppose $V$ and $W$ are finite-dimensional and $T \in L(V, W)$. Then 

$T$ is injective $\iff$ $T'$ is surjective.

Proof:

We have

$$T injective \iff null T = \\{0\\} \iff (null T)^0 = V' \iff range T' = V'$$

where the second equivalence follows from 3.127(b) and the third equivalence follows from 3.130(b).


### 3.132
Suppose $V$ and $W$ are finite-dimensional and $T \in L(V,W)$. Then 

$$M(T') = (M(T))^t$$

Proof:

Let $A = M(T)$ and $C = M(T')$. Suppose $1 \leq j \leq m$ and $1 \leq k \leq n$. 

From the definition of $M(T')$ we have  

$$T'(\psi_j) = \sum_{r=1}^n C_{r, j} \phi_r$$

The left side of the equation above equals $\psi_j \circ T$. Thus applying both sides of the equation above to $v_k$ gives

$$(\psi_j \circ T) (v_k) = \sum_{r=1}^n C_{r, j} \phi_r (v_k) = C_{k, j}$$

We also have

$$(\psi_j \circ T) (v_k) = \psi_j (Tv_k) = \psi_j (\sum_{r=1}^m A_{r, k} w_r) = \sum_{r=1}^m A_{r, k} \psi_j (w_r) = A_{j, k}$$

Comparing the last line of the two sets of equations, we have $C_{k, j} = A_{j, k}$. Thus $C = A^t$. In other words, $M(T') = (M(T))^t$, as desired.


### 3.133
Suppose $A \in F^{m, n}$. Then the column rank of $A$ equals the row rank of $A$.

Proof:

Define $T: F^{n, 1} \rightarrow F^{m,1}$ by $Tx = Ax$. Thus $M(T) = A$, where $M(T)$ is computed with respect to the standard bases of $F^{n,1}$ and $F^{m,1}$. Now

column rank of $A$ = column rank of $M(T)$ = dim range $T$ 

= dim range $T'$ = column rank of $M(T')$ = column rank of $A^t$ = row rank of $A$

where the second equality comes from 3.78, the third equality comes from 3.130(a), the fourth equality comes from 3.78, the fifth equality comes from 3.132, and the last equality follows from the definitions of row and column rank.




## Exercises

### (1) Explain why each linear functional is surjective or is the zero map.

Suppose $\phi \in L(V, F)$. If $\phi = 0$ then we are done. 

Suppose $\phi \neq 0$. Then there exists $v \in V$ such that $\phi(v) \neq 0$. Suppose $\phi(v) = \lambda$. 

Since $\lambda \neq 0$, for any $x \in F$, we can write 

$$x = \frac{x}{\lambda} \lambda = a \lambda$$ 

setting $a = \frac{x}{\lambda}$. Then 

$$x = a \lambda = a \phi(v) = \phi(av).$$ 

Thus $\phi$ is surjective.



### (2) Give three distinct examples of linear functionals on $R^{[0,1]}$.


### (3) Suppose $V$ is finite-dimensional and $v \in V$ with $v \neq 0$. Prove that there exists $\phi \in V'$ such that $\phi(v) = 1$.

Since $v \neq 0$, we can extend it to a basis $v, v_2,..., v_n$ of $V$. 

Define $\phi(v) = 1, \phi(v_i) = 0$ for $i = 2,...,n$. The linear functional $\phi$ is well-defined by 3.4.



### (4) Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$ such that $U \neq V$. Prove that there exists $\phi \in V'$ such that $\phi(u) = 0$ for every $u \in U$ but $\phi \neq 0$.

Let $u_1,...,u_m$ be a basis of $U$. Since $U \neq V$, $dim U < dim V$. We can extend to a basis $u_1,...,u_m, v_1,...,v_n$ of $V$.

Define $\phi(u_i) = 0$ for $i = 1,...,m$ and $\phi(v_j) = 1$ for $j = 1,...,n$. The linear functional $\phi$ is well-defined by 3.4. Thus $\phi(u) = 0$ for every $u \in U$ but $\phi \neq 0$.



### (5) Suppose $T \in L(V, W)$ and $w_1,...,w_m$ is a basis of $range T$. Hence for each $v \in V$, there exist unique numbers $\phi_1(v),...,\phi_m(v)$ such that $Tv = \phi_1(v) w_1 + ... + \phi_m(v) w_m$, thus defining functions $\phi_1,...,\phi_m$ from $V$ to $F$. Show that each of the functions $\phi_1,...,\phi_m$ is a linear functional on $V$.

Suppose $u, v \in V$. We have 

$$T(v + u) = \phi_1(v+u) w_1 + ... + \phi_m(v+u) w_m$$

$$Tv + Tu = \phi_1(v) w_1 + ... + \phi_m(v) w_m + \phi_1(u) w_1 + ... + \phi_m(u) w_m = (\phi_1(v) + \phi_1(u)) w_1 + ... + (\phi_m(v) + \phi_m(u)) w_m$$

Since $T(v+u) = Tv + Tu$, and $w_1,...,w_m$ is a basis, we have $\phi_i(v+u) = \phi_i(v) + \phi_i(u)$ for $i=1,...,m$. Thus $\phi_i$ satisfies additivity. 

Similary, suppose $\lambda \in F, v \in V$. We have

$$T(\lambda v) = \phi_1 (\lambda v) w_1 + ... + \phi_m (\lambda v) w_m$$

$$\lambda Tv = \lambda (\phi_1(v) w_1 + ... + \phi_m(v) w_m) = \lambda \phi_1(v) w_1 + ... + \lambda \phi_m(v) w_m$$

Since $T(\lambda v) = \lambda Tv$ and $w_1,...,w_m$ is a basis, we have $\phi_i(\lambda v) = \lambda \phi_i(v)$ for $i=1,...,m$. Thus $\phi_i$ satisfies homogeneity.

Thus each $\phi_1,..., \phi_m$ is a linear functional on $V$.



### (11) Suppose $v_1,...,v_n$ is a basis of $V$ and $\phi_1,...,\phi_n$ is the corresponding dual basis of $V'$. Suppose $\psi \in V'$. Prove that $\psi = \psi(v_1) \phi_1 + ... + \psi(v_n) \phi_n$.

We can write $v = \phi_1(v) v_1 + ... + \phi_n(v) v_n$ by 3.116. Applying $\psi$ to both sides, we have

$$\psi(v) = \psi(v_1) \phi_1(v) + ... \psi(v_n) \phi_n(v) = (\psi(v_1) \phi_1 + ... + \psi(v_n) \phi_n) (v)$$

for all $v \in V$. Thus $\psi = \psi(v_1) \phi_1 + ... + \psi(v_n) \phi_n$.



### (12) Suppose $S, T \in L(V,W)$. 

#### (a) Prove that $(S+T)' = S' + T'$.

Suppose $\phi \in W', v \in V$. 

$$(S+T)'(\phi)(v) = (\phi \circ (S+T))(v) = \phi ((S+T)v) = \phi(Sv + Tv) = \phi(Sv) + \phi(Tv) = (\phi \circ S)(v) + (\phi \circ T)(v) = S'(\phi)(v) + T'(\phi)(v)$$

for all $\phi \in W', v \in V$. Thus $(S+T)' = S' + T'$.

#### (b) Prove that $(\lambda T)' = \lambda T'$ for all $\lambda \in F$.

Suppose $\phi \in W', v \in V, \lambda \in F$.

$$(\lambda T)'(\phi)(v) = (\phi \circ (\lambda T))(v) = \phi( (\lambda T) v) = \lambda \phi(Tv) = \lambda (\phi \circ T)(v) = \lambda T'(\phi)(v)$$

for all $\phi \in W', v \in V$. Thus $(\lambda T)' = \lambda T'$.



### (13) Show that the dual map of the identity operator on $V$ is the identity operator on $V'$.

Suppose $\phi \in V', v \in V$. We have $I': V' \rightarrow V'$ such that 

$$I'(\phi)(v) = (\phi \circ I)(v) = \phi(Iv) = \phi(v)$$

for all $v \in V$. 

Thus $I'(\phi) = \phi$ for all $\phi \in V'$ and $I'$ is the identity operator on $V'$. 



### (14) Define $T: R^3 \rightarrow R^2$ by $T(x,y,z) = (4x + 5y + 6z, 7x + 8y + 9z)$. Suppose $\phi_1,\phi_2$ denotes the dual basis of the standard basis of $R^2$ and $\psi_1,\psi_2,\psi_3$ denotes the dual basis of the standard basis of $R^3$.

#### (a) Describe the linear functionals $T'(\phi_1)$ and $T'(\phi_2)$.

#### (b) Write $T'(\phi_1)$ and $T'(\phi_2)$ as linear combinations of $\psi_1,\psi_2,\psi_3$.


### (15) Define $T: P(R) \rightarrow P(R)$ by $(Tp)(x) = x^2 p(x) + p''(x)$ for each $x \in R$. 

#### (a) Suppose $\phi \in P(R)'$ is defined by $\phi(p) = p'(4)$. Describe the linear functional $T'(\phi)$ on $P(R)$.

#### (b) Suppose $\phi \in P(R)'$ is defined by $\phi(p) = \int^1_0 p$. Evaluate $(T'(\phi)) (x^3)$.


### (16) Suppose $W$ is finite-dimensional and $T \in L(V, W)$. Prove that $T' = 0 \iff T = 0$.

Suppose $\phi \in W'$.

$\Rightarrow$
Suppose $T' = 0$. Then $T'(\phi) = 0$ for all $\phi \in W'$. We have 

$$0 = T'(\phi)(v) = (\phi \circ T)(v) = \phi(Tv)$$

for all $\phi \in W'$. Hence $Tv = 0$. Since the equation holds for all $v \in V$, $T = 0$. 

$\Leftarrow$
Suppose $T = 0$. Then $Tv = 0$ for all $v \in V$. We have

$$0 = \phi(Tv) = (\phi \circ T) (v) = T'(\phi)(v)$$

for all $v \in V$. Thus $T'(\phi) = 0$. Since the equation holds for all $\phi \in W'$, $T' = 0$.


### (17) Suppose $V$ and $W$ are finite-dimensional and $T \in L(V, W)$. Prove that $T$ is invertible if and only if $T' \in L(W', V')$ is invertible.

Suppose $T$ is invertible. Then $T$ is injective and surjective by 3.63. By 3.129 and 3.131, $T'$ is injective and surjective. Hence $T'$ is invertible by 3.63. 

The other direction can be shown by applying the same reasoning with $T'$ in place of $T$.



### (18) Suppose $V$ and $W$ are finite-dimensional. Prove that the map that takes $T \in L(V, W)$ to $T' \in L(W', V')$ is an isomorphism of $L(V, W)$ onto $L(W', V')$.

Define $F: T \rightarrow T'$. First $F$ is linear by 3.120.

Exercise 16 showed that $T' = 0 \iff T = 0$, hence $F$ is injective. We have $dim L(V, W) = dim L(W', V')$ because $dim L(V, W) = (dim V)(dim W)$ and $dim L(W', V') = (dim W') (dim V') = (dim W) (dim V)$ by 3.111 and 3.72. Thus $F$ is surjective and invertible by 3.65. We conclude that $F$ is an isomorphism.



### (22) Suppose $V$ is finite-dimensional and $U$ and $W$ are subspaces of $V$.

#### (a) Show that $(U+W)^0 = U^0 \cap W^0$.

Suppose $\phi \in (U+W)^0$. Let $u+w \in U+W$. Then $\phi(u+w) = 0$. We have $u = u+0$ where $u \in U, 0 \in W$, and $\phi(u) = \phi(u+0) = 0$. Similarly, We have $w = w + 0$ where $w \in W, 0 \in U$, and $\phi(w) = \phi(w + 0) = 0$. Since $\phi \in U^0$ and $\phi \in W^0$, $\phi \in U^0 \cap W^0$.

Suppose $\phi \in U^0 \cap W^0$. Then $\phi(u) = 0$ for all $u \in U$ and $\phi(w) = 0$ for all $w \in W$. We have $0 = \phi(u) + \phi(w) = \phi(u+w)$ for all $u+w \in U+W$. Hence $\phi \in (U+W)^0$.

#### (b) Show that $(U \cap W)^0 = U^0 + W^0$.



### (24) Suppose $V$ is finite-dimensional and $v_1,...,v_m \in V$. Define a linear map $\Gamma: V' \rightarrow F^m$ by $\Gamma(\phi) = (\phi(v_1),...,\phi(v_m))$.

#### (a) Prove that $v_1,...,v_m$ spans $V$ if and only if $\Gamma$ is injective.

$\Rightarrow$
Suppose $v_1,...,v_m$ spans $V$. We want to show that $\Gamma$ is injective. 

Suppose $\Gamma(\phi) = (\phi(v_1),...,\phi(v_m)) = 0$. Then $\phi(v_1) = ... = \phi(v_m) = 0$, $v_1, ..., v_m \in null \phi$. 

Since $null \phi$ is a subspace and $v_1,....,v_m \in null \phi$, $span(v_1,...,v_m) \subseteq null \phi$. Since $V = span(v_1,...,v_m)$, $V = null \phi$. Thus $\phi (v) = 0$ for all $v \in V$. Hence $\phi = 0$. 

By 3.15, we conclude that $\Gamma$ is injective.

$\Leftarrow$
Suppose $\Gamma$ is injective. We want to show that $v_1,...,v_m$ spans $V$.

Since $\Gamma$ is injective, $null \Gamma = \\{0\\}$. Let $W = span(v_1,...,v_m)$. 

Assume towards contradiction that $v_1,...,v_m$ do not span $V$. Then there exists a subspace $U \subset V$, $U \neq \\{0\\}$ such that $V = W \oplus U$ by 2.33. Let $u_1,...,u_n$ be a basis of $U$. Define a linear functional on $W$ by $\phi(v_j) = 0$ for $j = 1,...,m$. We can extend it to a linear functional on $V$ (from 3A Exercise 13). Define $\psi(w) = 0, w \in W$, and $\psi(u_k) = 1$ for $k = 1,...,n$. Then $\psi(v_1)=...=\psi(v_m)=0$, so $\Gamma(\psi) = 0$, but $\psi \neq 0$ because $\psi(u_k) = 1$ for $k=1,...,n$. This contradicts the injectivity of $\Gamma$. 

We conclude that $v_1,...,v_m$ spans $V$.


#### (b) Prove that $v_1,...,v_m$ is linearly independent if and only if $\Gamma$ is surjective.

$\Rightarrow$
Suppose $v_1,...,v_m$ is linearly independent. We want to show that $\Gamma$ is surjective.

Let $W = span(v_1,...,v_m)$ be a subspace of $V$. Then $v_1,...,v_m$ is a basis of the subspace $W$. We can extend it to a basis of $V$, $v_1,...,v_m, u_1,...,u_n$.

Suppose $(x_1,...,x_m) \in F^m$. We can define a linear functional on $V$ by $\phi(v_j) = x_j, j = 1,...,m$, $\phi(u_k) = 0, k=1,...,n$. By 3.4 $\phi$ is well-defined. Since $(x_1,...,x_m)$ is arbitrary, $range \Gamma = F^m$. We conclude that $\Gamma$ is surjective.

$\Leftarrow$
Suppose $\Gamma$ is surjective. We want to show that $v_1,...,v_m$ is linearly independent.

Assume towards contradiction that $v_1,...,v_m$ is not linearly independent. Then there exists $i \in \\{1,...,m\\}$ such that $v_i = a_1 v_1 + ... + a_{i-1} v_{i-1}$ by 2.19. Applying $\phi$, we have

$$\phi(v_i) = a_1 \phi(v_1) + ... + a_{i-1} \phi(v_{i-1})$$

Consider $(0,..0,1,0,...0) \in F^m$ where the ith coordinate is 1 and all other coordinates are 0. 

Since $\Gamma$ is surjective, there exists $\phi \in V'$ such that $\Gamma(\phi) = (0,..0,1,0,...0)$. Then $\phi(v_1) = ... = \phi(v_{i-1}) = 0$ and $\phi(v_i) = 1$. However, $\phi(v_i) = a_1 \phi(v_1) + ... + a_{i-1} \phi(v_{i-1}) = 0$ which is a contradiction. 

We conclude that $v_1,...,v_m$ is linearly independent.



### (25) Suppose $V$ is finite-dimensional and $\phi_1,...,\phi_m \in V'$. Define a linear map $\Gamma: V \rightarrow F^m$ by $\Gamma(v) = (\phi_1(v), ..., \phi_m(v))$.

#### (a) Prove that $\phi_1,...,\phi_m$ spans $V'$ if and only if $\Gamma$ is injective.



#### (b) Prove that $\phi_1,...,\phi_m$ is linearly independent if and only if $\Gamma$ is surjective.



### (29) Suppose $V$ and $W$ are finite-dimensional and $T \in L(V, W)$. 

#### (a) Prove that if $\phi \in W'$ and $null T' = span(\phi)$, then $range T = null \phi$.
First consider $\phi = 0$. Then $null \phi = W$. Since $span(0) = \\{0\\}$, $null T' = \\{0\\}$. Then $T'$ is injective by 3.15, and $T$ is surjective by 3.129, and $range T = W$. Thus $W = range T = null \phi$.

For the rest of the proof suppose $\phi \neq 0$.

Since $null T' = span(\phi)$, $T'(\phi) = 0$. Then $\phi(Tv) = 0$ for all $v \in V$. Thus $range T \subseteq null \phi$.

To complete the proof, we will show that $null \phi$ and $range T$ have the same dimension. 

Suppose $dim W = m$.

Since $null T' = span(\phi)$, $dim null T' = 1$. We have $null T' = (range T)^0$ by 3.128, so $dim (range T)^0 = 1$. Then $dim range T = dim W - dim (range T)^0 = m - 1$ by 3.125.

Since $dim W = dim null \phi + dim range \phi$ by 3.21, and $dim range \phi = 1$, we have $dim null \phi = m-1$.

Thus $dim null \phi = dim range T = m-1$ and together with the fact that $range T \subseteq null \phi$, we conclude that $range T = null \phi$.


#### (b) Prove that if $\psi \in V'$ and $range T' = span(\psi)$, then $null T = null \psi$.
First consider $\psi = 0$. Then $null \psi = V$. Since $span(0) = \\{0\\}$, $range T' = \\{0\\}$. $T'(\phi) = 0$ for all $\phi \in W'$. Hence $T'=0$, and $T=0$ (from exercise 16). Thus $V = null T = null \psi$.

For the rest of the proof suppose $\psi \neq 0$.

Suppose $v \in null T$. Then $Tv = 0$. Since $\psi \in range T'$, there exists $\phi \in W'$ such that $T'(\phi) = \psi$. Then

$$0 = \phi(0) = \phi(Tv) = (T'(\phi))(v) = \psi(v).$$

Thus $v \in null \psi$. We conclude that $null T \subseteq null \psi$.

To complete the proof, we will show that $null T$ and $null \psi$ have the same dimension.

Suppose $dim V = n$.

Since $range T' = span(\psi)$, $dim range T' = 1$. By 3.130, $dim range T = dim range T' = 1$. Then $dim null T = dim V - dim range T = n - 1$. We also have $dim null \psi = dim V - dim range \psi = n - 1$. 

Thus $dim null \psi = dim null T = n-1$ and together with the fact that $null T \subseteq null \psi$, we conclude that $null T = null \psi$.



### (30) Suppose $V$ is finite-dimensional and $\phi_1,...,\phi_n$ is a basis of $V'$. Show that there exists a basis of $V$ whose dual basis is $\phi_1,...,\phi_n$.




### (31) Suppose $U$ is a subspace of $V$. Let $i: U \rightarrow V$ be the inclusion map defined by $i(u) = u$. Thus $i' \in L(V', U')$. 

#### (a) Show that $null i' = U^0$. 

Suppose $\phi \in null i'$. Then $i'(\phi) = 0$. 

We have $i'(\phi) (u) = 0$ for all $u \in U$. Then $\phi (i (u)) = \phi(u)= 0$ for all $u \in U$. Thus $\phi \in U^0$.

Suppose $\phi \in U^0$. Then $\phi(u) = 0$ for all $u \in U$. 

We have $\phi(u) = \phi(i(u)) = i'(\phi)(u) = 0$ for all $u \in U$. Thus $\phi \in null i'$.


#### (b) Prove that if $V$ is finite-dimensional, then $range i' = U'$.

Since $V$ is finite-dimensional, we have 

$$dim range i' = dim V' - dim null i' .$$

We also have

$$
\begin{aligned}
dim U' &= dim U \\
    &= dim V - dim U^0 \\
    &= dim V' - dim null i'
\end{aligned}
$$

where the first equality comes from 3.111, the second equality comes from 3.125, and the third equality comes from 3.111 and part (a). Thus $dim range i' = dim U'$. 

Since $range i' \subseteq U'$, $range i' = U'$ by 2.39.


#### (c) Prove that if $V$ is finite-dimensional, then $\tilde{i'}$ is an isomorphism from $V'/U^0$ onto $U'$.

From 3.107, $i'$ is an isomorphism from $V' / (null i')$ onto $range i'$. Since $null i' = U^0$ and $range i' = U'$ from part (a) and (b), $\tilde{i'}$ is an isomorphism from $V'/U^0$ onto $U'$.



### (33) Suppose $U$ is a subspace of $V$. Let $\pi: V \rightarrow V/U$ be the usual quotient map. Thus $\pi' \in L((V/U)', V')$.

#### (a) Show that $\pi'$ is injective.

Suppose $\phi \in (V/U)'$. Suppose $\pi'(\phi) = 0$. Then $(\pi'(\phi))(v) = 0$ for all $v \in V$. 

$\phi(\pi(v)) = \phi(v + U) = 0$ for all $v + U \in V/U$. Thus $\phi = 0$. 

Hence $\pi'$ is injective by 3.15.


#### (b) Show that $range \pi' = U^0$. 

First suppose $\psi \in range \pi'$. Then there exists $\phi \in (V/U)'$ such that $\pi' (\phi) = \psi$. 

Suppose $\pi(v) = v + U = 0 + U$. Then $v \in U$. Thus $null \pi = U$.

Suppose $u \in U$. Then 

$$\psi(u) = \pi'(\phi)(u) = \phi(\pi(u)) = \phi(0 + U) = 0.$$

Thus $\psi \in U^0$.

For the other direction, suppose $\psi \in U^0$. Then $\psi(u) = 0$ for all $u \in U$.

Define $\phi \in (V/U)'$ such that 

$$\phi(v + U) = \psi(v)$$ 

for all $v \in V$. 

We want to show that $\phi$ is a linear map.

Suppose $v_1 + U \in V/U, v_2 + U \in V/U$ and $v_1 + U = v_2 + U$. Then $v_1 - v_2 \in U$ by 3.101. Therefore $\psi(v_1 - v_2) = 0$, and 

$$\phi(v_1 + U) = \psi(v_1) = \psi(v_2) = \phi(v_2 + U).$$

Hence $\phi$ is well-defined.

Suppose $v_1 + U, v_2 + U \in V/U$. Then we have

$$
\begin{aligned}
\phi((v_1 + U) + (v_2 + U)) &= \phi((v_1 + v_2) + U) \\
    &= \psi(v_1 + v_2) \\
    &= \psi(v_1) + \psi(v_2) \\
    &= \phi(v_1 + U) + \phi(v_2 + U)
\end{aligned}
$$

Suppose $v + U \in V/U, \lambda \in F$. Then we have

$$
\begin{aligned}
\phi(\lambda (v+U)) &= \phi(\lambda v + U) \\
    &= \psi(\lambda v) \\
    &= \lambda \psi(v) \\
    &= \lambda \phi(v + U)
\end{aligned}
$$

Thus $\phi$ is well-defined and satisfies additivity and homogeneity, and therefore is a linear map. 

Note that 

$$\psi(v) = \phi(v + U) = \phi(\pi(v)) = \pi'(\phi)(v)$$

for all $v \in V$.

Hence $\psi = \pi'(\phi)$, and $\pi'$ is surjective.


#### (c) Conclude that $\pi'$ is an isomorphism from $(V/U)'$ onto $U^0$.

From part (a) and (b), $\pi': (V/U)' \rightarrow U^0$ is injective and surjective. We conclude that $\pi'$ is an isomorphism from $(V/U)'$ onto $U^0$.

