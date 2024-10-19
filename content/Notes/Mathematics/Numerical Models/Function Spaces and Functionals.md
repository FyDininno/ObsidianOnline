# Function Spaces

I think functions are particularly well represented as vectors. Vectors have coordinates. For example, $[\alpha, \beta, \gamma]$ is a vector, with the order of the vectors corresponding to the x,y,z axis respectively.

In the same way, we can think of a function $f$ as a very large vector, except its value at each coordinate is denoted $f(x_{i})$. Essentially, the coordinate values of $f$ correspond not to the x,y,z axis but an entire space, where each point in the space is an "axis".

$f=[\dots,f(-1),\dots,f(0),\dots,f(1),\dots]$ where the -1, 0, and 1 "axis" are the only ones shown explicitly. We can think of $f(-1)$ as the value of $f$ in the $-1$ "axis."

More generally, we can think of $f$ as equaling $[\dots,f(p_{1}),\dots,f(p_{5}),\dots]$ where $p_{1}$ and $p_{5}$ are elements of some space $V$, possibly having a boundary as it may be embedded in a larger space.

The value of $f$ at each axis is assumed to be in the complex domain for our purposes. 

The space which contains the vectors {$f$} is called a function space.

# Functionals

Functionals are functions on our so-called "vectors" which return a numerical value.

# Euler Lagrange Equation

Let's say that we change our function vector just a little bit $y_{\epsilon}(x) = y_{0}(x) + \epsilon \eta(x)$.

We may see how our functional $I(f)$ changes, where $f$ is within our function space.

Essentially, we have done a sort of directional derivative if we consider $\eta(x)$ to be our direction and $\epsi lon$