# Example Problem
## Sturm-Louisville Equation 
One important equation in physical models is the Sturm-Louisville Equation: $$\frac{d}{dx} \left( p(x) \frac{dy}{dx} \right) + q(x)y = f(x)$$
This says that some weighted function $y$ plus its weighted derivative is equal to some term on the right, sometimes indicating an eigenvalue to the system.

Usually, the starting and end points for a 1D system would be x=0 and x=pi. This is not a dynamic problem, it is a steady state problem in which this equation arises.

## Boundary Conditions
Dirichlet boundary conditions are imposed when one knows the value of the target function along its boundary.

In our example, we let u(0)=0.

# Four Types of Solutions

## Pure Mathematics
We view the equation as a linear problem, where the derivatives act as linear operators.  $$Lu-f=0$$
We find all $f$ st there is a $u$ which satisfies the equation above. Then, we count the problem as solved.
What we can do 