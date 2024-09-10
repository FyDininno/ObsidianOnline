The keystone of geometric algebra is that any number of vectors can be multiplied associatively and distributively together. The one rule about this geometric product is that a vector multiplied by itself must produce a scalar and that scalars commute with everything.

The result is that the dot product and wedge product can be constructed between two multivectors, which are products of an arbitrary number of vectors, via the geometric product. The wedge product of two multivectors is defined to be the highest dimensional element of their geometric product while the dot product is defined to be the lowest non-zero element of their geometric product.

As such, the equation for the dot product between two one dimensional vectors can be deduced to be $\frac{1}{2}(ab+ba)$ and the wedge product is found to be $\frac{1}{2}(ab-ba)$. Why is this?
Suppose we have two vectors $x$ and $y$. If 


Two vectors in a two dimensional vector space can always be found which have a dot product of zero. For example, given two arbitrary, linearly independent vectors $x$ and $y$, we can let $e_{1} = \frac{x+y}{2}$ and $e_{2} = \frac{x-y}{2}$  be two resultant vectors. Graphically, these two vectors look perpendicular to each other. Algebraically, these two have a dot product of zero. 
Notice that  $\frac{1}{2}(ab+ba) + \frac{1}{2}(ab-ba) = ab$. If we multiply $e_{1}$ and $e_{2}$ together, and we know that their dot product $\frac{1}{2}(e_{1}e_{2}+e_{2}e_{1})$ is zero, then it must be true that $\frac{1}{2}(e_{1}e_{2}-e_{2}e_{1}) = e_{1}e_{2}$ which simplifies to $e_{1}e_{2} = -e_{2}e_{1}$. So, now we see why it makes sense to define the dot and wedge product in this way, for if one uses an orthogonal basis such as $e_{1}$ and $e_{2}$ then their wedge product produces a two dimensional element and their dot product will produce a scalar.

This space of multivectors is called the Geometric Algebra of an n-dimensional vector space, which can have a mixed signature. 