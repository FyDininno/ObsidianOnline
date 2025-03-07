```python
import numpy as np

import matplotlib.pyplot as plt

  

# Data: wavelengths in meters and effective index values

wavelength_m = np.array([1.5e-06, 1.50556e-06, 1.51111e-06, 1.51667e-06, 1.52222e-06,

1.52778e-06, 1.53333e-06, 1.53889e-06, 1.54444e-06, 1.55e-06])

n_effective = np.array([2.50215, 2.49606, 2.48996, 2.48386, 2.47774,

2.47163, 2.46543, 2.459, 2.45257, 2.44614])

  

# Convert wavelength to nanometers for plotting

wavelength_nm = wavelength_m * 1e9

  

# 1. Plot: Effective index vs. wavelength

plt.figure(figsize=(6,4))

plt.plot(wavelength_nm, n_effective, 'o-', label=r'$n_{effective}$')

plt.xlabel('Wavelength (nm)')

plt.ylabel(r'$n_{effective}$')

plt.title('Effective Index vs. Wavelength')

plt.grid(True)

plt.legend()

  

# 2. Plot: Group index vs. wavelength

# Group index: n_g = n_effective - lambda * (dn_effective/dlambda)

dn_dlambda = np.gradient(n_effective, wavelength_m) # derivative with respect to wavelength (in meters)

group_index = n_effective - wavelength_m * dn_dlambda

  

plt.figure(figsize=(6,4))

plt.plot(wavelength_nm, group_index, 's-', label=r'$n_g = n_{eff} - \lambda \frac{dn_{eff}}{d\lambda}$')

plt.xlabel('Wavelength (nm)')

plt.ylabel('Group Index')

plt.title('Group Index vs. Wavelength')

plt.grid(True)

plt.legend()

  

# 3. Plot: n_effective vs. beta

# beta = 2*pi*n_effective/lambda

beta = 2 * np.pi * n_effective / wavelength_m

  

plt.figure(figsize=(6,4))

plt.plot(beta, n_effective, 'd-', label=r'$n_{effective}$ vs. $\beta$')

plt.xlabel(r'$\beta$ (rad/m)')

plt.ylabel(r'$n_{effective}$')

plt.title('Effective Index vs. Beta')

plt.grid(True)

plt.legend()

  

plt.show()
```
