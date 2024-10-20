# Function Spaces

I think functions are particularly well represented as vectors. Vectors have coordinates. For example, $[\alpha, \beta, \gamma]$ is a vector, with the order of the vectors corresponding to the x,y,z axis respectively.

In the same way, we can think of a function $f$ as a very large vector, except its value at each coordinate is denoted $f(x_{i})$. Essentially, the coordinate values of $f$ correspond not to the x,y,z axis but an entire space, where each point in the space is an "axis".

$f=[\dots,f(-1),\dots,f(0),\dots,f(1),\dots]$ where the -1, 0, and 1 "axis" are the only ones shown explicitly. We can think of $f(-1)$ as the value of $f$ in the $-1$ "axis."

More generally, we can think of $f$ as equaling $[\dots,f(p_{1}),\dots,f(p_{5}),\dots]$ where $p_{1}$ and $p_{5}$ are elements of some space $V$, possibly having a boundary as it may be embedded in a larger space. We will call $V$ our domain.

The value of $f$ at each axis is assumed to be in the complex domain for our purposes. 

The space which contains the vectors {$f$} is called a function space.

# Functionals

Functionals are functions on our so-called "vectors" which return a numerical value for each point in our domain.
For example, the functional $F(A,B)=A+B$, $A$ and $B$ really depend on our domain $V$, so it should be taken to mean $F(A(x),B(x))=A(x)+B(x)$

## The derivative of a functional

Given the above-mentioned functional, we might try to calculate the derivative with respect to $A$
This would result in $\frac{\partial F}{\partial A} = 1 + \frac{\partial B}{\partial A} = 1+0=1$.

When we talk about the derivative definition of a functional, we treat all inputs as completely independent fixed inputs to F, so $\frac{\partial B}{\partial A} = 0$. This alternative type of derivative is called a variation. The specific definition for the functional derivative is as follows:

![[Pasted image 20241018223658.png]]

Notice how the right hand side looks like a normal derivative, a difference quotient that mentions nothing about the domain of the function $f$. This allows us to take partials of the functional like we did earlier and treat the inputs as completely independent.
# Euler Lagrange Equation

Let's say that we change our function vector just a little bit $y_{\epsilon}(x) = y_{0}(x) + \epsilon \eta(x)$.

We may see how our functional $I(f)$ changes, where $f$ is within our function space.

Essentially, we have done a sort of directional derivative if we consider $\eta(x)$ to be our direction and $\epsilon$ to be our perturbation or "variation" constant.
$$I[y_\epsilon] = I[y] + \epsilon \int_{x_1}^{x_2} \left( \frac{\partial F}{\partial y} \eta(x) + \frac{\partial F}{\partial y'} \eta'(x) \right) \, dx + O(\epsilon^2)$$
Is the result of the equation after a Taylor expansion is done around epsilon equals zero, and where F is our functional.
