Linear Algebra Done Right - Chapter 6 Inner Product Spaces <br>
6C Orthogonal Complements and Minimization Problems
================
Rosie Sun <br>
2026-05-15


### 6.46 Definition: orthogonal complement
If $U$ is a subset of $V$, then the orthogonal complement of $U$, denoted by $U^{\perp}$, is the set of all vectors in $V$ that are orthogonal to every vector in $U$:

$$U^{\perp} = \\{v \in V: \langle u,v \rangle=0 for every u \in U\\}$$


### 6.48
(a) If $U$ is a subset of $V$, then $U^{\perp}$ is a subspace of $V$.

(b) $\\{0\\}^{\perp} = V$.

(c) $V^{\perp} = \\{0\\}$.

(d) If $U$ is a subset of $V$, then $U \cap U^{\perp} \subseteq \\{0\\}$.

(e) If $G$ and $H$ are subsets of $V$ and $G \subseteq H$, then $H^{\perp} \subseteq G^{\perp}$.

Proof:

(a) Suppose $U$ is a subset of $V$. Then $\langle u, 0 \rangle = 0$ for every $u \in U$; thus $0 \in U^{\perp}$. 

Suppose $v, w \in U^{\perp}$. If $u \in U$, then 

$$\langle u, v+w \rangle = \langle u,v \rangle + \langle u,w \rangle = 0 + 0 = 0$$

Thus $v + w \in U^{\perp}$, which shows that $U^{\perp}$ is closed under addition.

Similarly, suppose $\lambda \in F$ and $v \in U^{\perp}$. If $u \in U$, then 

$$\langle u, \lambda v \rangle = \overline{\lambda} \langle u, v \rangle = \overline{\lambda} 0 = 0$$

Thus $\lambda v \in U^{\perp}$, which shows that $U^{\perp}$ is closed under scalar multiplication. 

Thus $U^{\perp}$ is a subspace of $V$.

(b) Suppose $v \in V$. Then $\langle 0, v \rangle = 0$, which implies that $v \in \\{0\\}^{\perp}$. Thus $\\{0\\}^{\perp} = V$.

(c) Suppose $v \in V^{\perp}$. Then $\langle v, v \rangle = 0$, which implies that $v = 0$. Thus $V^{\perp} = \\{0\\}$.

(d) Suppose $U$ is a subset of $V$ and $u \in U \cap U^{\perp}$. Then $\langle u, u \rangle = 0$, which implies that $u = 0$. Thus $U \cap U^{\perp} \subseteq \\{0\\}$. 

(e) Suppose $G$ and $H$ are subsets of $V$ and $G \subseteq H$. Suppose $v \in H^{\perp}$. Then $\langle u, v \rangle = 0$ for every $u \in H$, which implies that $\langle u, v \rangle = 0$ for every $u \in G$. Hence $v \in G^{\perp}$. Thus $H^{\perp} \subseteq G^{\perp}$.


### 6.49
Suppose $U$ is a finite-dimensional subspace of $V$. Then 

$$V = U \oplus U^{\perp}$$

Proof:

First we will show that $V = U + U^{\perp}$. To do this, suppose that $v \in V$. Let $e_1,...,e_m$ be an orthonormal basis of $U$. 

We want to write $v$ as the sum of a vector in $U$ and a vector orthogonal to $U$. We have

$$v = (\langle v, e_1 \rangle e_1 + ... + \langle v, e_m \rangle e_m) + (v - \langle v, e_1 \rangle e_1 - ... - \langle v, e_m \rangle e_m)$$

Let $u = \langle v, e_1 \rangle e_1 + ... + \langle v, e_m \rangle e_m$ and $w = v - \langle v, e_1 \rangle e_1 - ... - \langle v, e_m \rangle e_m$. Because each $e_k \in U$, we see that $u \in U$. Because $e_1,...,e_m$ is an orthonormal list, for each $k=1,...,m$, we have 

$$\langle w, e_k \rangle = \langle v, e_k \rangle - \langle  \langle v, e_k \rangle e_k, e_k \rangle = \langle v, e_k \rangle - \langle v, e_k \rangle \langle e_k, e_k \rangle = 0$$

Thus $w$ is orthogonal to every vector in $span(e_1,...,e_m)$, which shows that $w \in U^{\perp}$. 

Hence we have written $v = u + w$, where $u \in U, w, \in U^{\perp}$, completing the proof that $V = U + U^{\perp}$. 

From 6.48, we know that $U \cap U^{\perp} = \\{0\\}$. This implies that $V = U \oplus U^{\perp}$ by 1.46.


### 6.51
Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$. Then

$$dim U^{\perp} = dim V - dim U$$

Proof: 

The formula for $dim U^{\perp}$ follows from 6.49 and 3.94.


### 6.52
Suppose $U$ is a finite-dimensional subspace of $V$. Then

$$U = (U^{\perp})^{\perp}$$

Proof:

$\subseteq$ Suppose $u \in U$. Then $\langle u, w \rangle = 0$ for every $w \in U^{\perp}$. Because $u$ is orthogonal to every vector in $U^{\perp}$, we have $u \in (U^{\perp})^{\perp}$.

$\supseteq$ Suppose $v \in (U^{\perp})^{\perp}$. By 6.49, we can write $v = u + w$, where $u \in U$ and $w \in U^{\perp}$. 

We have $v - u = w \in U^{\perp}$. Because $v \in (U^{\perp})^{\perp}$ and $u \in (U^{\perp})^{\perp}$ (first paragraph), we have $v - u \in (U^{\perp})^{\perp}$. 

Thus $v - u \in U^{\perp} \cap (U^{\perp})^{\perp}$, which implies that $v - u = 0$ by 6.48, which implies that $v - u$, which implies that $v \in U$.

Thus $(U^{\perp})^{\perp} \subseteq U$.


### 6.54
Suppose $U$ is a finite-dimensional subspace of $V$. Then

$$U^{\perp} = \\{0\\} \iff U = V$$

Proof:

First suppose $U^{\perp} = \\{0\\}. Then by 6.52, $U = (U^{\perp})^{\perp} = \\{0\\}^{\perp} = V$, as desired.

Conversely, if $U = V$, then $U^{\perp} = V^{\perp} = \\{0\\}$ by 6.48.


### 6.55 Definition: orthogonal projection
Suppose $U$ is a finite-dimensional subspace of $V$. The orthogonal projection of $V$ onto $U$ is the operator $P_U \in L(V)$ defined as follows: For each $v \in V$, write $v = u + w$, where $u \in U$ and $w \in U^{\perp}$. Then let $P_U v = u$.


### 6.57
Suppose $U$ is a finite-dimensional subspace of $V$. Then

(a) $P_U \in L(V)$;

(b) $P_U u = u$ for every $u \in U$;

(c) $P_U w = 0$ for every $w \in U^{\perp}$;

(d) $range P_U = U$;

(e) $null P_U = U^{\perp}$;

(f) $v - P_U v \in U^{\perp}$ for every $v \in V$;

(g) $P_U^2 = P_U$;

(h) $\lVert P_U v \rVert \leq \lVert v \rVert$ for every $v \in V$;

(i) if $e_1,...,e_m$ is an orthonormal basis of $U$ and $v \in V$, then

$$P_U v = \langle v, e_1 \rangle e_1 + ... + \langle v, e_m \rangle e_m.$$

Proof:

(a) To show that $P_U$ is a linear map on $V$, suppose $v_1, v_2 \in V$. Write $v_1 = u_1 + w_1$ and $v_2 = u_2 + w_2$ with $u_1, u_2 \in U$ and $w_1, w_2 \in U^{\perp}$. Thus $P_U v_1 = u_1$ and $P_U v_2 = u_2$. 

Now $v_1 + v_2 = (u_1 + u_2) + (w_1 + w_2)$ where $(u_1 + u_2) \in U$ and $w_1 + w_2 \in U^{\perp}$. Thus $P_U (v_1 + v_2) = u_1 + u_2 = P_U v_1 + P_U v_2$.

Similarly, suppose $\lambda \in F$ and $v \in V$. Write $v = u + w$, where $u \in U$ and $w \in U^{\perp}$. Then $\lambda v = \lambda u + \lambda w$ with $\lambda u \in U$ and $\lambda w \in U^{\perp}$. Thus $P_U (\lambda v) = \lambda u = \lambda P_U v$. 

Hence $P_U$ is a linear map from $V to V$.

(b) Suppose $u \in U$. We can write $u = u + 0$, where $u \in U$ and $0 \in U^{\perp}$. Thus $P_U u = u$.

(c) Suppose $w \in U^{\perp}$. We can write $w = 0 + w$, where $0 \in U$ and $w \in U^{\perp}$. Thus $P_U w = 0$. 

(d) The definition of $P_U$ implies that $range P_U \subseteq U$. Furthermore, (b) implies that $U \subseteq range P_U$. Thus $range P_U = U$.

(e) The inclusion $U^{\perp} \subseteq null P_U$ follows from (c). To prove the inclusion in the other direction, note that if $v \in null P_U$ then the decomposition must be $v = 0 + v$, where $0 \in U$ and $v \in U^{\perp}$. Thus $null P_U \subseteq U^{\perp}$.

(f) If $v \in V$ and $v = u + w$ with $u \in U$ and $w \in U^{\perp}$, then 

$$v - P_U v = v - u = w \in U^{\perp}$$

(g) If $v \in V$ and $v = u + w$ with $u \in U$ and $w \in U^{\perp}$, then 

$$P_U^2 v = P_U (P_U v) = P_U u = u = P_U v$$

If $v \in V$ and $v = u + w$ with $u \in U$ and $w \in U^{\perp}$, then

$$\lVert P_U v \rVert^2 = \lVert u \rVert^2 \leq \lVert u \rVert^2 + \lVert w \rVert^2 = \lVert v \rVert^2$$

where the last equality comes from the Pythagorean theorem.

(i) The formula for $P_U v$ comes from the proof of 6.49.


### 6.58 Riesz representation theorem revisited
Suppose $V$ is finite-dimensional. For each $v \in V$, define $\phi_v \in V'$ by 

$$\phi_v(u) = \langle u,v \rangle$$

for each $u \in V$. Then $v \rightarrow \phi_v$ is a one-to-one function from $V$ to $V'$.

Proof:

To show that $v \rightarrow \phi_v$ is surjective, suppose $\phi \in V'$. 

If $\phi = 0$, then $\phi = \phi_0$. Thus assume $\phi \neq 0$. Hence $null \phi \neq V$, which implies that $(null \phi)^{\perp} \neq \\{0\\}$ by 6.49.

Let $w \in (null \phi)^{\perp}$ be such that $w \neq 0$. Let 

$$(6.59)  v = \frac{\overline{\phi(w)}}{\lVert w \rVert^2} w$$

Then $v \in (null \phi)^{\perp}$. Also $v \neq 0$ (because $w \neq null \phi$).

Taking the norm of both sides gives

$$\lVert v \rVert = \frac{|\phi(w)|}{\lVert w \rVert}$$

Applying $\phi$ to both sides of 6.59 and then using 6.60, we have

$$\phi(v) = \frac{|\phi(w)|^2}{\lVert w \rVert^2} = \lVert v \rVert^2$$

Now suppose $u \in V$. Using the equation above, we have

$$u = u - \frac{\phi(u)}{\phi(v)} v + \frac{\phi(u)}{\phi(v)} v = (u - \frac{\phi(u)}{\phi(v)} v) + \frac{\phi(u)}{\lVert v \rVert^2} v$$

The term in parentheses above is in $null \phi$ and hence is orthogonal to $v$. Thus taking the inner product of both sides of the equation above with $v$ shows that 

$$\langle u,v \rangle = \frac{\phi(u)}{\lVert v \rVert^2} \langle v,v \rangle = \phi(u)$$

Thus $\phi = \phi_v$, showing that $v \rightarrow \phi_v$ is surjective, as desired.


### 6.59
Suppose $U$ is a finite-dimensional subspace of $V$, $v \in V$, and $u \in U$. Then

$$\lVert v - P_U v \rVert \leq \lVert v - u \rVert$$

Furthermore, the inequality above is an equality if and only if $u = P_U v$.

Proof:

We have 

$$
\begin{aligned}
\lVert v - P_U v \rVert^2 &\leq 
    \lVert v - P_U v \rVert^2 + \lVert P_U v - u \rVert^2 \\
    &= \lVert (v - P_U v) + (P_Uv - u) \rVert^2 \\
    &= \lVert v-u \rVert^2
\end{aligned}
$$

where the first inequality holds because $0 \leq \lVert P_U v - u \rVert^2$, the second inequality comes from the Pythagorean theorem (which applies because $v - P_U v \in U^{\perp}$ by 6.57 and $P_U v - u \in U$). 

Taking square roots gives the desired inequality.

The inequality proved is an equality if and only if $\lVert v - P_U v \rVert^2 = \lVert v - P_U v \rVert^2 + \lVert P_U v - u \rVert^2$, which happens if and only if $\lVert P_U v - u \rVert = 0$, which happens if and only if $u = P_U v$.


### 6.67




## Exercises

### (1) Suppose $v_1,...,v_m \in V$. Prove that $\\{v_1,...,v_m\\}^{\perp} = (span(v_1,...,v_m))^{\perp}$.

$\subseteq$ 
Suppose $v \in \\{v_1, ..., v_m\\}^{\perp}$. Then $\langle v_k, v \rangle = 0$ for $k = 1, ... ,m$. 

Let $a_1, ..., a_m \in F$. Then 

$$
\begin{aligned}
0 &= a_1 \langle v_1, v \rangle + ... + a_m \langle v_m, v \rangle \\
    &= \langle a_1 v_1, v \rangle + ... + \langle a_m v_m, v \rangle \\
    &= \langle a_1 v_1 + ... + a_m v_m, v \rangle
\end{aligned}
$$

Since $a_1,...,a_m$ is arbitrary, $v \in (span(v_1,...,v_m))^{\perp}$.

$\supseteq$ 
Suppose $v \in (span(v_1, ..., v_m))^{\perp}$. Then $\langle a_1 v_1 + ... + a_m v_m, v \rangle = 0$ for any $a_1, ..., a_m \in F$. 

Since $v_k \in span(v_1, ..., v_m)$ for $k=1, ..., m$, we have $\langle v_k, v \rangle = 0$ for $k=1,...,m$. 

Hence $v \in \\{v_1, ..., v_m\\}^{\perp}$.



### (2)


### (3)


### (4)


### (5) Suppose that $V$ is finite-dimensional and $U$ is a subspace of $V$. Show that $P_{U^{\perp}} = I - P_U$, where $I$ is the identity operator on $V$.

Suppose $v \in V$. We can uniquely write $v = u + w$ where $u \in U$ and $w \in U^{\perp}$ by 6.49. Hence 

$$P_{U^{\perp}} v = w = v - u = Iv - P_U v = (I - P_U) v$$



### (6) Suppose $V$ is finite-dimensional and $T \in L(V,W)$. Show that $T = TP_{(null T)^{\perp}} = P_{range T} T$.

First we want to show $T = TP_{(null T)^{\perp}}$.

Suppose $v \in V$. We have $V = null T \oplus (null T)^{\perp}$. We can write $v = v_1 + v_2$, where $v_1 \in null T$ and $v_2 \in (null T)^{\perp}$. Then $P_{(null T)^{\perp}} v = v_2$. We have

$$Tv = T(v_1 + v_2) = Tv_1 + Tv_2 = Tv_2 = T (P_{(null T)^{\perp}} v)$$

Hence $T = TP_{(null T)^{\perp}}$.

Next we want to show $T = P_{range T} T$. 

Since $Tv \in range T, $, by 6.57(b), we have $P_{range T} (Tv) = Tv = (P_{range T} T) v$ for all $v \in V$.

Hence $T = P_{range T} T$.



### (7) Suppose $X$ and $Y$ are finite-dimensional subspaces of $V$. Prove that $P_X P_Y = 0$ if and only if $\langle x, y \rangle=0$ for all $x \in X$ and all $y \in Y$.

$\Rightarrow$
Suppose $P_X P_Y = 0$. Suppose $y \in Y$. Then $P_Y y = y$ by 6.57(b), and 

$$P_X y = P_X (P_Y y) = (P_X P_Y) y = 0$$ 

By 6.57(c), $y \in X^{\perp}$. Thus $Y \subseteq X^{\perp}$. 

Therefore $\langle x, y \rangle = 0$ for every $x \in X, y \in Y$.

$\Leftarrow$
Suppose $\langle x, y \rangle = 0$ for all $x \in X$ and $y \in Y$. Then $Y \subseteq X^{\perp}$. 

Suppose $v \in V$. We can write $v = y + w$ where $y \in Y$ and $w \in Y^{\perp}$. Then $P_Y v = y$. 

$$0 = P_X y = P_X (P_Y v) = (P_X P_Y) v$$ 

Therefore $P_X P_Y = 0$.



### (8) Suppose $U$ is a finite-dimensional subspace of $V$ and $v \in V$. Define a linear functional $\phi: U \rightarrow F$ by $\phi(u) = \langle u, v \rangle$ for all $u \in U$. By the Riesz representation theorem, there exists a unique vector $w \in U$ such that $\phi(u) = \langle u, w \rangle$ for all $u \in U$. Show that $w = P_U v$.

Since $\phi(u) = \langle u, v \rangle = \langle u, w \rangle$ for all $u \in U$, we have $\langle u, v \rangle - \langle u, w \rangle = \langle u, v-w \rangle = 0$ for all $u \in U$. 

Hence $v - w \in U^{\perp}$. 

Because $w \in U$, we can write $v = (v - w) + w$ where $v - w \in U^{\perp}$ and $w \in U$. Therefore we have

$$P_U v = P_U (v-w+w) = P_U (v-w) + P_U w = 0 + w = w$$



### (9) Suppose $V$ is finite-dimensional. Suppose $P \in L(V)$ is such that $P^2 = P$ and every vector in $null P$ is orthogonal to every vector in $range P$. Prove that there exists a subspace $U$ of $V$ such that $P = P_U$.

Let $U = range P$. We will show $P = P_U$ by verifying that, for every $v \in V$, we can write $v = Pv + (v - Pv)$, where $Pv \in U$ and $(v - Pv) \in U^\perp$.

By the definition of range, $Pv \in range P$. Then $Pv \in U$ for every $v \in V$. 

Since $Pv = PPv$ for every $v \in V$ by hypothesis, we have

$$P (v - Pv) = Pv - PPv = 0.$$

Thus $(v - Pv) \in null P$. Since $null P$ is orthogonal to $range P$, $null P \subseteq (range P)^\perp$. Then $(v - Pv) \in U^\perp$ for every $v \in V$.

We have written $v = Pv + (v - Pv)$ where $Pv \in U$ and $(v - Pv) \in U^\perp$. 

From 6.47 the decomposition is unique, hence $P = P_U$.



### (10) Suppose $V$ is finite-dimensional and $P \in L(V)$ is such that $P^2 = P$ and $\lVert Pv \rVert \leq \lVert v \rVert$ for every $v \in V$. Prove that there exists a subspace $U$ of $V$ such that $P = P_U$.



### (11) Suppose $T \in L(V)$ and $U$ is a finite-dimensional subspace of $V$. Prove that $U$ is invariant under $T$ $\iff$ $P_U T P_U = T P_U$.

$\Rightarrow$
Suppose $U$ is invariant under $T$.

Suppose $v \in V$ and $v = u + w, u \in U, w \in U^\perp$. Suppose $Tu = y$. Since $U$ is invariant under $T$, $y \in U$.

Note that since $y \in U$, $P_U y \in U$ by 6.57.

We have

$$
\begin{aligned}
(P_U T P_U)(v) 
    &= P_U T (P_U v) \\
    &= (P_U T) (u) \\
    &= P_U (Tu) \\
    &= P_U y \\
    &= y
\end{aligned}
$$

and

$$(T P_U) (v) = T (P_U v) = Tu = y.$$

Hence $P_U T P_U = T P_U$.

$\Leftarrow$
Suppose $P_U T P_U = T P_U$.

Suppose $u \in U$ and $Tu = y$. 

We have

$$(P_U T P_U) u = (P_U T) u =  P_U y$$

and 

$$(T P_U) u = Tu = y.$$

By hypothesis, $(P_U T P_U) u = (T P_U) u$. Thus $P_U y = y$, which implies that $y \in U$ by 6.57. 

Hence $U$ is invariant under $T$.



### (12) Suppose $V$ is finite-dimensional, $T \in L(V)$, and $U$ is a subspace of $V$. Prove that $U$ and $U^\perp$ are both invariant under $T$ $\iff$ $P_U T = T P_U$.

$\Rightarrow$
Suppose $U$ and $U^\perp$ are both invariant under $T$.

Suppose $v \in V$ and $v = u + w, u \in U, w \in U^\perp$. Since $U$ is invariant under $T$, $Tu \in U$; since $U^\perp$ is invariant under $T$, $Tw \in U^\perp$.

We have

$$
\begin{aligned}
(P_U T)v &= P_U (Tv) \\
    &= P_U (Tu + Tw) \\
    &= P_U (Tu) + P_U (Tw) \\
    &= Tu
\end{aligned}
$$

and 

$$(T P_U)v = T (P_U v) = Tu.$$

Thus $(P_U T)v = (T P_U)v$ for all $v \in V$. Hence $P_U T = T P_U$.

$\Leftarrow$
Suppose $P_U T = T P_U$.

Suppose $u \in U, w \in U^\perp$. We have

$$(P_U T) u = P_U (Tu)$$

and 

$$(T P_U) u = Tu.$$

By hypothesis $P_U (Tu) = Tu$, thus $Tu \in U$ by 6.57. Hence $U$ is invariant under $T$.

Similarly, we have

$$(P_U T) w = P_U (Tw)$$

and 

$$(T P_U) w = T0 = 0.$$

By hypothesis $P_U (Tw) = 0$, thus $Tw \in U^\perp$ by 6.57. Hence $U^\perp$ is invariant under $T$.



### (13) Suppose $F=R$ and $V$ is finite-dimensional. For each $v \in V$, let $\phi_v$ denote the linear functional on $V$ defined by $\phi_v(u) = \langle u,v \rangle$ for all $u \in V$.

#### (a) Show that $v \rightarrow \phi_v$ is an injective linear map from $V$ to $V'$.

Define $T \in L(V, V')$, where $Tv = \phi_v$ where $\phi_v(u) = \langle u,v \rangle$.

First we want to show that $T$ is linear. 

Let $v, w \in V$. Then $T(v+w) = \phi_{v+w}$. 

$$\phi_{v+w} (u) = \langle u, v+w \rangle = \langle u, v \rangle + \langle u, w \rangle = \phi_v(u) + \phi_w(u)$$

Therefore $T(v+w) = Tv + Tw$.

Let $\lambda \in R, v \in V$. Then $T(\lambda v) = \phi_{\lambda v}$.

$$\phi_{\lambda v} (u) = \langle u, \lambda v \rangle = \lambda \langle u, v \rangle = \lambda \phi_v(u)$$

where the second equality follows from the fact that $F = R$ so $\lambda = \overline{\lambda}$.

Therefore $T(\lambda v) = \lambda Tv$. Thus $T$ is a linear map.

To show that $T$ is injective, suppose $Tv = 0$. Then $\phi_v = 0$, and $\phi(u) = \langle u, v \rangle= 0$ for all $u \in V$. Taking $u = v$, we have $\langle v, v \rangle = 0$. Hence $v = 0$. Therefore $null T = \\{0\\}$, and $T$ is injective.


#### (b) Use (a) and a dimension-counting argument to show that $v \rightarrow \phi_v$ is an isomorphism from $V$ to $V'$.

By 3.111, $dim V = dim V'$. From part (a), $T$ is injective, therefore $T$ is surjective by 3.65. Thus it is an isomorphism.



### (14) Suppose that $e_1,...,e_n$ is an orthonormal basis of $V$. Explain why the dual basis (3.112) of $e_1,...,e_n$ is $e_1,...,e_n$ under the identification of $V'$ with $V$ provided by the Riesz representation theorem 6.58.

Define $\phi_k(u) = \langle u, e_k \rangle$ for $k=1,...,n$, for all $u \in V$. 

Since $e_1,...,e_n$ is an orthonormal basis of $V$, $\phi_k(e_j) = \langle e_j, e_k \rangle = \delta_{jk}$. Therefore $\phi_1,...,\phi_n$ satisfies the condition in 3.112 and is the dual basis of $e_1,...,e_n$.

By the Riesz representation, we can associate each $\phi_k$ with $e_k$. Thus the dual basis $\phi_1,...,\phi_n$ corresponds to $e_1,...,e_n$.



### (15) In $R^4$, let $U = span((1,1,0,0), (1,1,1,2))$. Find $u \in U$ such that $\lVert u - (1,2,3,4) \rVert$ is as small as possible.



