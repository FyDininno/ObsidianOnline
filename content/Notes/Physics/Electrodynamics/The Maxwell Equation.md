To view the Maxwell Equation, the units of the fields must first be understood.

We know by experiment the formula for the electric field. $\epsilon$ appears in the denominator. When we follow Gauss' Law and integrate the field around the sphere encapsulating the charge, we get that the integral equals $\frac{q}{\epsilon}$. This implies that out of all the constants in the electric field formula, $\epsilon$ is of relevance. In fact, because it appears in the denominator, we call it the permittivity of free space, because it reduces the strength of the field.

If we multiply both sides of the Gauss Equation by $\epsilon$ then we get the integrand to be $\epsilon \mathcal{E}$. Therefore $\epsilon \mathcal{E} \cdot ds = dq$  means that $\epsilon \mathcal{E}$ represents the electric field per unit area. Remember, $\mathcal{E}=\hat{R}\frac{1}{4\pi R^2} \frac{1}{\epsilon} \left[ \frac{V}{m} \right]$ so $\epsilon$ in a way turns charge per unit area at a point into field/voltage change at a point.

$\mathcal{D}=\epsilon\mathcal{E} \left[ \frac{C}{m^2} \right]$
$\mathcal{B}=u\mathcal{H} \left[ \frac{W}{m^2} \right]$

represent Coloumbs per meter squared and Webers per meter squared respectively (one Tesla). 

On the other hand 

$\mathcal{E} \left[ \frac{V}{m} \right]$
$\mathcal{H} \left[ \frac{A}{m} \right]$

represent Volts per meter and Amperes per meter.

We then have 

$p \left[ \frac{C}{m^3} \right]$ 
$p_{m} \left[ \frac{W}{m^3} \right]$

represent Coloumbs per meter cubed and Webers per meter cubed.

And finally we have

$J \left[ \frac{A}{m^2} \right]$
$M \left[ \frac{V}{m^2} \right]$

The current density represents the change in electrons per unit time through a cross section, and the magnetization represents the change in dipole moments per unit length through a cross sectional area.

Whatever interpretation you must give to these to make sense at the moment, they must be considered foremost within the solution to the Maxwell Equation in their interpretations.

## The Maxwell Equation

$(\nabla +\frac{1}{c} \partial_{t})(\mathcal{E}+\eta \mathcal{H}^*)=\eta (\rho - \mathcal{J}) + (c\rho_{m} - \mathcal{M})^*$

Here, $c$ represents the group velocity of the media and $\eta$ represents the impedance of the media. The impedance of the represents how fast a charge will move through a medium. The group velocity represents how fast the wave will travel through the medium or free space.

$\eta = \sqrt{ \frac{\mu}{\epsilon} } \left[ \Omega = \frac{V}{A} \right]$
$c = \frac{1}{\sqrt{ \mu \epsilon }} \left[ \frac{m}{s} \right]$

$\epsilon = \epsilon_{r}\epsilon_{0} \left[ \frac{F}{m} \right]$
$\mu = \mu_{r}\mu_{0} \left[ \frac{H}{m} \right]$

Epsilon, the permittivity of the medium, is a constant that relates charge present and the flux that the charge creates. Mu, the permeability of the medium, is a constant relating the magnetization present and the charge it creates in the material.

On the left and right hand sides, our variables are:

$F = \mathcal{E}+\eta \mathcal{H}^*$
$J = \eta (\rho - \mathcal{J}) + (c\rho_{m} - \mathcal{M})^*$

These two variables represent the fields and current densities respectively. The Maxwell Equation says that the gradient of the field profile and the movement of the field itself is the current profile. Remember that the gradient of a scalar function produces a vector. The gradient of any field produces two elements of grade higher and lower than the field being acted on.

Notice that the gradient of the fields determines the currents, and that the time derivative of the field equals the currents. This means the field acts on itself to travel in the right conditions. This gives rise to the wave equation in free space when the entire right hand side is zero (see Geometric Algebra for Electrical Engineers, Equation 3.17 and Theorem 3.3, by Peeter Joot).