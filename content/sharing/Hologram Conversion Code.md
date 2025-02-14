```python
# Import necessary libraries
import os
from PIL import Image
import numpy as np
import matplotlib.pyplot as plt


# ---------------------- 1. File Import and Display ----------------------
# Define the filename (adjust the file path as needed)
reference_directory = '/home/fydininno/Pictures/ECE_184'
filename = 'Part_B_resolution_target.bmp'
file_path = os.path.join(reference_directory, filename)

# Open the image and convert it to a NumPy array of type float64
img = Image.open(file_path).convert('L')  # 'L' mode forces grayscale
cropped_USAF = np.array(img).astype(np.float64)  # Now should be (1024,1024)

# Optionally, if the data is already in the [0,255] range, you can convert it:
cropped_USAF_uint8 = np.clip(cropped_USAF, 0, 255).astype(np.uint8)

# Display the 1024×1024 hologram
plt.figure()
plt.imshow(cropped_USAF_uint8, cmap='gray')
plt.title('Cropped 1024×1024 Hologram (uint8)')
plt.axis('off')
plt.show()


# ---------------------- 2. Parameter Definitions ----------------------
# Define physical parameters (adjust these values as needed)
lambda_val = 632.8e-9   # Wavelength in meters
z = 11.00e-2             # Propagation distance (e.g., 10.10 m)
deltax = 3.10e-6         # Pixel size in meters

# Calculate the wave number
k = 2 * np.pi / lambda_val


# ---------------------- 3. Meshgrid and Phase Factor ----------------------
# Create coordinate arrays for a 1024×1024 image.
crop_size = 1024

# Create spatial coordinate arrays centered at zero
x = np.linspace(-crop_size/2, crop_size/2 - 1, crop_size) * deltax
y = np.linspace(-crop_size/2, crop_size/2 - 1, crop_size) * deltax
X, Y = np.meshgrid(x, y)  # Physical coordinates (meters)

# Compute the phase factor S1
S1 = np.exp((1j * k) / (2 * z) * (X**2 + Y**2))  # Now correctly using physical coordinates


# ---------------------- 4. FFT Reconstruction ----------------------
# Multiply the hologram with S1, apply fftshift before and after fft2
reconstruction = np.fft.fftshift(np.fft.fft2(np.fft.fftshift(cropped_USAF * S1)))
# reconstruction = reconstruction_field * np.conjugate(reconstruction_field)


# ---------------------- 5. Display the Reconstruction ----------------------
# For visualization, we'll display the amplitude (absolute value) of the FFT result.
plt.figure()
plt.imshow(np.abs(reconstruction), cmap='gray')
plt.title('Reconstructed Hologram (Amplitude)')
plt.axis('off')
plt.show()
```
