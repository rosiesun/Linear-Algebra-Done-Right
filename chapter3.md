Linear Algebra Done Right - Chapter 3 <br>
Linear Maps
================
Rosie Sun <br>
2026-04-02

# 3A Vector Space of Linear Maps

### 3.1 Definition: linear map
A linear map from $V$ to $W$ is a function $T:V \rightarrow W$ with the following properties. 

Additivity: $T(u+v) = Tu+Tv$ for all $u,v \in V$.

Homogeneity: $T(\lambda v) = \lambda (Tv)$ for all $\lambda in F$ and all $v \in V$.

### 3.2 Notation
- The set of linear maps from $V$ to $W$ is denoted by $L(V,W)$.
- THe set of linear maps from $V$ to $V$ is denoted by $L(V)$. In other words, $L(V,V)=L(V)$.

### 3.4 Linear map lemma
Suppose $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_n \in W$. Then there exists a unique linear map $T:V \rightarrow W$ such taht $T v_k = w_k$ for each $k = 1,...,n$.

### 3.5 Definition: addition and scalar multiplication on $L(V,W)$
Suppose $S, T \in L(V,W)$ and $\lambda \in F$. The sum $S+T$ and the product $\lambda T$ are the linear maps from $V$ to $W$ defined by $(S+T)(v) = Sv + Tv$ and $(\lambda T)(v) = \lambda (Tv)$ for all $v \in V$.

### 3.6 $L(V,W)$ is a vector space
With the operations of addition and scalar multiplication as defined above, $L(V,W)$ is a vector space.

### 3.7 Definition: product of linear maps
If $T \in L(U,V)$ and $S \in L(V,W)$ then the product $ST \in L(U,W)$ is defined by $(ST)(u) = S(Tu)$ for all $u \in U$.

### 3.8 Algebraic properties of products of linear maps
Associativity: $(T_1 T_2)T_3 = T_1 (T_2 T_3)$ whenever $T_1, T_2, T_3$ are linear maps such that the products make sense (meaning $T_3$ maps into the domain of $T_2$ and $T_2$ maps into the domain of $T_1$).

Identity: $TI = IT = T$ whenever $T \in L(V,W)$; here the first $I$ is the identity operator on $V$ and the second $I$ is the identity operator on $W$.

Distributive properties: $(S_1 + S_2) T = S_1 T + S_2 T$ and $S(T_1 + T_2) = ST_1 + ST_2$ whenever $T, T_1, T_2 \in L(U,V)$ and $S, S_1, S_2 \in L(V,W)$. 

### 3.10 Linear maps take 0 to 0
Suppose $T$ is a linear map from $V$ to $W$. Then $T(0)=0$.


## Exercises

#### (4) Suppose $T \in L(V,W)$ and $v_1,...,v_m$ is a list of vectors in $V$ such that $Tv_1,...,Tv_m$ is a linearly independent list in $W$. Prove that $v_1,...,v_m$ is linearly independent.
Let $a_1 v_1 + ... + a_m v_m = 0$.

Applying $T$,

$$T(a_1 v_1 + ... + a_m v_m) = T0 = 0$$

By linearity, 

$$a_1 Tv_1 + ... + a_m Tv_m = 0$$

Since $Tv_1,...,Tv_m$ is linearly independent, $a_1 = ... = a_m = 0$. Therefore $v_1,...,v_m$ is linearly independent in $V$.


#### (5) Prove that $L(V,W)$ is a vector space, as was asserted in 3.6.
Commutativity: Let $S,T \in L(V,W)$, let $v \in V$. 

$$(S+T)(v) = Sv + Tv = Tv + Sv = (T+S)(v)$$ 

by the fact that $W$ is a vector space. 

Associativity: Let $R, S, T \in L(V,W)$, let $v \in V$.

$$((R+S)+T)(v) = (R+S)(v) + Tv = Rv + Sv + Tv = Rv + (S+T)(v) = (R+(S+T))(v)$$

by the fact that $W$ is a vector space.

Additive identity: Defined in 3.3. There exists $0 \in L(V,W)$ where $0v=0$. Let $T \in L(V,W)$. Then

$$(T+0)(v) = Tv + 0(v) = Tv + 0 = Tv$$

Additive inverse: Let $T \in L(V,W)$. Define $(-T) \in L(V,W)$ such that $(-T)(v) = -Tv$. $(-T) \in L(V,W)$ since $(-T)(u+v) = -T(u+v) = (-Tu) + (-Tv) = (-T)(u) + (-T)(v)$, and $(-T)(av) = -T(av) = -aTv = a(-T)(v)$. Thus additivity and homogeneity are satisfied, so $(-T)$ is a linear map. Then 

$$(T+(-T))(v) = Tv + (-T)(v) = Tv + (-Tv) = 0$$

Multiplicative identity: Let $T \in L(V,W)$.

$$(1T)(v) = 1(Tv) = Tv$$

Distributive properties: Let $S, T \in L(V,W), a,b \in F$. Then 

$$(a(S+T))(v) = a((S+T)(v)) = a(Sv + Tv) = a(Sv) + a(Tv) = (aS)(v) + (aT)(v)$$

And 

$$((a+b)T)(v) = (a+b)(Tv) = a(Tv) + b(Tv) = (aT)(v) + (bT)(v)$$


#### (6) Prove that multiplication of linear maps has the associative, identity, and distributive properties asserted in 3.8.

Associativity: Let $T_3 \in L(U,V), T_2 \in L(V, W), T_1 \in L(W,Z)$. Then 

$$((T_1 T_2)T_3)(u) = (T_1 T_2)(T_3 u) = T_1 (T_2 (T_3 u))$$

and 

$$(T_1(T_2 T_3))(u) = T_1 ((T_2 T_3)(u)) = T_1 (T_2 (T_3 u))$$

Thus $(T_1 T_2) T_3 = T_1 (T_2 T_3)$.

Identity: Let $T \in L(V,W)$. 

$$(TI)(v) = T(Iv) = Tv$$

And

$$(IT)(v) = I(Tv) = Tv$$

Thus $TI = IT = T$.

Distributive properties: 

Let $T, T_1, T_2 \in L(U,V), S, S_1, S_2 \in L(V,W)$. Then 

$$(S(T_1+T_2))(u) = S((T_1+T_2)(u)) = S(T_1 u + T_2 u) = S(T_1 u) + S (T_2 u) = (S T_1)(u) + (S T_2)(u)$$

And

$$((S_1+S_2)T)(u) = (S_1+S_2)(Tu) = S_1(Tu) + S_2(Tu) = (S_1 T)(u) + (S_2 T)(u)$$


#### (7) Show that every linear map from a one-dimensional vector space to itself is multiplication by some scalar. More precisely, prove that if $dim V = 1$ and $T \in L(V)$, then there exists $\lambda \in F$ such that $Tv=\lambda v$ for all $v \in V$.
Let $v \in V$. Let $e$ be a basis of $V$. 

Since $Te \in V$, we can write $Te = \lambda e$ for some unique $\lambda in F$.

Let $v=ae$ for some $a \in F$.

We have

$$Tv = T(ae) = aTe = a (\lambda e) = \lambda(ae) = \lambda v$$ 

Therefore $T$ is multiplication by $\lambda$.


#### (8) Give an example of a function $\phi: R^2 \rightarrow R$ such that $\phi (av) = a \phi(v)$ for all $a \in R$ and $v \in R^2$, but $\phi$ is not linear.
Let $\phi(x,y) = x^2 / y$ if $y \neq 0$, and $\phi(x,y) = 0$ if $y=0$.

When $y \neq 0$, 

$$\phi(ax, ay) = (ax)^2/(ay) = a x^2 /y = a phi(x,y)$$

When $y = 0$, 

$$\phi(ax,ay) = 0 = a phi(x,y)$$

Therefore the function satisfies the homogeneity property.

When $y_1 \neq 0, y_2 \neq 0, y_1 + y_2 \neq 0$,

$$\phi(x_1 + x_2, y_1 + y_2) = (x_1+x_2)^2/(y_1 + y_2)$$

$$\phi(x_1,y_1) + \phi(x_2, y_2) = x_1^2 / y_1 + x_2^2 / y_2 $$

which is not equal to each other.


#### (9) Give an example of a function $\phi: C \rightarrow C$ such that $\phi(w+z) = \phi(w) + \phi(z)$ for all $w, z \in C$ but $\phi$ is not linear. 
Let $\phi(z)=Re(z)$. First we show that it satisfies linearity. 

Let $w=a+bi, z=c+di$. We have 

$$\phi(w+z)=Re(a+bi+c+di)= a+c = Re(a+bi)+Re(c+di) = \phi(w) + \phi(z)$$

Now we show that it does not satisfy homogeneity. Let $w=a+bi, \lambda = i$. We have

$$\phi(iw) = Re(-b+ai) = -b$$

$$i \phi(w) = i Re(a+bi) = ai$$

Therefore $\phi$ is not linear.


#### (11) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that $T$ is a scalar multiple of the identity if and only if $ST=TS$ for every $S \in L(V)$.
$\rightarrow$

Let $T = aI \in L(V), v \in V, S \in L(v)$. Then $Tv = (aI)v = a(Iv) = av$. We have 

$$(ST)(v) = S(Tv) = S(av) = a(Sv)$$

$$(TS)(v) = T(Sv) = aI(Sv) = a(Sv)$$

Thus $ST=TS$ as desired.

$\leftarrow$

Since $V$ is finite-dimensional, let $v_1,...,v_n$ be a basis for $V$. Given that $ST=TS$ for every $S \in L(V)$, define $S$ such that $S(v_j) = v_i, S(v_k)=0, i,j \in \\{1,...,n\\}, k \neq j$. i.e. $S$ sends the $v_j$ to $v_i$ and kills the other dimensions.

$$(ST)(v_j) = S(Tv_j) = S(a_1 v_1 + ... + a_n v_n) = a_i v_i, a_1,...,a_n \in F$$. 

$$(TS)(v_j) = T(Sv_j) = T(v_i)$$. 

Then $Tv_i = a_i v_i$. Since $i$ is arbitrary, $T v_i = a_i v_i, i = 1,...,n$.

Reapplying the linear maps, we have 

$$(ST)(v_j) = S(Tv_j) = S(a_j v_j) = a_j v_i$$

$$(TS)(v_j) = T(Sv_j) = T(v_i) = a_i v_i$$

Then $a_i = a_j, i,j=1,...,n$. Hence $T = aI$.


#### (12) Suppose $U$ is a subspace of $V$ with $U \neq V$. Suppose $S \in L(U,W)$ and $S \neq 0$. Define $T: V \rightarrow W$ by $Tv = Sv$ if $v \in U$ and $Tv = 0$ if $v \in V, v \notin U$. Prove that $T$ is not a linear map on $V$.
Since $S \neq 0$, $Su \neq 0$ for some $u \in U$. Let $v \in V, v \notin U$. Then $v+u \notin U$. $T(v+u) = 0$. However, $Tu + Tv = Su + 0$. Then $T(v+u) \neq Tu + Tv$. Hence $T$ is not a linear map on $V$.


#### (13) Suppose $V$ is finite-dimensional. Prove that every linear map on a subspace of $V$ can be extended to a linear map on $V$. In other words, show that if $U$ is a subspace of $V$ and $S \in L(U,W)$, then there exists $T \in L(V,W)$ such that $Tu = Su$ for all $u \in U$.
Let $u_1,...,u_m$ be a basis for $U$, and extend it to a basis $u_1,...,u_m, v_1,...,v_n$ for $V$. By 3.4, there exists a unique linear map $T: V \rightarrow W$ such that $T u_k = S u_k$ for each $k = 1,...,m$ and $T v_j = 0$ for each $j = 1,...,n$.

Let $u \in U$. Then 

$$Tu = T(a_1 u_1 + ... a_m u_m) = T(a_1 u_1) + ... + T(a_m u_m) = a_1 Tu_1 + ... + a_m Tu_m = a_1 Su_1 + ... a_m Su_m = S(a_1 u_1) + ... + S(a_m u_m) = S(a_1 u_1 + ... + a_m u_m) = S(u)$$. 


#### (15) Suppose $v_1,...,v_m$ is a linearly dependent list of vectors in $V$. Suppose also that $W \neq \\{0\\}$. Prove that there exist $w_1,...,w_m \in W$ such that no $T \in L(V,W)$ satisfies $Tv_k = w_k$ for each $k=1,...,m$.  

Assume towards contradiction that there exist $T$ such that $Tv_k = w_k$ for each $k$.

Since $v_1,...,v_m$ is a linearly dependent list of vectors, there exist scalars $a_1,...,a_m$, not all 0, such that $a_1 v_1 + ... + a_m v_m = 0$. Let $j$ be an index such that $a_j \neq 0$. 

Let $w_j = w \neq 0$, and $w_i=0$ for all $i \neq j$.

Applying $T$, we have $T(0) = 0$, but

$$T(a_1 v_1 + ... a_m v_m) = a_1 Tv_1 + ... a_m Tv_m = a_j w \neq 0$$

which is a contradiction. 


#### (16) Suppose $V$ is finite-dimensional with $dim V > 1$. Prove that there exist $S,T \in L(V)$ such that $ST \neq TS$.
Let $V=P_3(F)$. Let $p(z) \in V$. 

Define differentiation map and multiplication map $Dp=p', Mp = zp(z)$. Then 

$$(DM)(p) = D (z p(z)) = p + z p'$$

$$(MD)(p) = M (p') = z p'$$

Thus $DM \neq MD$.



# 3B Null Spaces and Ranges

### 3.11 Definition: null space
For $T \in L(V,W)$, the null space of $T$, denoted by $null T$, is the subset of $V$ consisting of those vectors that $T$ maps to 0: $null T = \\{v \in V: Tv = 0\\}$.

### 3.13 The null space is a subspace
Suppose $T \in L(V,W)$. Then $null T$ is a subspace of $V$.

### 3.14 Definition: injective
A function $T:V \rightarrow W$ is called injective if $Tv = Tu$ implies $u=v$.

### 3.15
Let $T \in L(V,W)$. Then $T$ is injective if and only if $null T = \\{0\\}$. 

### 3.16 Definition: range
For $T \in L(V,W)$, the range of $T$ is the subset of $W$ consisting of those vectors that are equal to $Tv$ for some $v \in V$: $range T = \\{Tv: v \in V\\}$.

### 3.18 The range is a subspace
If $T \in L(V,W)$, then $range T$ is a subspace of $W$.

### 3.19 Definition: surjective
A function $T: V \rightarrow W$ is called surjective if its range equals $W$.

### 3.21 Fundamental theorem of linear maps
Suppose $V$ is finite-dimensional and $T \in L(V,W)$. Then $range T$ is finite-dimensional and $dim V = dim null T + dim range T$.

### 3.22 Linear map to a lower-dimensional space is not injective
Suppose $V$ and $W$ are finite-dimensional vector spaces such that $dim V > dim W$. Then no linear map from $V$ to $W$ is injective.

### 3.24 Linear map to a higher-dimensional space is not surjective
Suppose $V$ and $W$ are finite-dimensional vector spaces such that $dim V < dim W$. Then no linear map from $V$ to $W$ is surjective.

### 3.26 Homogeneous system of linear equations
A homogeneous system of linear equations with more variables than equations has nonzero solutions.

### 3.28 System of linear equations with more equations than variables
A system of linear equations with more equations than variables has no solution for some choice of the constant terms.


## Exercises

#### (7) Suppose $V$ and $W$ are finite-dimensional with $2 \leq dim V \leq dim W$. Show that $\\{T \in L(V,W): T is not injective \\}$ is not a subspace of $L(V,W)$.
Let $v_1,...,v_n$ be a basis of $V$. Let $w_1,...,w_n$ be a list of linearly independent vectors in $W$. We know that there are at least n linearly independent vectors because $dim W >= dim V$.

Define linear maps $S, T \in L(V,W)$ such that

$$S(v_j) = \begin{cases} 
0 & j = 1 \\ 
w_j & j \neq 1 
\end{cases}$$

$$T(v_j) = \begin{cases} 
0 & j = 2 \\ 
w_j & j \neq 2
\end{cases}$$

Then $null S = span(v_1)$ and $null T = span(v_2)$. Thus $S, T$ are not injective.

We want to show that $S+T$ is injective.

Suppose $(S+T)(v) = 0$ for some $v \in V$. Then $v=a_1 v_1 + ... + a_n v_n$, for some $a_1,...,a_n \in F$. We can rewrite the equation as 

$$(S+T)(v) = S(a_1 v_1 + ... + a_n v_n) + T(a_1 v_1 + ... + a_n v_n) = a_1 w_1 + a_2 w_2 + 2 a_3 w_3 + ... + 2 a_n w_n$$

since $S(a_1 v_1) + T(a_1 v_1) = a_1 w_1$, and $S(a_2 v_2) + T(a_2 v_2) = a_2 w_2$.

Since $w_1,...,w_n$ is linearly independent by design, $a_1 = a_2 = ... = a_n = 0$, which means $v=0$. Thus $null (S+T) = \\{0\\}$.

Hence $(S+T)$ is injective, while $S$ and $T$ are both non-injective. $\\{T \in L(V,W): T is not injective \\}$ is not closed under addition, therefore is not a subspace of $L(V,W)$.


#### (8) Suppose $V$ and $W$ are finite-dimensional with $dim V \geq dim W \geq 2$. Show that $\\{T \in L(V,W): T is not surjective \\}$ is not a subspace of $L(V,W)$.
Let $v_1,...,v_n$ be a basis of $V$ and $w_1,...,w_m$ be a basis of $W$. $n \geq m$.

Define two linear maps $S, T \in L(V,W)$ such that

$$S(v_j) = \begin{cases} 
0 & j = 1 \\ 
w_j & 2 \leq j \leq m \\
0 & j > m
\end{cases}$$

$$T(v_j) = \begin{cases} 
0 & j = 2 \\ 
w_j & 1 \leq j \leq m, j \neq 2 \\
0 & j > m
\end{cases}$$

Then $range S = span(w_2, ..., w_m) \subset W$ and $range T = span(w_1, w_3, ..., w_m) \subset W$. $S, T$ are not surjective.

We want to show that $(S+T)$ is surjective. Let $w \in W$. Then $w = a_1 w_1 + ... + a_m w_m$ for some $a_1,...,a_m \in F$. Find $v \in V$ such that $v = a_1 v_1 + ... + a_m v_m + 0 v_{m+1} + ... 0 v_n$. This $v$ exists since $v_1,...,v_n$ are basis vectors. We have

$$(S+T)(v) = \sum_{j=1}^{n} a_j (S+T)(v_j)= a_1 w_1 + a_2 w_2 + ... + a_m w_m$$

by linearity, $(S+T)(v_j) = w_j$ for $1 \leq j \leq m$ and the fact that $(S+T)(v_j) = 0$ for $j > m$.

Thus $w \in range(S+T)$, and $W \subseteq range(S+T)$.

Hence $(S+T)$ is surjective while $S, T$ are not surjective. $\\{T \in L(V,W): T is not surjective \\}$ is not closed under addition, therefore is not a subspace of $L(V,W)$.


#### (9) Suppose $T \in L(V,W)$ is injective and $v_1,...,v_n$ is linearly independent in $V$. Prove that $Tv_1,...,Tv_n$ is linearly independent in $W$.
Suppose $a_1 Tv_1 + ... + a_n Tv_n = 0$, for some $a_1,...,a_n \in F$. Rewriting, we have $T(a_1 v_1 + ... + a_n v_n) = 0$. Since $T$ is injective, $null T = \\{0\\}$. We conclude that $a_1 v_1 + ... + a_n v_n = 0$. Since $v_1,...,v_n$ is linearly independent, $a_1=...=a_n=0$. Thus $Tv_1,...,Tv_n$ is linearly independent in $W$.


#### (10) Suppose $v_1,...,v_n$ spans $V$ and $T \in L(V,W)$. Show that $Tv_1,...,Tv_n$ spans $range T$.
Let $w \in range T$. Then there exist some $v \in V$ such that $Tv = w$. Since $v_1,...,v_n$ spans $V$, we can rewrite as $T(v) = T(a_1 v_1 + ... + a_n v_n) = a_1 T v_1 + ... + a_n T v_n$. Thus $w \in span(Tv_1,..., Tv_n)$. Therefore $Tv_1, ..., Tv_n$ spans $range T$.


#### (11) Suppose that $V$ is finite-dimensional and that $T \in L(V,W)$. Prove that there exists a subspace $U$ of $V$ such that $U \cap null T = \\{0\\}$ and $range T = \\{Tu: u \in U\\}$.
Let $v_1,...,v_n$ be a basis of $null T$. Since $dim V \geq dim null T$, we can extend it to a basis of $V$, $v_1,...,v_n, u_1,...,u_m$. 

Let $U = span(u_1,...,u_m)$. Since $u_1,...,u_m$ is linearly independent, $u_1,...,u_m$ is a basis of $U$. It follows that $U + null T$ is a direct sum. Thus $U \cap null T = \\{0\\}$ by 1.46.

For $v \in V$, we can rewrite as $v=a_1 v_1 + ... + a_n v_n + b_1 u_1 + ... + b_m u_m$, for some $a_1,...,a_n, b_1,...,b_m$.

Applying $T$, we have

$$Tv = T(a_1 v_1 + ... + a_n v_n + b_1 u_1 + ... + b_m u_m) = b_1 Tu_1 + ... + b_m Tu_m = T (b_1 u_1 + ... + b_m u_m)$$

which establishes that $range T \subseteq \\{Tu: u \in U\\}$. The reverse inclusion is trivial.

Therefore $range T = \\{Tu: u \in U\\}$.


#### (12) Suppose $T$ is a linear map from $F^4$ to $F^2$ such that $null T = \\{(x_1,x_2,x_3,x_4) \in F^4: x_1=5x_2, x_3=7x_4\\}$. Prove that $T$ is surjective.
Given the definition of $null T$, a basis of $null T$ is $(5,1,0,0), (0,0,7,1)$, which implies that $dim null T = 2$. Thus by 3.21,

$$dim range T = dim (F^4) - dim null T = 4-2=2$$

Since $T: F^4 \rightarrow F^2$ and $dim range T = dim F^2 = 2$, we have $range T = F^2$.

By definition, $range T$ is surjective.


#### (16) Suppose $V$ and $W$ are both finite-dimensional. Prove that there exists an injective linear map from $V$ to $W$ if and only if $dim V \leq dim W$.
$$\rightarrow$$

Let $T \in L(V,w)$. Assume $T$ is injective. Then $null T = \\{0\\}$ and $dim null T = 0$.

Therefore $$dim V = dim null T + dim range T = dim range T \leq dim W$$

$$\leftarrow$$

Assume $dim V \leq dim W$. 

Let $v_1,...,v_n$ be a basis of $V$. Let $w_1,...,w_m$ be a basis of $W$. Since $dim V \leq dim W$, $n \leq m$. 

Define $T \in L(V,W)$ such that 

$$Tv_i=w_i, i=1,...,n$$

To show that $T$ is injective, assume $Tv=0$ for some $v \in V$. We can rewrite $v=a_1 v_1  + ... + a_n v_n$ for some $a_1,...,a_n$.

Applying $T$,

$$Tv = a_1 Tv1 + ... + a_n Tv_n = a_1 w_1 + ... + a_n w_n = 0$$

Since $w_1,...,w_n$ are linearly independent, $a_1,...,a_n = 0$.

Thus $v=0$, so $null T = \\{0\\}$. Therefore $T$ is injective.


#### (17) Suppose $V$ and $W$ are both finite-dimensional. Prove that there exists an surjective linear map from $V$ to $W$ if and only if $dim V \geq dim W$.
$$\rightarrow$$

Let $T \in L(V,W)$. Assume $T$ is surjective. Then $range T = W$.

$$dim V = dim null T + dim range T = dim null T + dim W \geq dim W$$

$$\leftarrow$$

Assume $dim V \geq dim W$. Let $v_1,...,v_n$ be a basis of $V$, $w_1,...,w_m$ be a basis of $W$. $n \geq m$.

Define $T \in L(V,W)$ such that 

$$T(v_i) = w_i, i=1,...,m$$

We want to show that $T$ is surjective. Let $w \in W$. We can rewrite $w=a_1 w_1 + ... + a_m w_m$ for some $a_1,...,a_m$. Then 

$$w = a_1 w_1 + ... + a_m w_m = a_1 Tv_1 + ... + a_m Tv_m = T(a_1 v_1 + ... + a_m v_m)$$

Therefore $w \in range T$. Thus $range T = W$ and we conclude that $T$ is surjective.


#### (19) Suppose $W$ is finite-dimensional and $T \in L(V,W)$. Prove that $T$ is injective if and only if there exists $S \in L(W,V)$ such that $ST$ is the identity operator on $V$.

$$\rightarrow$$

Assume $T$ is injective. Let $v_1,...,v_n$ be a basis for $V$. Since $T is injective, $Tv_1,...,Tv_n$ is linearly independent in $W$ and spans $range T$ (exercise 9, 10). Then $Tv_1, ..., Tv_n$ is a basis of $range T$. We can extend it to a basis of $W$, $Tv_1,...,Tv_n, u_1,...,u_m$. 

Define $S \in L(W,V)$ such that 

$$S(Tv_i) = v_i, i=1,...,n$$ 

$$S(u_j) = 0, j=1,...,m$$ 

Then $ST(v_i)=v_i$.

Since $ST$ is linear and agrees with the identity operator on the basis vectors $v_1,..., v_n$ of $V$, it must be the identity operator on all of $V$.

$$\leftarrow$$

Assume there exists $S \in L(W,V)$ such that $ST$ is the identity operator on $V$. Assume towards contradiction that $T$ is not injective, i.e. $null T \neq \\{0\\}$. Let $v \in null T, v \neq 0$. Then we have 

$$S(Tv)= S(0)=0$$

$$(ST)(v)=v \neq 0$$

which is a contradiction. Therefore we conclude that $T$ is injective.


#### (20) Suppose $W$ is finite-dimensional and $T \in L(V,W)$. Prove that $T$ is surjective if and only if there exists $S \in L(W,V)$ such that $TS$ is the identity operator on $W$.
$$\rightarrow$$

Assume $T$ is surjective, i.e. $range T = W$. Let $w_1,...,w_n$ be a basis of $W$. Since $w_1,...,w_n \in range T$, there exist $v_1,...,v_n$ such that $Tv_1=w_1,...,Tv_n=w_n$. Define $S \in L(W,V)$ such that 

$$S(w_i)=v_i, i=1,...,n$$

Then 

$$TS(w_i) = T(Sw_i)=Tv_i=w_i$$ 

for $i=1,...,n$. Since Since $TS$ is linear and agrees with the identity operator on the basis vectors $w_1,..., w_n$ of $w$, it must be the identity operator on all of $W$.

$$\leftarrow$$

Assume that there exists $S \in L(W,V)$ such that $TS$ is the identity operator on $W$. Let $w \in W$. $TS(w) = T(Sw)=w$. Therefore $w \in range T$. Therefore $range T = W$, and $T$ is surjective.


#### (25) Suppose that $W$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $null S \subseteq null T$ if and only if there exists $E \in L(W)$ such that $T=ES$.
$$\leftarrow$$

Assume there exists $E \in L(W)$ such that $T=ES$. We want to show that $null S \subseteq null T$. 

Let $v \in null S$. Then $Sv = 0$. 

$$Tv=(ES)(v)=E(Sv)=E(0)=0$$

Hence $v \in null T$. Thus $null S \subseteq null T$ as desired.

$$\rightarrow$$

Assume $null S \subseteq null T$. Let $w_1,...,w_n$ be a basis of $range S$. Then there exist some $v_1,...,v_n \in V$ such that $Sv_1=w_1,...,Sv_n=w_n$. 

Define $E$ such that 

$$E w_i = Tv_i$$

for $i=1,...,n$.

To show $E$ is well-defined, assume there is some $u_i \in V$ such that $Sv_i = Su_i$ for $i \in \\{1,...,n\\}$. 

$$S(u_i) - S(v_i) = S(u_i - v_i) = 0$$

Therefore $u_i - v_i \in null S$. 

Since $null S \subseteq null T$, $u_i - v_i \in null T$.

$$T(u_i - v_i) = T(u_i) - T(v_i) = 0$$

Therefore $T(u_i) = T(v_i)$. 

Thus it does matter if we had picked the pre-image $v_i$ or $u_i$, the linear map $E$ is well-defined. We can extend it to $range S$ by linearity. 

To extend from $range S$ to $W$, extend the basis vectors of $range S$ to $W$, $w_1,...,w_n, y_1,...,y_m$. Define $E(y_j) = 0, j=1,...,m$. 

Let $v \in V$. Then $Sv = a_1 w_1 + ... + a_n w_n$ for some $a_1,...,a_n$. Since $w_i = Sv_i$, we have

$$Sv = a_1 Sv_1 + ... + a_n Sv_n = S(a_1 v_1 + ... + a_n v_n)$$

Therefore 

$$v - (a_1 v_1 + ... + a_n v_n) \in null S$$

By the hypothesis, $null S \in null T$, so 

$$Tv - T(a_1 v_1 + ... + a_n v_n) = 0$$

Hence we conclude

$$ES(v) = E(Sv) = E(a_1 w_1 + ... + a_n w_n) = a_1 Tv_1 + ... + a_n Tv_n = Tv$$


#### (26) Suppose that $V$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $range S \subseteq range T$ if and only if there exists $E \in L(V)$ such that $S = TE$.
$$\leftarrow$$

Assume there exists $E \in L(V)$ such that $S=TE$. Let $w \in range S$. We want to show that $w \in range T$.
Since $w \in range S$, there exist some $v \in V$ such that $Sv = w$. By assumption, we have 

$$Sv = TEv = T(Ev) = w$$

Therefore $w \in range T$. Hence $range S \subseteq range T$.

$$\rightarrow$$
Assume $range S \subseteq range T$. We will construct $E \in L(V)$.

Let $v_1,...,v_n$ be a basis of $V$. Then $Sv_i=w_i$ for some $w_i, i=1,...,n$. By assumption, since $w_i \in range S$, $w_i \in range T$. Then there exist some $u_i$ such that $Tu_i=w_i$. 

Define $E$ such that

$$Ev_i = u_i$$

for $i = 1,...,n$.

Then 

$$Sv_i = w_i = Tu_i = T(Ev_i) = (TE)(v_i)$$

We can extend $E$ by linearity to the entire $V$.

Let $v \in V$. We can rewrite as $v = a_1 v_1 + ... + a_n v_n$ for some $a_1,...,a_n$.

We have 

$$Sv = \sum_{i=1}^{n} a_i Sv_i = \sum_{i=1}^{n} a_i w_i = \sum_{i=1}^{n} a_i Tu_i = \sum_{i=1}^{n} a_i T(Ev_i) = \sum_{i=1}^{n} a_i TE(v_i) = (TE)(v)$$

Thus $S=TE$.


#### (27) Suppose $P \in L(V)$ and $P^2 = P$. Prove that $V = null P \oplus range P$.
First we want to show that $null P \cap range P = \\{0\\}$.

Assume $v \in null P \cap range P$. Then $Pv = 0$ and $Px = v$ for some $x \in V$. 

Applying $P$, we have 

$$PPx=Pv=0$$

Therefore $Px \in null P$. Then $Px = 0 = v$. Thus $null P \cap range P = \\{0\\}$ as desired.

Next we want to show that $V = null P + range P$.

Let $v \in V$. We can rewrite as $v = (v - Pv) + Pv$. 

Note that $P(v - Pv) = Pv - PPv = 0$, therefore $v-Pv \in null P$. 

And $Pv \in range P$ by definition. Therefore $V = null P + range P$. 

Hence we conclude $V = null P \oplus range P$.



#### (30) Suppose $\phi \in L(V,F)$ and $\phi \neq 0$. Suppose $u \in V$ is not in $null \phi$. Prove that $V = null \phi \oplus \\{au: a \in F\\}$.
First we want to show that $null \phi \cap \\{au: a \in F\\} = \\{0\\}$. 

Assume $v \in null \phi \cap \\{au: a \in F\\}$. Then $\phi v = 0$ and $v = au$ for some $a \in F$.

Applying $\phi$, 

$$\phi v = \phi (au) = a \phi u = 0$$

Since $\phi u \neq 0$ by definition, $a=0$. Therefore $v=0$, and $null \phi$ and $\\{au: a \in F\\}$ are disjoint. 

Next we want to show that $V = null \phi + \\{au: a \in F\\}$.

Let $v = w + au$, where $w \in null \phi$, $a \in F$.

Applying $\phi$,

$$\phi v = \phi(w + au) = \phi w + \phi (au) = a \phi u$$

Then

$$a = \phi v / \phi u, \phi u \neq 0$$

Now rewrite $v = (v - au) + au$.

$$\phi (v-au) = \phi v - \phi (au) = \phi v - (\phi v / \phi u) \phi u = \phi v - \phi v = 0$$

Therefore $v-au \in null \phi$, and $V = null \phi + \\{au: a \in F\\}$.

Thus $V = null \phi \oplus \\{au: a \in F\\}$.


# 3C Matrices






# 3D Invertibility and Isomorphisms

### 3.59 Definition: Invertible, inverse
- A linear map $T \in L(V,W)$ is called invertible if there exists a linear map $S \in L(W,V)$ such that $ST$ equals the identity operator on $V$ and $TS$ equals the identity operator on $W$.
- A linear map $S \in L(W,V)$ satisfying $ST=I$ and $TS=I$ is called an inverse of $T$ (note that the first $I$ is the identity operator on $V$ and the second $I$ is the identity operator on $W$).

### 3.60 Inverse is unique
An invertible linear map has a unique inverse.

### 3.63 invertibility $iff$ injectivity and surjectivity
A linear map is invertible if and only if it is injective and surjective.

### 3.65
Suppose that $V$ and $W$ are finite-dimensional vector spaces, $dim V = dim W$, and $T \in L(V,W)$. Then $T$ is invertible $\iff T$ is injective $\iff T$ is surjective.

### 3.68
Suppose $V$ and $W$ are finite-dimensional vector spaces of the same dimension, $S \in L(W,V)$ and $T \in L(V,W)$. Then $ST=I$ if and only if $TS=I$.

### 3.69 Definition: isomorphism, isomorphic
- An isomorphism is an invertible linear map.
- Two vector spaces are called isomorphic if there is an isomorphism from one vector space onto the other one.

### 3.70
Two finite-dimensional vector spaces over $F$ are isomorhpic if and only if they have the same dimension.

### 3.71
Suppose $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_m$ is a basis of $W$. Then $M$ is an isomorphism between and $F^{m,n}$

### 3.72
Suppose $V$ and $W$ are finite-dimensional. Then $L(V,W)$ is finite-dimensional and $dim L(V,W) = (dim V) (dim W)$.


## Exercises

#### (2) Suppose $T \in L(U,V)$ and $S \in L(V,W)$ are both invertible linear maps. Prove that $ST \in L(U,W)$ is invertible and that $(ST)^{-1} = T^{-1} S^{-1}$.
Since $S, T$ are invertible, we have 

$$S S^{-1} = S^{-1} S = I$$ 

and 

$$T T^{-1} = T^{-1} T = I$$

We have 

$$(ST)(T^{-1} S^{-1}) = S (T T^{-1}) S^{-1} = S I S^{-1} = S S^{-1} = I$$

$$(T^{-1} S^{-1})(ST) = T^{-1} (S^{-1} S) T  = T^{-1} I T = T^{-1} T = I$$

Therefore $ST$ is invertible and $T^{-1} S^{-1}$ is the inverse of $ST$.


#### (4) Suppose $V$ is finite-dimensional and $dim V > 1$. Prove that the set of noninvertible linear maps from $V$ to itself is not a subspace of $L(V)$.


#### (6) Suppose that $W$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $null S = null T$ if and only if there exists an invertible $E \in L(W)$ such that $S=ET$.


#### (7) Suppose that $V$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $range S = range T$ if and only if there exists an invertible $E \in L(V)$ such that $S=TE$.

#### (11) Suppose $V$ is finite-dimensional and $S,T \in L(V)$. Prove that $ST$ is invertible $\iff S$ and $T$ are invertible.

#### (12) Suppose $V$ is finite-dimensional and $S,T,U \in L(V)$ and $STU=I$. Show that $T$ is invertible and that $T^{-1} = US$.

#### (14) Prove or give a counterexample: If $V$ is a finite-dimensional vector space and $R,S,T \in L(V)$ are such that $RST$ is surjective, then $S$ is injective.


#### (15) Suppose $T \in L(V)$ and $v_1,...,v_m$ is a list in $V$ such that $Tv_1,...,Tv_m$ spans $V$. Show that $v_1,...,v_m$ spans $V$.



