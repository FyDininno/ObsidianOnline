Tensors are essentially a way to take two or more vector spaces, irrespective of their elements, and turn them into a tensor vector space. A tensor vector space is a vector space where the bases are tensor products of the basis vectors in the original vector space. For example, if we have three vector spaces $X,H,E$ with bases vectors $[x_{1},x_{2}], [h_{1}], [e_{1},e_{2},e_{3}]$, then one such tensor basis would be $x_{1} \otimes h_{1} \otimes e_{2}$. The *rank* of a tensor is how many of these basis tensor vectors you need to specify the entire tensor vector space. 

The tensor product is multilinear.

Tensors are important because they are the "basic" multilinear map. They are like a template for all multilinear maps. Any multilinear map from the Cartesian product of two or more vector spaces to another vector space can be viewed instead as first a map from the Cartesian product to a tensor space and then a map from the tensor space to the final space. The first mapping gives the Cartesian product multilinearity, and the second shows how a linear map would act on the multilinear basis vectors.

The Tensor Product: https://www.math3ma.com/blog/the-tensor-product-demystified
The Category Theory of Tensors: https://www.jeremykun.com/2014/01/17/how-to-conquer-tensorphobia/

In the spirit of multilinear product combinations of basis vectors, tensors can be thought of as nested lists. Matrices are rank 2 tensors because they are a list of lists. Rank three tensors can be thought of as a list of l