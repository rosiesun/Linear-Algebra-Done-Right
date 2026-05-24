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

Proof:

First we show the existence of a linear map $T$ with the desired property. Define $T: V \rightarrow W$ by

$$T(c_1 v_1 + ... + c_n v_n) = c_1 w_1 + ... + c_n w_n$$

where $c_1,...,c_n$ are arbitrary elements of $F$. The list $v_1,...,v_n$ is a basis of $V$. Thus the equation above does indeed define a function $T$ from $V$ to $W$ (because each element of $V$ can be uniquely written in the form $c_1 v_1 + ... + c_n v_n$). 

For each $k$, taking $c_k=1$ and the other $c$'s equal to 0 in the equation above shows that $Tv_k = w_k$.

If $u,v \in V$ with $u=a_1 v_1 + ... + a_n v_n, v=c_1 v_1 + ... + c_n v_n$, then 

$$T(u+v) = T((a_1 + c_1) v_1 + ... (a_n + c_n) v_n) = (a_1 + c_1) w_1 + ... + (a_n + c_n) w_n = (a_1 w_1 + ... + a_n w_n) + (c_1 w_1 + ... + c_n w_n) = Tu + Tv$$

Similarly, if $\lambda \in F$ and $v = c_1 v_1 + ... + c_n v_n$, then 

$$T(\lambda v) = T(\lambda c_1 v_1 + ... + \lambda c_n v_n) = \lambda c_1 w_1 + ... + \lambda c_n w_n = \lambda (c_1 w_1 + ... + c_n w_n) = \lambda Tv$$

Thus $T$ is a linear map from $V$ to $W$.

To prove uniqueness, now suppose that $T \in L(V,W)$ and that $Tv_k = w_k$ for each $k=1,...,n$. Let $c_1,...,c_n \in F$. Then the homogeneity of $T$ implies that $T(c_k v_k) = c_k w_k$ for each $k=1,...,n$. The additivity of $T$ now implies that 

$$T(c_1 v_1 + ... + c_n v_n) = c_1 w_1 + ... + c_n w_n$$

Thus $T$ is uniquely determined on $span(v_1,...,v_n)$ by the equation above. Because $v_1,...,v_n$ is a basis of $V$, this implies that $T$ is uniquely determined on $V$, as desired.


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

Proof:

By additivity, we have

$$T(0) = T(0+0) = T(0) + T(0)$$

Add the additive inverse of $T(0)$ to each side of the equation above to conclude that $T(0) = 0$.



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

Proof:

Because $T$ is a linear map, $T(0) = 0$ by 3.10. Thus $0 \in null T$.

Suppose $u,v \in null T$. Then 

$$T(u+v) = Tu + Tv = 0+0 = 0$$

Hence $u+v \in null T$. Thus $null T$ is closed under addition.

Suppose $u \in null T, \lambda \in F$. Then 

$$T(\lambda u) = \lambda Tu = \lambda 0 = 0$$

Hence $\lambda u \in null T$. Thus $null T$ is closed under scalar multiplication.

We have shown that $null T$ contains 0, and is closed under addition and scalar multiplication. Thus $null T$ is a subspace of $V$ by 1.34.


### 3.14 Definition: injective
A function $T:V \rightarrow W$ is called injective if $Tv = Tu$ implies $u=v$.

### 3.15
Let $T \in L(V,W)$. Then $T$ is injective if and only if $null T = \\{0\\}$. 

Proof:

$\Rightarrow$
First suppose $T$ is injective. We want to prove that $null T = \\{0\\}$. 

We already know that $\\{0\\} \in null T$ by 3.10. 

To prove the inclusion in the other direction, suppose $v \in null T$. Then $Tv = 0 = T(0)$. Because $T$ is injective, the equation implies that $v=0$. 

Thus we can conclude that $null = \\{0\\}$, as desired.

$\Leftarrow$
Now suppose $null = \\{0\\}$. We want to prove that $T$ is injective.

To do this, supopse $u,v \in V$ and $Tu = Tv$. Then $0 = Tu - Tv = T(u-v)$. Thus $u-v \in null T$, which equals $\\{0\\}$. Hence $u-v=0$, which implies that $u=v$. 

Hence $T$ is injective, as desired.


### 3.16 Definition: range
For $T \in L(V,W)$, the range of $T$ is the subset of $W$ consisting of those vectors that are equal to $Tv$ for some $v \in V$: $range T = \\{Tv: v \in V\\}$.

### 3.18 The range is a subspace
If $T \in L(V,W)$, then $range T$ is a subspace of $W$.

Proof:

Supopse $T \in L(V,W)$. Then $T(0) = 0$ by 3.10, which implies that $0 \in range T$.

If $w_1,w_2 \in range T$, then there exist $v_1,v_2 \in V$ such that $Tv_1 = w_1, Tv_2 = w_2$. Thus 

$$T(v_1+v_2) = Tv_1 + Tv_2 = w_1 + w_2$$

Hence $w_1 + w_2 \in range T$. Thus $range T$ is closed under addition.

If $w \in range T, \lambda \in F$, then there exists $v \in V$ such that $Tv = w$. Thus 

$$T(\lambda v) = \lambda Tv = \lambda w$$

Hence $\lambda w \in range T$. Thus $range T$ is closed under scalar multiplication.

We have shown that $range T$ contains 0, and is closed under addition and scalar multiplication. Thus $range T$ is a subspace of $W$ by 1.34.


### 3.19 Definition: surjective
A function $T: V \rightarrow W$ is called surjective if its range equals $W$.

### 3.21 Fundamental theorem of linear maps
Suppose $V$ is finite-dimensional and $T \in L(V,W)$. Then $range T$ is finite-dimensional and $dim V = dim null T + dim range T$.

Proof:

Let $u_1,...,u_m$ be a basis of $null T$; thus $dim null T = m$. The linearly independent list $u_1,...,u_m$ can be extended to a basis $u_1,...,u_m, v_1,...,v_n$ of $V$ by 2.32. Thus $dim V = m + n$. 

To complete the proof, we need to show that $range T$ is finite-dimensional and $dim range T = n$. We will do this by proving that $Tv_1,...,Tv_n$ is a basis of $range T$.

Let $v \in V$. Because $u_1,...,u_m, v_1,...,v_n$ spans $V$, we can write 

$$v = a_1 u_1 + ... + a_m u_m + b_1 v_1 + ... + b_n v_n$$

where the $a$'s and $b$'s are in $F$. Applying $T$ to both sides of the equation, we get

$$Tv = b_1 Tv_1 + ... + b_n Tv_n$$

where the terms of the form $Tu_k$ disappeared because each $u_k$ is in $null T$. The last equation implies that the list $Tv_1,...,Tv_n$ spans $range T$. In particular, $range T$ is finite-dimensional.

To show $Tv_1,...,Tv_n$ is linearly independent, suppose $c_1,...,c_n \in F$ and

$$c_1 Tv_1 + ... + c_n Tv_n = 0$$

Then $T(c_1 v_1 + ... + c_n v_n) = 0$. Hence $c_1 v_1 + ... + c_n v_n \in null T$. 

Because $u_1,...,u_m$ spans $null T$, we can write 

$$c_1 v_1 + ... + c_n v_n = d_1 u_1 + ... + d_m u_m$$

where the $d$'s are in $F$. This equation implies that all the $c$'s and $d$'s are 0 (because $u_1,...,u_m, v_1,...,v_n$ is linearly independent). Thus $Tv_1,...,Tv_n$ is linearly independent and hence is a basis of $range T$, as desired.


### 3.22 Linear map to a lower-dimensional space is not injective
Suppose $V$ and $W$ are finite-dimensional vector spaces such that $dim V > dim W$. Then no linear map from $V$ to $W$ is injective.

Proof:

Let $T \in L(V,W)$. Then 

$$dim null T = dim V - dim range T \geq dim V - dim W > 0$$

where the first equality comes from the fundamental theorem of linear maps (3.21) and the second inequality comes from 2.37. The inequality above states that $dim null T > 0$. This means that $null T$ contains vectors other than 0. Thus $T$ is not injective by 3.15.


### 3.24 Linear map to a higher-dimensional space is not surjective
Suppose $V$ and $W$ are finite-dimensional vector spaces such that $dim V < dim W$. Then no linear map from $V$ to $W$ is surjective.

Proof:

Let $T \in L(V,W)$. Then 

$$dim range T = dim V - dim null T \leq dim V < dim W$$

where the first equality above comes from the fundamental theorem of linear maps (3.21). The inequality above states that $dim range T < dim W$. This means that $range T$ cannot equal $W$. Thus $T$ is not surjective.


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

We know that if $v_1,...,v_n$ is a basis of $V$ and $T: V \rightarrow W$ is linear, then the values of $Tv_1,...,Tv_n$ determine the values of $T$ on arbitrary vectors in $V$ - see the linear map lemma 3.4. As we will soon see, matrices provided an efficient method of recording the values of the $Tv_k$'s in terms of a basis of $W$.

### 3.29 Definition: matrix
Supppose $m, n$ are nonnegative integers. An m-by-n matrix $A$ is a rectangular array of elements of $F$ with m rows and n columns:

$$
\begin{pmatrix}
A_{1,1} & ... & A_{1,n} \\
... & ... & ... \\
A_{m,1} & ... & A_{m,n}
\end{pmatrix}
$$

The notation $A_{j,k}$ denotes the entry on row j, column k of $A$.

### 3.31 Definition: matrix of a linear map
Suppose $T \in L(V,W)$ and $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_m$ is a basis of $W$. The matrix of $T$ with respect to these bases is the m-by-n matrix $M(T)$ whose entries $A_{j,k}$ are defined by

$$Tv_k = A_{1,k} w_1 + ... + A_{m,k} w_m$$

If the bases $v_1,...,v_n$ and $w_1,...,w_m$ are not clear from the context, then the notation $M(T, (v_1,...,v_n), (w_1,...,w_m))$ is used.

### 3.35 
Suppose $S, T \in L(V,W)$. Then $M(S+T) = M(S) + M(T)$.

### 3.38
Suppose $\lambda \in F$ and $T \in L(V,W)$. Then $M(\lambda T) = \lambda M(T)$.

### 3.39 Notation
For m and n positive integers, the set of all m-by-n matrices with entries in $F$ is denoted by $F^{m,n}$. 

### 3.40
Suppose m and n are positive integers. With addition and scalar multiplication defined as above, $F^{m,n}$ is a vector space of dimension mn. 

### 3.43
If $T \in L(U,V)$ and $S \in L(V,W)$, then $M(ST) = M(S)M(T)$.




# 3D Invertibility and Isomorphisms

### 3.59 Definition: Invertible, inverse
- A linear map $T \in L(V,W)$ is called invertible if there exists a linear map $S \in L(W,V)$ such that $ST$ equals the identity operator on $V$ and $TS$ equals the identity operator on $W$.
- A linear map $S \in L(W,V)$ satisfying $ST=I$ and $TS=I$ is called an inverse of $T$ (note that the first $I$ is the identity operator on $V$ and the second $I$ is the identity operator on $W$).

### 3.60 Inverse is unique
An invertible linear map has a unique inverse.

Proof:

Suppose $T \in L(V,W)$ is invertible and $S_1, S_2$ are inverses of $T$. Then 

$$S_1 = S_1 I = S_1 (T S_2) = (S_1 T) S_2 = I S_2 = S_2$$

Thus $S_1 = S_2$.


### 3.61 Notation
If $T$ is invertible, then its inverse is denoted by $T^{-1}$. In other words, if $T \in L(V,W)$ is invertible, then $T^{-1}$ is the unique element of $L(W,V)$ such that $T^{-1} T = I$ and $T T^{-1} = I$.

### 3.63 invertibility $iff$ injectivity and surjectivity
A linear map is invertible if and only if it is injective and surjective.

Proof:

Suppose $T \in L(V,W)$. We need to show that $T$ is invertible if and only if it is injective and surjective.

$\Rightarrow$
First suppose $T$ is invertible. To show that $T$ is injective, suppose $u, v \in V$ and $Tu = Tv$. Then 

$$u = T^{-1} (Tu) = T^{-1} (Tv) = v$$

so $u = v$. Hence $T$ is injective. 

To show that $T$ is surjective, let $w \in W$. Then $w = T (T^{-1} w)$, which shows that $w \in range T$. Thus $range T = W$. Hence $T$ is surjective, completing this direction of the proof.

$\Leftarrow$
Now suppose $T$ is injective and surjective. We want to prove that $T$ is invertible. 

For each $w \in W$, define $S(w)$ to be the unqiue element of $V$ such that $T(S(w)) = w$ (the existence and uniqueness of such an element follow from the injectivity and surjectivity of $T$). The definition of $S$ implies that $TS$ equals the identity operator on $W$.

To prove that $ST$ equals the identity operator on $V$, let $v \in V$. Then

$$T(STv) = TS(Tv) = I Tv = Tv$$

This equation implies that $STv = v$ because $T$ is injective. Thus $ST$ equals the identity on $V$.

To complete the proof, we need to show that $S$ is linear. To do this, suppose $w_1,w_2 \in W$. Then 

$$T(Sw_1 + Sw_2) = TSw_1 + TSw_2 = w_1 + w_2$$

Thus $Sw_1 + Sw_2$ is the unique element of $V$ that $T$ maps to $w_1+w_2$. By the definition of $S$, this implies that $S(w_1+w_) = Sw_1 + Sw_2$. Hence $S$ satisfies the additive property required for linearity.

The proof of homogeneity is similar. Specifically, if $w \in W$ and $\lambda \in F$, then 

$$T(\lambda Sw) = \lambda T (Sw) = \lambda w$$

Thus $\lambda Sw$ is the unique element of $V$ that $T$ maps to $\lambda w$. By the definition of $S$, this implies that $S (\lambda w) = \lambda Sw$. Hence $S$ is linear, as desired.


### 3.65
Suppose that $V$ and $W$ are finite-dimensional vector spaces, $dim V = dim W$, and $T \in L(V,W)$. Then $T$ is invertible $\iff T$ is injective $\iff T$ is surjective.

Proof:

The fundamental theorem of linear maps (3.21) states that 

$$dim V = dim null T + dim range T$$

If $T$ is injective (which by 3.15 is equivalent to the condition $dim null T = 0$), then the equation above implies that 

$$dim range T = dim V - dim null T = dim V = dim W$$

which implies that $T$ is surjective by 2.39.

Conversely, if $T$ is surjective, then

$$dim null T = dim V - dim range T = dim V - dim W = 0$$

which implies that $T$ is injective.

Thus we have shown that $T$ is injective if and only if $T$ is surjective. 

Thus if $T$ is either injective or surjective, then $T$ is both injective and surjective, which implies that $T$ is invertible. Hence $T$ is invertible if and only if $T$ is injective if and only if $T$ is surjective.


### 3.68
Suppose $V$ and $W$ are finite-dimensional vector spaces of the same dimension, $S \in L(W,V)$ and $T \in L(V,W)$. Then $ST=I$ if and only if $TS=I$.

Proof:

First suppose $ST = I$. If $v \in V$ and $Tv = 0$, then $v = Iv = (ST)v = S(Tv) = S(0) = 0$

Thus $T$ is injective by 3.15. Because $V$ and $W$ have the same dimension, this implies that $T$ is invertible by 3.65.

Now multiply both sides of the equation $ST = I$ by $T^{-1}$ on the right, getting $S=T^{-1}$. Thus $TS = T T^{-1} = I$, as desired.

To prove the implication in the other direction, simply reverse the roles of $S$ and $T$ (and $V$ and $W$) in the direction we have already proved, showing that if $TS = I$, then $ST = I$. 


### 3.69 Definition: isomorphism, isomorphic
- An isomorphism is an invertible linear map.
- Two vector spaces are called isomorphic if there is an isomorphism from one vector space onto the other one.

### 3.70
Two finite-dimensional vector spaces over $F$ are isomorhpic if and only if they have the same dimension.

Proof:

$\Rightarrow$
First suppose $V$ and $W$ are isomorphic finite-dimensional vector spaces. Thus there exists an isomorphism $T$ from $V$ onto $W$. 

Because $T$ is invertible, we have $null T = \\{0\\}$ and $range T = W$. Thus $dim null T = 0$ and $dim range T = dim W$. The formula $dim V = dim null T + dim range T$ thus becomes the equation $dim V = dim W$, completing the proof in one direction.

$\Leftarrow$
Suppose $V$ and $W$ are finite-dimensional vector spaces of the same dimension. Let $v_1,...,v_n$ be a basis of $V$ and let $w_1,...,w_n$ be a basis of $W$. Let $T \in L(V,W)$ be defined by 

$$T(c_1 v_1 + ... + c_n v_n) = c_1 w_1 + ... + c_n w_n$$

Then $T$ is a well-defined linear map because $v_1,...,v_n$ is a basis of $V$. Also, $T$ is surjective because $w_1,...,w_n$ spans $W$. Furthermore, $null T = \\{0\\}$ because $w_1,...,w_n$ spans $W$. Thus $T$ is injective. Because $T$ is injective and surjective, it is an isomorphism (by 3.63). Hence $V$ and $W$ are isomorphic.


### 3.71
Suppose $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_m$ is a basis of $W$. Then $M$ is an isomorphism between $L(V,W)$ and $F^{m,n}$

Proof:

We already noted that $M$ is linear. We need to prove that $M$ is injective and surjective. 

We begin with injectivity. If $T \in L(V,W)$ and $M(T) = 0$, then $Tv_k = 0$ for each $k=1,...,n$. Because $v_1,...,v_n$ is a basis of $V$, this implies that $T=0$. Thus $M$ is injective by 3.15.

To prove that $M$ is surjective, suppose $A \in F^{m,n}$. By the linear map lemma 3.4, there exists $T \in L(V,W)$ such that 

$$Tv_k = \sum_{j=1}^m A_{j,k} w_j$$

for each $k=1,...,n$. Because $M(T)$ equals $A$, the range of $M$ equals $F^{m,n}$, as desired.


### 3.72
Suppose $V$ and $W$ are finite-dimensional. Then $L(V,W)$ is finite-dimensional and $dim L(V,W) = (dim V) (dim W)$.

Proof:

The desired result follows from 3.71, 3.70, 3.40.


### 3.73 Definition: matrix of a vector
Suppose $v \in V$ and $v_1,...,v_n$ is a basis of $V$. The matrix of $v$ with respect to this basis is the n-by-1 matrix 

$$M(v) = 
\begin{pmatrix}
b_1 \\
... \\
b_n
\end{pmatrix}
$$

where $b_1,...,b_n$ are scalars such that $v = b_1 v_1 + ... + b_n v_n$.


### 3.76 Linear maps act like matrix multiplication
Suppose $T \in L(V,W)$ and $v \in V$. Suppose $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_m$ is a basis of $W$. Then 

$$M(Tv) = M(T)M(v)$$

Proof:

Suppose $v = b_1 v_1 + ... + b_n v_n$, where $b_1,...,b_n \in F$. Thus 

$$Tv = b_1 Tv_1 + ... + b_n Tv_n$$

Hence 

$$M(Tv) = b_1 M(Tv_1) + ... + b_n M(Tv_n) = b_1 M(T)_{.,1} + ... + b_n M(T)_{.,n} = M(T)M(v)$$


### 3.82
Suppose that $u_1,...,u_n$ and $v_1,...,v_n$ are bases of $V$. Then the matrices 

$$M(I, (u_1,...,u_n), (v_1,...,v_n))$$

$$M(I, (v_1,...,v_n), (u_1,...,u_n))$$

are invertible, and each is the inverse of the other.

### 3.84 Change-of-basis formula
Suppose $T \in L(V)$. Suppose $u_1,...,u_n$ and $v_1,...,v_n$ are bases of $V$. Let $A = M(T, (u_1,...,u_n))$ and $B = M(T, (v_1,...,v_n))$, and $C = M(I, (u_1,...,u_n), (v_1,...,v_n))$. Then $A = C^{-1} B C$.



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


#### (6) Suppose that $W$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $null S = null T$ if and only if there exists an invertible $E \in L(W)$ such that $S=ET$.
$\Leftarrow$

Suppose there exists invertible $E \in L(W)$ such that $S=ET$. 

First let $v \in null S$. Then $Sv = 0$, $ETv = Sv= 0$. Applying $E^{-1}$ to both sides, we have 

$$E^{-1} E T v = E^{-1} 0$$

Thus $Tv = 0$, and $v \in null T$.

Next let $v \in null T$. Then $Tv = 0$, $Sv = ETv = E0 = 0$. Thus $v \in null S$.

Hence we conclude that $null S = null T$.

$\Rightarrow$
Let $w_1,...,w_n$ be a basis of $range T$, and let $Y$ be a complement subspace such that $W = range T \oplus Y$. Let $y_1,...,y_m$ be a basis of $Y$.

Since $w_i \in range T, i=1,...,n$, there exists $v_i \in V$ such that $Tv_i=w_i, i=1,...,n$.

Define $E \in L(W)$ such that

$$Ew_i = Tv_i = Sv_i, i=1,...,n$$

$$Ey_j = y_j, j=1,...,m$$

To show that $E$ is well-defined on $range T$, we want to show that if $Tu_1 = Tu_2$, $u_1, u_2 \in V$, then $Su_1 = Su_2$. 

Assume $Tu_1 = Tu_2$. Then $T(u_1 - u_2) = 0$. $u_1 - u_2 \in null T$. By hypothesis, $u_1 - u_2 \in null S$, and $S(u_1 - u_2) = 0$. Hence $Su_1 = Su_2$, and $E$ is well-defined on $range T$. 

We want to show that $S=ET$.

Let $v \in V$. Then $Tv \in range T$, and we can write 

$$Tv = a_1 w_1 + ... + a_n w_n$$ 

for some $a_1,...,a_n$. Since $w_1 = Tv_1, ..., w_n = Tv_n$ for some $v_1,...,v_n$, 

$$Tv = a_1 Tv_1 + ... + a_n Tv_n = T (a_1 v_1 + ... + a_n v_n)$$

$T(v - (a_1 v_1 + ... + a_n v_n)) = 0$, therefore $v - (a_1 v_1 + ... + a_n v_n) \in null T$. By hypothesis, $v - (a_1 v_1 + ... + a_n v_n) \in null S$. So $S(v - (a_1 v_1 + ... + a_n v_n)) = 0$ and $Sv = S(a_1 v_1 + ... + a_n v_n)$. 

$$ETv = ET(a_1 v_1 + ... + a_n v_n) = a_1 Ew_1 + ... + a_n Ew_n = a_1 Sv_1 + ... + a_n Sv_n = Sv$$

By design, $range E = W$. By 3.65, $E$ is invertible.


#### (7) Suppose that $V$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $range S = range T$ if and only if there exists an invertible $E \in L(V)$ such that $S=TE$.
$\Leftarrow$
Suppose there exists an invertible $E \in L(V)$ such that $S=TE$. 

Let $w \in range S$. Then there exists $v \in V$ such that $Sv = w$. Since $TEv = T(Ev) = Sv = w$, $w \in range T$. 

Let $w \in range T$. Then there exists $v \in V$ such that $Tv = w$. Since $TEv = Sv$, applying $E^{-1}$ gives us $TEE^{-1} v = S E^{-1} v$, $w = Tv = S (E^{-1} v)$. Therefore $w \in range S$. 

Hence we conclude that $range S = range T$.

$\Rightarrow$
Suppose $range S = range T$. Since 

$$dim V = dim null S + dim range S = dim null T + dim range T$$, 

and $dim range S = dim range T$, $dim null S = dim null T$.

Let $s_1,...,s_n$ be a basis of $null S$, let $U$ be a complement subspace that $null S \oplus U = V$, and let $u_1,...,u_m$ be a basis of $U$.

Let $t_1,...,t_n$ be a basis of $null T$, let $U'$ be a complement subspace that $null T \oplus U' = V$, and let $u'_1,...,u'_m$ be a basis of $U'$. 

Since $Su_j \in range S = range T$, $Tx_j = Su_j, j=1,...,m$ for some $x_j \in V$.

Define $E \in L(V)$ such that 

$$E s_i = t_i, i=1,...,n$$

$$E u_j = x_j, j=1,...,m$$

First we want to show that $S=TE$.

$$(TE)(s_i) = T(Es_i) = Tt_i = 0 = S(s_i)$$

$$(TE)(u_j) = T (T|_{U'})^{-1} Su_j = Su_j$$

Next we want to show that $E$ is invertible.

On $null S$, $E$ sends the basis $s_1,...,s_n$ bijectively to $t_1,...,t_n$.

On $U$, $E$ is a composition of two bijective maps, $(T|_{U'})^{-1}$ and $S|_{U}$. Hence it is bijective. 

Since any vector in $V$ decomposes uniquely as a sum from $null S$ and $U$, and $E$ is bijective on both pieces, $E$ is bijective on $V$. Therefore $E$ is invertible.


#### (11) Suppose $V$ is finite-dimensional and $S,T \in L(V)$. Prove that $ST$ is invertible $\iff S$ and $T$ are invertible.
$\Leftarrow$

Suppose $ST$ is invertible. Then $ST$ is injective and surjective. 

We have $range ST = V$. Thus $range S = V$, and $S$ is surjective. 

Assume towards contradiction that $T$ is not surjective. Then $dim range T < dim V$.

Then the restriction $S|_{range T}: range T \rightarrow V$ is not surjective by 3.24. Thus $S(range T) \neq V$. But $range ST = S(range T)$, so $ST$ is not surjective, which is a contradiction. Thus $T$ is surjective.

By 3.65, $S,T$ are invertible.

$\Rightarrow$

Suppose $S,T$ are invertible. Then 

$$ST T^{-1} S^{-1} = I = T^{-1} S^{-1} ST$$

Therefore $ST$ is invertible.


#### (12) Suppose $V$ is finite-dimensional and $S,T,U \in L(V)$ and $STU=I$. Show that $T$ is invertible and that $T^{-1} = US$.
By 3.68,

$$STU = S(TU) = I \Rightarrow (TU)S = T(US) = I$$

$$STU = (ST)U = I \Rightarrow U(ST) = (US)T = I$$

Thus $T$ is invertible and $T^{-1} = US$.


#### (14) Prove or give a counterexample: If $V$ is a finite-dimensional vector space and $R,S,T \in L(V)$ are such that $RST$ is surjective, then $S$ is injective.
By 3.65, $RST$ being surjective implies it is injective and invertible.

Then 

$$dim V = dim null RST + dim range RST = dim range RST$$

Assume towards contradiction that $S$ is not injective. Then $dim null S >= 1$. 

$$dim V = dim null S + dim range S > dim range S$$

Since $dim range S < dim V$, and $dim range ST \leq dim S$, we have $dim range ST < dim V$. Similarly, $dim range RST < dim V$. This is a contradiction to the fact that $RST$ is surjective.

Therefore we conclude $S$ is injective.


#### (15) Suppose $T \in L(V)$ and $v_1,...,v_m$ is a list in $V$ such that $Tv_1,...,Tv_m$ spans $V$. Show that $v_1,...,v_m$ spans $V$.
Let $v \in V$. Since $Tv_1,...,Tv_m$ spans $V$, we can write $v = a_1 Tv_1 + ... + a_m Tv_m$ for some $a_1,...,a_m$. Then $v \in range T$. Therefore $T$ is surjective. By 3.65, $T$ is injective and invertible. 

Since $V = span(Tv_1,...,Tv_m)$, $V = T(span(v_1,...,v_m))$ by linearity. Because $T$ is invertible, $span(v_1,...,v_m) = V$. 




# 3E Duality

### 3.108 Definition: linear functional
A linear functional on $V$ is a linear map from $V$ to $F$. In other words, a linear functional is an element of $L(V, F)$.

### 3.110 Definition: dual space
The dual space of $V$, denoted by $V'$, is the vector space of all linear functionals on $V$. In other words, $V' = L(V, F)$.

### 3.111 
Suppose $V$ is finite-dimensional. Then $V'$ is also finite-dimensional and $dim V' = dim V$.

### 3.112 Definition: dual basis

### 3.114

### 3.116

### 3.118 Definition: dual map

### 3.120

### 3.121 Definition: annihilator

### 3.124

### 3.125

### 3.127

### 3.128

### 3.129

### 3.130

### 3.131

### 3.132

