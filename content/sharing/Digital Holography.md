```python
# Import necessary libraries
import os
from PIL import Image
import numpy as np
import matplotlib.pyplot as plt
```

```python
# ---------------------- 1. File Import and Display ----------------------
# Define the filename (adjust the file path as needed)
reference_directory = '/home/fydininno/Pictures/ECE_184/Lab_5'
filename = 'ucsd_logo.png'
file_path = os.path.join(reference_directory, filename)

# Open the image and convert it to a NumPy array of type float64
img = Image.open(file_path).convert('L')  # 'L' mode forces grayscale
resized_USAF = np.array(img).astype(np.float64)  # Now should be (128,128)

# Normalize the image to range [0,1]
resized_USAF = (resized_USAF - np.min(resized_USAF)) / (np.max(resized_USAF) - np.min(resized_USAF))

# Ensure values greater than 1 are set to 1
scale_factor = 1.5
scaled_hologram = np.clip(resized_USAF*scale_factor, 0, 1) # reveals the correct details

# Generate a random complex phase shift for each element in the grid
random_phases = np.exp(1j * 2 * np.pi * np.random.rand(*resized_USAF.shape))
complex_hologram = scaled_hologram * random_phases

# Display the magnitude of the complex hologram
plt.figure()
plt.imshow(np.abs(complex_hologram), cmap='gray')
plt.title('Magnitude of Normalized Complex Hologram')
plt.axis('off')
plt.show()

# Display the phase of the complex hologram
plt.figure()
plt.imshow(np.angle(complex_hologram), cmap='twilight')
plt.title('Phase of Normalized Complex Hologram')
plt.axis('off')
plt.show()

```

```python
# ---------------------- 3. Perform Lee Encoding ----------------------
# Define the four basis vectors for encoding
basis_vectors = [np.exp(1j * k * np.pi / 2) for k in range(4)]

# Compute projections onto the basis vectors
A1 = np.maximum(0, np.real(hologram_plane))
A2 = np.maximum(0, np.imag(hologram_plane))
A3 = np.maximum(0, -np.real(hologram_plane))
A4 = np.maximum(0, -np.imag(hologram_plane))

# Expand the hologram from 128x128 to 128x512
expanded_hologram = np.zeros((128, 512))
expanded_hologram[:, 0::4] = A1
expanded_hologram[:, 1::4] = A2
expanded_hologram[:, 2::4] = A3
expanded_hologram[:, 3::4] = A4

# Display the encoded hologram
plt.figure()
plt.imshow(expanded_hologram, cmap='gray')
plt.title('Expanded Hologram (Binary Representation)')
plt.axis('off')
plt.show()

# Expand the hologram from 512x128 to 512x512
binary_hologram = np.zeros((512, 512))

# Assign each value a binary representation based on thresholds
thresholds = [0.2, 0.4, 0.6, 0.8, 1.0]
for i in range(128):
    for j in range(512):
        value = expanded_hologram[i, j]
        if value < 0.2:
            binary_hologram[i*4:i*4+4, j] = [0, 0, 0, 0]
        elif value < 0.4:
            binary_hologram[i*4:i*4+4, j] = [1, 0, 0, 0]
        elif value < 0.6:
            binary_hologram[i*4:i*4+4, j] = [1, 1, 0, 0]
        elif value < 0.8:
            binary_hologram[i*4:i*4+4, j] = [1, 1, 1, 0]
        else:
            binary_hologram[i*4:i*4+4, j] = [1, 1, 1, 1]

# Display the encoded hologram
plt.figure()
plt.imshow(binary_hologram, cmap='gray')
plt.title('Lee Encoded Hologram (Binary Representation)')
plt.axis('off')
plt.show()
```

```python
# ---------------------- 4. Perform Reconstruction ----------------------
# Perform the inverse FFT
reconstructed_hologram = np.fft.ifftshift(np.fft.ifft2(np.fft.ifftshift(binary_hologram)))

# Take the absolute value
magnitude_hologram = np.abs(reconstructed_hologram)

# Clip the delta points
capped_hologram = np.clip(magnitude_hologram, 0, 1)

# Scale and clip the final image
final_scaling_factor = 1.5 * 10**3  # Adjust this factor as needed
capped_hologram *= final_scaling_factor
capped_hologram = np.clip(capped_hologram, 0, 1)

# Display the log-magnitude of the reconstructed hologram
plt.figure()
plt.imshow(capped_hologram, cmap='gray')
plt.title('Final Scaled Magnitude of Reconstructed Hologram')
plt.axis('off')
plt.show()
```