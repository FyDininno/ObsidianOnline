# Simulational Section
## Effective Index vs Length
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
## N-effective Plots
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
## Lossless MZI
```python
import numpy as np

import matplotlib.pyplot as plt

  

# MZI Transfer function - Loss-less case

lambda_center = 1.525e-6 # Center wavelength [m]

lambda_min = 1.50e-6 # Minimum wavelength [m]

lambda_max = 1.55e-6 # Maximum wavelength [m]

step_size = 1e-11 # Wavelength step size [m]

  

# Create wavelength array from lambda_min to lambda_max (inclusive)

wavelength = np.arange(lambda_min, lambda_max + step_size, step_size)

  

# Effective index parameters (from Lumerical Mode file)

neff0 = 2.474686

dnbydlambda = -0.001327 * 1e9 # dispersion coefficient (1/nm)

  

# Calculate the effective index over the wavelength range

neff = neff0 + (wavelength - lambda_min) * dnbydlambda

  

# Calculate the group index for the Mach-Zehnder

ng = neff - wavelength * dnbydlambda

  

# Calculate the propagation constant beta

beta = 2 * np.pi * neff / wavelength

  

# Free Spectral Range (FSR) in meters for the MZI

FSR_mzi = 5.66e-9

  

# Calculate the path length difference (DeltaL)

# In the original script, ng(1) is the first element of ng

deltaL = lambda_center**2 / (ng[0] * FSR_mzi)

  

# Calculate the transmission (loss-less case)

transm = 0.5 * (1 + np.cos(beta * deltaL))

transdb = 10 * np.log10(transm)

  

# Plot the transmission spectrum

plt.plot(wavelength * 1e6, transdb)

plt.xlabel('Wavelength (µm)')

plt.ylabel('Transmission (dB)')

plt.title('Transmission Spectra of an MZI without loss')

plt.xlim(lambda_min * 1e6, lambda_max * 1e6)

plt.ylim(-100, 0)

plt.show()
```
## Lossy MZI
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

  

# --------- 1. Fit: n_effective vs. Wavelength ---------

# Using a quadratic fit (degree=2)

coeffs = np.polyfit(wavelength_m, n_effective, 2)

poly_fit = np.poly1d(coeffs)

  

# Generate a dense wavelength array for a smooth fitted curve

wavelength_dense = np.linspace(wavelength_m[0], wavelength_m[-1], 200)

n_fit_dense = poly_fit(wavelength_dense)

  

plt.figure(figsize=(6,4))

plt.plot(wavelength_nm, n_effective, 'o', label='Data')

plt.plot(wavelength_dense * 1e9, n_fit_dense, '-', label='Quadratic Fit')

plt.xlabel('Wavelength (nm)')

plt.ylabel('Effective Index')

plt.title('Effective Index vs. Wavelength')

plt.grid(True)

plt.legend()

  

# --------- 2. Fit: Group Index vs. Wavelength ---------

# Group index is defined as n_g = n_eff - lambda*(dn_eff/dlambda)

# Compute the derivative of the fitted polynomial

poly_deriv = np.polyder(poly_fit)

dn_dlambda_dense = poly_deriv(wavelength_dense)

group_index_dense = n_fit_dense - wavelength_dense * dn_dlambda_dense

  

plt.figure(figsize=(6,4))

plt.plot(wavelength_dense * 1e9, group_index_dense, '-', label='Group Index (from fit)')

plt.xlabel('Wavelength (nm)')

plt.ylabel('Group Index')

plt.title('Group Index vs. Wavelength')

plt.grid(True)

plt.legend()

  

# --------- 3. Fit: n_effective vs. Beta ---------

# beta = 2*pi*n_effective/lambda

# We generate data for lambda ranging from 1500nm to 1550nm.

wavelength_range = np.linspace(1.5e-06, 1.55e-06, 200)

n_fit_range = poly_fit(wavelength_range)

beta_range = 2 * np.pi * n_fit_range / wavelength_range

  

# Although beta is computed nonlinearly, plotting n_effective vs. beta

# should yield a nearly linear trend over the narrow range.

# We perform a linear fit on this relation.

lin_coeffs = np.polyfit(beta_range, n_fit_range, 1)

n_lin_fit = np.polyval(lin_coeffs, beta_range)

  

plt.figure(figsize=(6,4))

plt.plot(beta_range, n_fit_range, 'o', label='Data from fit')

plt.plot(beta_range, n_lin_fit, '-', label='Linear Fit')

plt.xlabel(r'$\beta$ (rad/m)')

plt.ylabel('Effective Index')

plt.title('Effective Index vs. Beta')

plt.grid(True)

plt.legend()

  

plt.show()
```
# Experimental Section
## Effective and Group Indices
```python
import numpy as np

import matplotlib.pyplot as plt

  

# Data arrays

wavelength = np.array([1460, 1480, 1500, 1510, 1530, 1550, 1570, 1590, 1620, 1650, 1700])

Neff = np.array([2.545824, 2.524036, 2.502157, 2.491185, 2.469179, 2.446138, 2.422945, 2.399711, 2.365453, 2.331429, 2.274536])

Ng = np.array([4.132918, 4.139832, 4.146333, 4.149524, 4.156473, 4.241871, 4.245278, 4.248318, 4.200209, 4.20511, 4.215425])

  

# Create the plot

plt.figure(figsize=(8,6))

plt.plot(wavelength, Neff, 'bo-', label='Effective Index (Neff)')

plt.plot(wavelength, Ng, 'ro-', label='Group Index (Ng)')

plt.xlabel('Wavelength (nm)')

plt.ylabel('Index')

plt.title('Effective and Group Index vs. Wavelength')

plt.grid(True)

plt.legend()

plt.show()
```
## Wavelength vs Power
```python
import numpy as np

import matplotlib.pyplot as plt

  

# Given data

voltage = np.array([0, 0.5, 1, 1.5, 2, 2.5, 3, 3.5, 4, 4.45])

current_mA = np.array([0, 2, 3, 5, 7, 9, 11, 13, 15, 17])

wavelength = np.array([1542.16, 1542.16, 1542.05, 1542.0, 1541.54,

1541.021, 1540.54, 1539.12, 1539.095, 1538.441])

  

# Calculate power as voltage * current (V*mA)

power = voltage * current_mA

  

# Fit a quadratic polynomial to the data: wavelength as a function of power

poly_coeffs = np.polyfit(power, wavelength, 2)

poly_fit = np.poly1d(poly_coeffs)

  

# Create a dense power array for smooth plotting

power_dense = np.linspace(power.min(), power.max(), 200)

wavelength_fit = poly_fit(power_dense)

  

# Compute the derivative of the fitted polynomial: d(wavelength)/d(power)

poly_deriv = np.polyder(poly_fit)

tunability = poly_deriv(power_dense)

  

# Plot the wavelength vs. power along with the fitted curve and its derivative

fig, (ax1, ax2) = plt.subplots(2, 1, sharex=True, figsize=(7,8))

  

# Upper plot: wavelength vs. power with fit

ax1.plot(power, wavelength, 'o', label='Data')

ax1.plot(power_dense, wavelength_fit, '-', label='Quadratic Fit')

ax1.set_ylabel('Wavelength (nm)')

ax1.set_title('Wavelength vs. Power and its Derivative (Tunability)')

ax1.legend()

ax1.grid(True)

  

# Lower plot: derivative (tunability) vs. power

ax2.plot(power_dense, tunability, 'r-', label='d(Wavelength)/d(Power)')

ax2.set_xlabel('Power (V·mA)')

ax2.set_ylabel('Tunability (nm per V·mA)')

ax2.legend()

ax2.grid(True)

  

plt.tight_layout(rect=[0, 0, 1, 0.96])

plt.show()
```
## Response vs Squarewave Wavelength,Frequency 
```python
import numpy as np

import matplotlib.pyplot as plt

  

# Provided data: frequency (Hz) and amplitude (mV)

frequency = np.array([200, 500, 1000, 1500, 2000, 2500, 3000, 3500, 4000, 4500])

amplitude = np.array([400, 364, 336, 332, 288, 260, 248, 216, 200, 180])

  

# Compute squarewave period from frequency (T = 1/f) and convert to milliseconds.

period_s = 1 / frequency

period_ms = period_s * 1e3

  

# -------- Plot 1: Amplitude vs. Squarewave Wavelength (Period in ms) --------

plt.figure(figsize=(6,4))

plt.plot(period_ms, amplitude, 'o-', label='Data (Period)')

plt.xlabel('Squarewave "Wavelength" (Period in ms)')

plt.ylabel('Amplitude (mV)')

plt.title('MZI Interferometer Readout vs. Squarewave Wavelength')

plt.grid(True)

plt.legend()

plt.show()

  

# -------- Plot 2: Amplitude vs. Frequency (Hz) --------

plt.figure(figsize=(6,4))

plt.plot(frequency, amplitude, 'o-', label='Data (Frequency)')

plt.xlabel('Frequency (Hz)')

plt.ylabel('Amplitude (mV)')

plt.title('MZI Interferometer Readout vs. Frequency')

plt.grid(True)

plt.legend()

plt.show()
```