# Metrics
### *Definition* 1| A Metric
1. Given a set $X$,
2. A *metric* $d$ is defined on $X$ to be a function which takes $X \times X$ to $\mathbb{R}$, with the following properties:
	1. It is positive $d(x,y) > 0$  $\forall (x,y) \in X$ when $x\neq y$
	2. It is zero under identical arguments $d(x,x) = 0$
	3. It is symmetric $d(x,y) = d(y,x)$
	4. It is minimal $d(x,y) \leq d(x,p) + d(p,y)$  $\forall p \in X$
### *Definition* 2| A Metric Space
1. Given a set $X$
2. and a metric $d$ on the same space,
3. a *metric space* is defined to be the pair $(X,d)$
### *Definition* 3| Two Equivalent Metrics
1. Given two metrics $d_{1}$ and $d_{2}$ on a space $X$,
2. $d_{1}$ and $d_{2}$ are said to be *equivalent* if 
3. there exists two constants $c_{1}$ < $c_{2}$ which are finite and greater than zero such that
4. $c_{1}d_{1}(x,y)\leq d_{2}(x,y)\leq c_{2}d_{1}(x,y)$ $\forall (x,y) \in X$
- This shows that $d_{1}$ and $d_{2}$ scale more or less linearly with each other. If $d_{1}$ is large, then so must be $d_{2}$. If $d_{1}$ is small, then so must $d_{2}.$If $d_{1}$ converges as $y$ get close to $x$, then so must $d_{2}$. On the other hand, the above statements can be said in reverse order because if $d_{2}$ is bounded by $d_{1}$ by being within a range /wrto $d_{1}$, then $d_{1}$ also must be bounded by the value of $d_{2}$ by being required to contain $d_{2}$ in the range $[c_{1}d_{1},c_{2}d_{1}]$. It can then be concluded from the definition via a proof that there exist two constants satisfying the same conditions so that  $a_{1}d_{2}(x,y)\leq d_{1}(x,y)\leq a_{2}d_{2}(x,y)$ $\forall (x,y) \in X$.
### *Definition* 4| Two Equivalent Metric Spaces
1. Suppose you have two metric spaces $(X_{1},d_{1})$ and $(X_{2},d_{2})$.
2. $(X_{1},d_{1})$ and $(X_{2},d_{2})$ are considered to be topologically equivalent if
3. there exists a bijective function $h$ bringing $X_{1}$ to $X_{2}$ so that
4. the distance formula $d_{1}^{'}(x,y) \equiv d_{2}(h(x),h(y))$
5. is equivalent to $d_{1}(x,y)$ by the previous definition.
- An immediate result of this definition is that ($X,d_{1}$) and $(X,d_{2})$ are equivalent metric spaces is $d_{1}$ and $d_{2}$ are equivalent metrics.
- The meaning of such a definition is that $d_{2}$ scales more or less proportionally to $d_{1}$ even though they may exist in different spaces. This is a much stronger condition than having only a homeomorphic map between two metric spaces, which we will see next.
### *Definition* 5| A Continuous Map Between Two Metric Spaces
1. Given two metric spaces $(X_{1},d_{1})$ and $(X_{2},d_{2})$, 
2. a map $f$ taking $X_{1}$ to $X_{2}$ is said to be *continuous* if
3. for all $\epsilon  > 0$ at a point $x\in X_{1}$, there is a $\delta>0$ such that
4. $d_{1}(x,y)<\delta\implies d_{2}(f(x),f(y))<\epsilon$.
5. $f$ is said to be a homeomorphism if it is bijective.
- This says given a point $x$ and its mapping to $f(x)$, there will always be a point $y$ in $X_{1}$ which will bring $f(y)$ arbitrarily close to $f(x)$. This is less powerful than having two equivalent metric spaces because there is no specification of the relationship between $\delta$ and $\epsilon$, whereas the equivalence case says that $\delta = \frac{\epsilon}{c_{2}}$.
# Sequences
### *Definition* 1| A Cauchy Sequence

### *Definition* 2| Completeneess

### *Definition* 3| Connectedness

### *Definition* 4| Compactnedness

### *Definition* 5| The Space of Compact Sets

### *Definition* 6| The Distance Between Subspaces
