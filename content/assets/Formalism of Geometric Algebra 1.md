#mathematics #diary 
# Defining $\mathbb{G}^n$
$\mathbb{G}^n =\cup_{i} \{G_{0}\dots G_{n}\}$ where:
1. There is a product $+$ over $\mathbb{G}^n$
	1. $+(a,b)$[^1]$\in \mathbb{G}^n$
		1. $a+b\in G_{k}$ if $a,b\in G_{k}$
	2. abelian
	3. associative
2. There is a product $g$ over $\mathbb{G}^n$ 
	1. $g(a,b)$[^2]$\in\mathbb{G}^n$
		1. $aa\in G_{0}$ if $a\in G_{1}$
		2. $\zeta a=a\zeta\in G_{1}$ if $a\in G_{1}$ and $\zeta\in G_{0}$
		3. $a_{1}\dots a_{k}\in G_{k}$ if $a_{i}a_{j}+a_{j}a_{i}=0$ and $a_{m}\in G_{1}$
	3. associative
	4. distributive
3. $\cap_{i}G_{i}=0$
	1. $0+a=a$
	2. $0a=0$
4. $G_{0}=\mathbb{R},\mathbb{C},\mathbb{^*R},\space or \space\mathbb{^*C}$[^3], called the scalar field
# Notation
1. *Greek Letters* represent scalars, elements of $G_{0}$
2. *Lower Case Letters* represent vectors, elements of $G_{1}$ 
3. *Capital Letters* represent an arbitrary element of $\mathbb{G}^n$
4. $A_{n}$ is an element of $G_{k}$ where $A$ is any capital letter
# Definitions
1. Grade Selection
	1. $\langle A \rangle_{i} \equiv a_{i}$ for $A=a_{1}+\dots+a_{n}$ where $a_{i}\in G_{i}$
2. Outer Product
	1. $a_{1}|a_{2}|\dots|a_{k} \equiv \langle a_{1}\dots a_{k} \rangle_{k}$ for $a_{i}\in G_{1}$
3. Inner Product
	1. $a_{1}|\dots|a_{k}\cdot  a_{k+1}|\dots|a_{k+s}\equiv \langle a_{1}\dots a_{k+s} \rangle_{|k-s|}$
# Theorems
1. *ab+ba is a scalar*
	1. Suppose $v=(a+b)$
	2. $v^2=\alpha \in G_{0}$
		1. $(a+b)^2=\alpha$
		2. $a^2+b^2+ab +ba=\alpha$
		3. This implies that $ab+ba$ is a scalar because $a^2$ and $b^2$ are required to also be scalars, and both sides of the equation must be scalar to be equal.
	3. $ab=\frac{1}{2}(ab+ba)+\frac{1}{2}(ab-ba)$
		1. $ab=\alpha+\frac{1}{2}(ab-ba)$
2. *Existence of Perpedicular Vectors* [^4]
	1. Suppose that $a$ and $b$ are linearly independent, i.e. $a\neq \alpha b$
	2. Let $A=\sqrt{ b^2 }a$ and $B=\sqrt{ a^2 }b$
	3. Let $R_{\parallel}=\frac{A+B}{2}$ and $R_{\perp}=\frac{A-B}{2}$
	4. $R_{\parallel}R_{\perp}+R_{\perp}R_{\parallel}=0$
		1. 
3. *Projection and Rejection*
	1. Suppose that $a$ and $b$ are linearly independent, i.e. $a\neq \alpha b$
	2. The projection of $a$ onto $b$ is $b_{\parallel}=\frac{1}{2}(b+aba^{-1})$
	3. The rejection of $a$ onto $b$ is $b_{\perp}=\frac{1}{2}(b-aba^{-1})$
	4. $b_{\parallel}$ and $b_{\perp}$ are perpendicular
	5. $b_{\parallel}$ and $a$ are parallel
	6. $b_{\perp}$ and $a$ are perpendicular
4. *$\frac{1}{2}$(ab+ba) is the inner product and $\frac{1}{2}$(ab-ba) is the outer product*
	1. Use the orthogonal expansiono then show that the only scalar part of the equation must be the dot product and the wedge product results in a grade 2 selection.
		1. Decompose b into parallel and perpendicular components of a.
		2. Then show that the 0.5(ab-ba) term is in G_2
5. *$G_{i}$ form vector spaces*
	1. decompose anything in G_i into the multiplication of perpendicular vectors.
	2. Scalar multiplication can be absorbed into one of these vectors, resulting in an element within G_i
6. *There are a maximum of n linearly-independent vectors*
	1. Suppose you have an element in G_n. 
	2. By contradiction, suppose that you have another linearly indepent vector from all of the elements in G_n. If you multiply it by an element by this linearly independent vector, you should get an element in G_n+1, but that is not within G^n which violates the rule that the product is closed.
7. *Equivalent Representations of $A_{k}$*
	1. A_k stays the same under the rotation 
	2. A_k stays the same under one vector having an addition within the span of the other vectors, within its own span
# Operations
# Elucidations on the intent, rules, and geometric insights of GA
# Applications
[^1]: $u+v\equiv +(u,v)$
[^2]: $uv\equiv g(u,v)$
[^3]: The Hyperreal and Hypercomplex numbers
[^4]:We defined two vectors as being perpendicular if $ab+ba=0$. There are many ways of making perpendicular vectors, as will be shown in the next theorem.