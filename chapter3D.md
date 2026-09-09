Linear Algebra Done Right - Chapter 3 Linear Maps <br>
3D Invertibility and Isomorphisms
================
Rosie Sun <br>
2026-04-02


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


### 3.78
Suppose $V$ and $W$ are finite-dimensional and $T \in L(V, W)$. Then $dim range T$ equals the column rank of $M(T)$.

Proof:

Suppose $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_m$ is a basis of $W$. 

The linear map that takes $w \in W$ to $M(w)$ is an isomorphism from $W$ onto the space $F^{m,1}$ of m-by-1 column vectors.

The restriction of this isomorphism to $range T$ (which equals $span (Tv_1,...,Tv_n)$) is an isomorphism from $range T$ onto $span(M(Tv_1),..., M(Tv_n))$. For each $k \in \\{1,...,n\\}$, the m-by-1 matrix $M(Tv_k)$ equals column $k$ of $M(T)$. 

Thus $dim range T = $ the column rank of $M(T)$.


### 3.82
Suppose that $u_1,...,u_n$ and $v_1,...,v_n$ are bases of $V$. Then the matrices 

$$M(I, (u_1,...,u_n), (v_1,...,v_n))$$

$$M(I, (v_1,...,v_n), (u_1,...,u_n))$$

are invertible, and each is the inverse of the other.


### 3.84 Change-of-basis formula
Suppose $T \in L(V)$. Suppose $u_1,...,u_n$ and $v_1,...,v_n$ are bases of $V$. Let $A = M(T, (u_1,...,u_n))$ and $B = M(T, (v_1,...,v_n))$, and $C = M(I, (u_1,...,u_n), (v_1,...,v_n))$. Then $A = C^{-1} B C$.





## Exercises

### (1) Suppose $T \in L(V, W)$ is invertible. Show that $T^{-1}$ is invertible and $(T^{-1})^{-1} = T$.

Since $T$ is invertible, $T T^{-1} = T^{-1} T = I$. 

Now exchange the role of $T$ and $T^{-1}$. Then $T^{-1}$ is invertible and $(T^{-1})^{-1} = T$, and $T$ is the unique inverse of $T^{-1}$ by 3.60.



### (2) Suppose $T \in L(U,V)$ and $S \in L(V,W)$ are both invertible linear maps. Prove that $ST \in L(U,W)$ is invertible and that $(ST)^{-1} = T^{-1} S^{-1}$.

Since $S, T$ are invertible, we have 

$$S S^{-1} = S^{-1} S = I$$ 

and 

$$T T^{-1} = T^{-1} T = I$$

We have 

$$(ST)(T^{-1} S^{-1}) = S (T T^{-1}) S^{-1} = S I S^{-1} = S S^{-1} = I$$

$$(T^{-1} S^{-1})(ST) = T^{-1} (S^{-1} S) T  = T^{-1} I T = T^{-1} T = I$$

Therefore $ST$ is invertible and $T^{-1} S^{-1}$ is the inverse of $ST$.



### (3) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that the following are equivalent. (a) $T$ is invertible. (b) $Tv_1, ..., Tv_n$ is a basis of $V$ for every basis $v_1, ..., v_n$ of $V$. (c) $Tv_1, ..., Tv_n$ is a basis of $V$ for some basis $v_1, ..., v_n$ of $V$.

(a) $\rightarrow$ (b)
Suppose $T$ is invertible. Suppose $v_1, ..., v_n$ is a basis of $V$. Since $Tv_1, ..., Tv_n$ is a list of length $n = dim V$, we just need to show that $Tv_1, ..., Tv_n$ is linearly independent. 

Suppose $a_1 Tv_1 + ... + a_n Tv_n = 0$ for some $a_1, ..., a_n \in F$. Then $T (a_1 v_1 + ... + a_n v_n) = 0$. 

Since $T$ is invertible, $T$ is injective by 3.63, $null T = \\{0\\}$ by 3.15, thus $a_1 v_1 + ... + a_n v_n = 0$. 

Since $v_1, ..., v_n$ is a basis of $V$, $a_1 = ... = a_n = 0$. Hence $Tv_1, ..., Tv_n$ is linearly independent in $V$. Thus (b) holds.

(b) $\rightarrow$ (c) follows immediately.

(c) $\rightarrow$ (a)
Suppose $Tv_1, ..., Tv_n$ is a basis of $V$ for some basis $v_1, ..., v_n$ of $V$. 

Suppose $Tv = 0$ for some $v \in V$. Since $v_1, ..., v_n$ is a basis, $v = b_1 v_1 + ... + b_n v_n$ for some $b_1, ..., b_n \in F$. Then 

$$0 = Tv = T(b_1 v_1 + ... + b_n v_n) = b_1 Tv_1 + ... + b_n Tv_n.$$

Since $Tv_1, ..., Tv_n$ is a basis of $V$, $b_1 = ... = b_n = 0$. Thus $v = 0$, and $T$ is injective by 3.15. Since $V$ is finite-dimensional, $T$ is invertible by 3.65. Thus (a) holds.



### (4) Suppose $V$ is finite-dimensional and $dim V > 1$. Prove that the set of noninvertible linear maps from $V$ to itself is not a subspace of $L(V)$.

We want to show that the set of noninvertible linear maps from $V$ to itself is not closed under addition, and thus not a subspace of $L(V)$.

Suppose $v_1, ..., v_n$ is a basis of $V$, and $T_1, ..., T_n \in L(V)$ such that 

$$T_i v_i = v_i$$

for $i = 1,...,n$ and

$$T_i v_j = 0, j \neq i.$$

Then each $T_i$ is not injective, since $T_i v_j = 0$ and $v_j \neq 0$. Hence each $T_i$ is not invertible. We have

$$(T_1 + ... + T_n) v_i = T_1 v_i + ... + T_n v_i = T_i v_i = v_i$$

for $i = 1, ..., n$.

Thus $T_1 + ... + T_n = I$ which is invertible. 



### (5) Suppose $V$ is finite-dimensional, $U$ is a subspace of $V$, and $S \in L(U, V)$. Prove that there exists an invertible linear map $T$ from $V$ to itself such that $Tu = Su$ for every $u \in U$ if and only if $S$ is injective.

$\Rightarrow$
Suppose there exists an invertible linear map $T$ from $V$ to itself such that $Tu = Su$ for every $u \in U$. 

Assume towards contradiction that $S$ is not injective. Then $Su = 0$ for some $u \neq 0$. By hypothesis $Tu = Su = 0$. Since $T$ is invertible, $T$ is injective by 3.65. Then $u = 0$ by 3.15, which is a contradiction. 

$\Leftarrow$
Suppose $S$ is injective. 

Suppose $u_1, ..., u_m$ is a basis of $U$. We can extend to $u_1, ..., u_m, v_1, ..., v_n$ a basis of $V$ by 2.32. Then $dim V = m + n$. 

Since $S$ is injective, it preserves linear independence (proven in Chapter 3B exercise 9). Thus $Su_1, ..., Su_m$ is linearly independent in $V$. We can extend to $Su_1, ..., Su_m, w_1, ..., w_n$ a basis of $V$, which is well-defined because the length of the list is also $m + n$.

Define $T \in L(V, V)$ such that 

$$Tu_j = Su_j, j = 1,...,m$$

and

$$Tv_i = w_i, i = 1,...,n. $$

$T$ is well-defined by 3.4. Since $T$ and $S$ agree on the basis of $U$, $Tu = Su$ for all $u \in U$. 

Suppose $Tv = 0$ for some $v \in V$. We can write $v = a_1 u_1 + ... + a_m u_m + b_1 v_1 + ... + b_n v_n$ for some $a_1, ..., a_m, b_1, ..., b_n \in F$. Then 

$$0 = Tv = T(a_1 u_1 + ... + a_m u_m + b_1 v_1 + ... + b_n v_n) = a_1 Su_1 + ... + a_m Su_m + b_1 w_1 + ... + b_n w_n. $$

Since $Su_1, ..., Su_m, w_1, ..., w_n$ is a basis of $V$, $a_1 = ... = a_m = b_1 = ... = b_n = 0$. Thus $v = 0$, $null T = \\{0\\}$, and $T$ is injective. 

Since $V$ is finite-dimensional, $T$ is invertible by 3.65.



### (6) Suppose that $W$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $null S = null T$ if and only if there exists an invertible $E \in L(W)$ such that $S = ET$.

$\Leftarrow$
Suppose there exists invertible $E \in L(W)$ such that $S = ET$. 

First suppose $v \in null S$. Then $Sv = 0$ and 

$$(ET)v = Sv = 0.$$ 

Applying $E^{-1}$ to both sides, we have 

$$E^{-1} E T v = E^{-1} 0.$$

Therefore $Tv = 0$. Thus $v \in null T$, and $null S \subseteq null T$.

Next suppose $v \in null T$. Then $Tv = 0$ and 

$$Sv = (ET) v = E(Tv) = E0 = 0.$$ 

Thus $v \in null S$, and $null T \subseteq null S$.

Hence we conclude that $null S = null T$.

$\Rightarrow$
Suppose $null S = null T$.

Define $\Gamma: range T \rightarrow range S$ such that 

$$\Gamma(Tv) = Sv.$$

First we want to show that $\Gamma$ is well-defined.

Suppose $Tv_1 = Tv_2 \in range T$. Then $Tv_1 - Tv_2 = 0$, $T(v_1 - v_2) = 0$. Since $null S = null T$, $S(v_1 - v_2) = 0$ and $Sv_1 = Sv_2$. Thus 

$$\Gamma(Tv_1) = Sv_1 = Sv_2 = \Gamma(Tv_2).$$

Next we want to show that $\Gamma$ is a linear map. 

Suppose $Tv_1, Tv_2 \in range T$. Then 

$$
\begin{aligned}
\Gamma(Tv_1 + Tv_2) &= \Gamma(T(v_1 + v_2)) \\
    &= S(v_1 + v_2) \\
    &= Sv_1 + Sv_2 \\
    &= \Gamma(Tv_1) + \Gamma(Tv_2)
\end{aligned}
$$

Suppose $Tv \in range T, \lambda \in F$. Then 

$$
\begin{aligned}
\Gamma(\lambda (Tv)) &= \Gamma(T(\lambda v)) \\
    &= S(\lambda v) \\
    &= \lambda Sv \\
    &= \lambda \Gamma(Tv)
\end{aligned}
$$

Thus $\Gamma$ satisfies additivity and homogeneity; it is a linear map.

Suppose $\Gamma(Tv) = 0$. Then $\Gamma(Tv) = Sv = 0$. $v \in null S$. Since $null S = null T$, $v \in null T$ and $Tv = 0$. Hence $\Gamma$ is injective.

Since $W$ is finite-dimensional, $range T$ is a subspace of $W$, and $\Gamma \in L(range T, W)$ is injective, by exercise 5 above, there exists an invertible linear map $E \in L(W)$ such that $E(Tv) = \Gamma(Tv) = Sv$ for every $v \in V$. Hence $S = ET$.



### (7) Suppose that $V$ is finite-dimensional and $S,T \in L(V,W)$. Prove that $range S = range T$ if and only if there exists an invertible $E \in L(V)$ such that $S = TE$.

$\Leftarrow$
Suppose there exists an invertible $E \in L(V)$ such that $S = TE$. 

Suppose $w \in range S$. Then there exists $v \in V$ such that $Sv = w$. By hypothesis, 

$$T(Ev) = (TE)v = Sv = w.$$ 

Thus $w \in range T$, and $range S \subseteq range T$. 

Suppose $w \in range T$. Then there exists $v \in V$ such that $Tv = w$. By hypothesis, 

$$S (E^{-1} v) = TE(E^{-1} v) = Tv = w.$$ 

Thus $w \in range S$, and $range T \subseteq range S$.

Hence we conclude that $range S = range T$.

$\Rightarrow$
Suppose $range S = range T$. 

By 3.24 the fundamental theorem of linear maps, we have

$$dim V = dim null S + dim range S$$

and 

$$dim V = dim null T + dim range T.$$ 

By hypothesis $dim range S = dim range T$, thus $dim null S = dim null T$. 

Let $s_1, ..., s_m$ be a basis of $null S$. We can extend to a basis $s_1, ..., s_m, u_1,...,u_n$ of $V$ by 2.32. 

Let $t_1, ..., t_m$ be a basis of $null T$. 

Note that $Su_1, ..., Su_n$ is a basis of $range S$ (proof of 3.21). For $i = 1, ..., n$, since $Su_i \in range S = range T$, there exist $x_i \in V$ such that $Tx_i = Su_i$. Then $Tx_1, ..., Tx_n$ is a basis of $range T$. 

Next we want to show that $t_1, ..., t_m, x_1, ..., x_n$ form a basis of $V$. We will use Chapter 2B exercise 10.

Suppose $a_1 x_1 + ... + a_n x_n = 0$ for some $a_1, ..., a_n \in F$. We have 

$$T(a_1 x_1 + ... + a_n x_n) = a_1 Tx_1 + ... + a_n Tx_n = 0.$$

Then $a_1 = ... = a_n = 0$. Thus $x_1, ..., x_n$ is linearly independent in $V$. Let $X = span(x_1, ..., x_n)$. Then $x_1, ..., x_n$ is a basis of $X$.

Suppose $v \in null T \cap X$. Then $v = b_1 x_1 + ... + b_n x_n$ for some $b_1, ..., b_n \in F$. We have

$$0 = Tv = T(b_1 x_1 + ... + b_n x_n) = b_1 Tx_1 + ... + b_n Tx_n.$$ 

Since $Tx_1, ..., Tx_n$ is a basis, $b_1 = ... = b_n = 0$. Thus $v = 0$ and $null T \cap X = \\{0\\}$. Hence $V = null T \oplus X$. 

Since $t_1, ..., t_m$ is a basis of $null T$ and $x_1, ..., x_n$ is a basis of $X$, $t_1, ..., t_m, x_1, ..., x_n$ form a basis of $V$.

Define $E \in L(V)$ such that 

$$E s_j = t_j, j = 1, ..., m$$

$$E u_i = x_i, i = 1, ..., n$$

By 3.4 $E$ is well-defined.

$E$ is invertible since $E$ maps some basis to a basis (Chapter 3D exercise 3).

Finally we want to show that $S = TE$.

$$(TE)(s_j) = T(Es_j) = Tt_j = 0 = S(s_j), j = 1,...,m,$$

and 

$$(TE)(u_i) = T (Eu_i) = Tx_i = Su_i, i = 1,...,n.$$

Since $TE$ and $S$ agree on each basis vector, $TE = S$.



### (8) Suppose $V$ and $W$ are finite-dimensional and $S, T \in L(V, W)$. Prove that there exist invertible $E_1 \in L(V)$ and $E_2 \in L(W)$ such that $S = E_2 T E_1$ if and only if $dim null S = dim null T$.

$\Rightarrow$
Suppose there exist invertible $E_1 \in L(V)$ and $E_2 \in L(W)$ such that $S = E_2 T E_1$.

Consider $E_1|_{null S}: null S \rightarrow null T$. We want to show that it is an isomorphism from $null S$ onto $null T$.

Suppose $v \in null S$. Then 

$$0 = Sv = E_2 T E_1 v.$$

Since $E_2$ is invertible, it is injective. Then $T E_1 v = 0$, and $E_1 v \in null T$.

The image of $E_1|_{null S}$ lands in $null T$, so $E_1|_{null S}: null S \rightarrow null T$ is well-defined.

Since $E_1$ is invertible, it is injective. Thus the restriction $E_1|_{null S}$ is also injective.

Suppose $w \in null T$. 

Since $E_1: V \rightarrow V$ is surjective, there exists $v \in V$ such that $E_1 v = w$. We have

$$E_2 T E_1 v = E_2 T (E_1 v) = E_2 T w = E_2 (0) = 0 = Sv.$$

Thus $v \in null S$, and $E_1 v = w$. Hence $E_1|_{null S}$ is surjective onto $null T$. 

Since $E_1|_{null S}: null S \rightarrow null T$ is injective and surjective, it is an isomorphism from $null S$ onto $null T$. Hence $null S$ and $null T$ are isomorphic, and $dim null S = dim null T$ by 3.70.

$\Leftarrow$
Suppose $dim null S = dim null T$.

By 3.21 fundamental theorem of linear maps, we have

$$dim V = dim null S + dim range S, $$

$$dim V = dim null T + dim range T.$$

Since $dim null S = dim null T$, $dim range S = dim range T$.

Let $s_1, ..., s_m$ be a basis of $null S$. We can extend to a basis $s_1, ..., s_m, u_1, ..., u_n$ of $V$. Similarly, let $t_1, ..., t_m$ be a basis of $null T$. We can extend to a basis $t_1, ..., t_m, x_1, ..., x_n$ of $V$. 

Define $E_1 \in L(V)$ such that 

$$E_1 s_j = t_j, j = 1, ..., m$$

and

$$E_1 u_i = x_i, i = 1, ..., n.$$

$E_1 \in L(V)$ is invertible since it maps a basis to another basis. 

Note that $Tx_1, ..., Tx_n$ is a basis of $range T$ (proof of 3.21). We can extend to a basis $Tx_1, ..., Tx_n, z_1, ..., z_m$ of $W$. Similarly, $Su_1, ..., Su_n$ is a basis of $range S$. We can extend to a basis $Su_1, ..., Su_n, y_1, ..., y_m$ of $W$.

Define $E_2 \in L(W)$ such that 

$$E_2 Tx_i = Su_i, i = 1, ..., n$$

and

$$E_2 z_j = y_j, j = 1, ..., m.$$

$E_2 \in L(W)$ is invertible since it maps a basis to another basis. 

Suppose $v \in V$. We can write 

$$v = a_1 s_1 + ... + a_m s_m + b_1 u_1 + ... + b_n u_n$$ 

for some $a_1, ..., a_m, b_1, ..., b_n \in F$. Then 

$$
\begin{aligned}
E_2 T E_1 v 
    &= E_2 T E_1 (a_1 s_1 + ... + a_m s_m + b_1 u_1 + ... + b_n u_n) \\
    &= E_2 T (a_1 t_1 + ... + a_m t_m + b_1 x_1 + ... + b_n x_n) \\
    &= 0 + E_2 T(b_1 x_1) + ... + E_2 T(b_n x_n) \\
    &= b_1 Su_1 + ... + b_n Su_n \\
    &= 0 + S(b_1 u_1 + ... + b_n u_n) \\
    &= S(a_1 s_1 + ... + a_m s_m + b_1 u_1 + ... + b_n u_n) \\
    &= Sv
\end{aligned}
$$

Thus $S = E_2 T E_1$.



### (9) Suppose $V$ is finite-dimensional and $T: V \rightarrow W$ is a surjective linear map of $V$ onto $W$. Prove that there is a subspace $U$ of $V$ such that $T|_U$ is an isomorphism of $U$ onto $W$.

Since $V$ is finite-dimensional, $range T$ is finite-dimensional. 

Since $T$ is surjective, $range T = W$. Then $W$ is finite-dimensional had has a basis by 2.31. Let $w_1, ..., w_m$ be a basis of $W$.

Since $T$ is surjective, there exist $v_1, ..., v_m \in V$ such that $Tv_1 = w_1, ..., Tv_m = w_m$.

Suppose $a_1 v_1 + ... + a_m v_m = 0$. Then

$$T(a_1 v_1 + ... + a_m v_m) = a_1 w_1 + ... + a_m w_m = 0.$$

Since $w_1, ..., w_m$ is a basis of $W$ thus linearly independent, $a_1 = ... = a_m = 0$. Thus $v_1, ..., v_m$ is linearly independent in $V$.

Consider $U = span(v_1, ..., v_m)$. $v_1, ..., v_m$ spans $U$ and is linearly independent, therefore it is a basis of $U$. 

Since $T|_U$ maps one basis to another basis, it is an isomorphism of $U$ onto $W$.



### (10)


### (11) Suppose $V$ is finite-dimensional and $S,T \in L(V)$. Prove that $ST$ is invertible $\iff S$ and $T$ are invertible.

$\Rightarrow$
Suppose $ST$ is invertible. Then $ST$ is injective and surjective by 3.63.

Assume towards contradiction that $T$ is not injective. Then $null T \neq \\{0\\}$ and there exists $v \in V$, $v \neq 0$ such that $Tv = 0$ by 3.15. We have 

$$(ST)v = S(Tv) = 0.$$ 

Since $ST$ is injective, $v = 0$ by 3.15, which is a contradiction. 

Thus $T$ is injective, and since $V$ is finite-dimensional, $T$ is surjective and invertible by 3.65.

Assume towards contradiction that $S$ is not injective. Then $null S \neq \\{0\\}$ and there exists $v \in V$, $v \neq 0$ such that $Sv = 0$ by 3.15. Since $T$ is invertible, there exists $u \in V$ such that $Tu = v$. Then $Tu \neq 0$ and $u \neq 0$. We have 

$$Sv = S(Tu) = (ST)u = 0.$$  

Since $ST$ is injective, $u = 0$ by 3.15, which is a contradiction. 

Thus $S$ is injective, and since $V$ is finite-dimensional, $S$ is surjective and invertible by 3.65.

$\Leftarrow$
Suppose $S, T \in L(V)$ are invertible. Then 

$$ST T^{-1} S^{-1} = S S^{-1} = I$$

and 

$$T^{-1} S^{-1} ST = T^{-1} T = I$$

Thus $T^{-1} S^{-1}$ is the inverse of $ST$. Hence $ST$ is invertible.



### (12) Suppose $V$ is finite-dimensional and $S, T, U \in L(V)$ and $STU = I$. Show that $T$ is invertible and that $T^{-1} = US$.

We have $S(TU) = I$ and $(TU)S = I$ by 3.68.

We have $(ST)U = I$ and $U(ST) = I$ by 3.68.

Thus 

$$(TU)S = T(US) = I$$ 

and 

$$U(ST) = (US)T = I.$$

Hence $T$ is invertible and $US$ is the inverse of $T$.



### (14) Prove or give a counterexample: If $V$ is a finite-dimensional vector space and $R,S,T \in L(V)$ are such that $RST$ is surjective, then $S$ is injective.

Since $V$ is finite-dimensional, $RST \in L(V)$ being surjective implies it is injective and invertible by 3.65. 

From exercise 11, $RST$ being invertible implies $R$ is invertible and $ST$ is invertible. And $ST$ being invertible implies $S$ being invertible. 

Hence $S$ is injective.



### (15) Suppose $T \in L(V)$ and $v_1, ..., v_m$ is a list in $V$ such that $Tv_1, ..., Tv_m$ spans $V$. Show that $v_1, ..., v_m$ spans $V$.

Suppose $v \in V$. Since $Tv_1, ..., Tv_m$ spans $V$, $V$ is finite-dimensional. We can write 

$$v = a_1 Tv_1 + ... + a_m Tv_m$$ 

for some $a_1, ..., a_m \in F$. We have 

$$v = a_1 Tv_1 + ... + a_m Tv_m = T(a_1 v_1 + ... + a_m v_m).$$

Thus $v \in range T$, and $V = range T$. Therefore $T$ is surjective. By 3.65, $T$ is injective and invertible. Applying $T^{-1}$, we have 

$$v = (T^{-1} T)v = T^{-1}(a_1 Tv_1 + ... + a_m Tv_m) = a_1 v_1 + ... + a_m v_m.$$

Hence $v_1, ..., v_m$ spans $V$. 



### (17)


### (18)




