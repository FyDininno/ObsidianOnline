# Straight to the Point
People often wonder what geometric algebra is and can't seem to get a straight answer. Today, I will give you a straight answer.
At the heart of geometric algebra is a rule that allows your algebraic system to become orthogonalizable.
What do I mean by this?
Suppose for a minute that in addition to your usual algebraic system with
$a(b+c) = ab+bc$ ; $(b+c)a = ba + ca$
$(ab)c = a(bc)$
you also have
$ab + ba \in \mathcal{R}$
this introduces a symmetry into your system where if you take any two vectors $u,v$ you can find two new vectors $r,w$ which have the properties $rw + wr = 0$ and $rr = ww = 1$. 
The quantity $ab + ba$ is none other than the dot product (multiplied by two), except now it is formulated in a system where general multiplication between vectors is possible.
The condition ab + ba = $\mathcal{R}$ is also the same as saying that $x^2 \in \mathcal{R}$ because if $x = a +b$, then applying the first two rules makes $a^2+{b^2}+ab+ba \in \mathcal{R}$. Since $a^2$ and $b^2$ are required to be part of $\mathcal{R}$, $ab+ba$ is also necessarily part of $\mathcal{R}$.
By defining the dot product between two vectors $a$ and $b$ to be $a\cdot b \equiv \frac{1}{2}(ab+ba)$, we may now use the Gram-Schmidt orthogonalization method to orthogonalize any system of vectors $v_{1},\dots,v_{n}$, thereby *predicting* the existance of an orthonormal basis for computation.
From these rules follows the the existance of *grades*, elements with dimensions higher than 1 or 0 (vectors or scalars).
It can be shown that any arbitrary product $A=v_{1}v_{2}\dots v_{n}$ can be decomposed into a sum of elements $A_{0}+A_{1}+\dots +A_{n}$ where each $A_{i}$ can be written in the form $a_{1}a_{2}\dots a_{k}$ with each pair of vectors following $a_{i}\cdot a_{j}=\delta_{ij}$ physically manifested as orthogonality, and each element $A_{i}$ cannot be reduced further to a lower or higher grade (all of these claims will be proven). $A_{0}$ represents the product of no vectors (just a scalar), $A_{1}$ represents a single vector, $A_{2}$ represents the product of two orthogonal vectors (a bivector), and so on. 
It should now be noted that this algebra is not commutative with the exception of the scalar, as scalars have inherited commutability with all vectors from the underlying vector space from whence the vectors in our algebra came. Furthermore, the set of scalars, vectors, bivectors, trivectors, and so on, each form their own vector spaces, and the intersection of all of their spaces is the element $0$. Upon a formal definition of the rules, all these aspects will become clear.
As as last note, I have heard people say that GA replaces the use of matrices, and I disagree. Matrices are simply a notation for multiplying systems of equations together, and I frequently use them to prove facts in GA when necessary.
# The formal rules
# What Geometric Algebra can do