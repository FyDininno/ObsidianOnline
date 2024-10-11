# Green's Functions
This blog does it justice if you know that functions are elements of infinite dimensional vector spaces whose basis vectors are spaced $dx$ apart. Think of it this way: for each value of $x$, there is a basis vector associated with that $x$. The coordinate at that basis vector is the value of your function at that $x$ value. The coordinates are spaced $dx$ apart because we assume that the only x values that we consider are spaced $dx$ apart. What you are left with is a vector $f = [f(x_{1}), f(x_{2}), f(x_{3}), \dots]$ where $x_{1},x_{2},$ and $x_{3}$ are spaced $dx$ apart. 

To take the dot product of two functions, you have to do integration. It's just like the ordinary dot product where you multiply each element together, but this time you also multiply by $dx$ to keep the product finite for bounded functions.

The question now is, how does one single out a basis vector? You have to use a delta function which is defined as $\delta(x-x') = \frac{1}{dx}$ for $x-x'=0$, and $0$ otherwise. Then when you take the dot product of your delta function and $f$ and let $x'$ be your desired coordinate, the result after integrating throughout space will be the value of $f$ at $x'$ (or your $f$ coordinate at $x'$)

Once you understand this, we can view any linear differential system like $Lf=b$ like $Ax=b$, where the ladder is a linear system of equations - the only difference being that $f$ and $b$ are infinite dimensional. The Green's function allows us to single out a coordinate from $b$ by acting like a delta function for $Lf$. Each Green's function is specific to an operator $L$. This is where the article takes over:

https://mjmorse.com/blog/greens-function-intuition/