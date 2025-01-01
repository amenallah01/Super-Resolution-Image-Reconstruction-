# Image Super-Resolution Reconstruction

This repository contains a comprehensive implementation of image super-resolution techniques aimed at reconstructing high-resolution images from a set of low-resolution images. The project is part of a practical course on Image and Signal Processing at Université Paris-Saclay.

## Objective

The primary goal is to develop methods for reconstructing super-resolved images, which have a higher resolution than that of the original sensor, using a series of low-resolution images. The initial approach utilizes basic techniques involving spatial shifts and successive additions of images to enhance resolution. Later phases will focus on improving preliminary results through advanced regularization techniques, including Wiener filtering and gradient descent methods.

## Key Features

- **Spatial Shift Estimation:** Accurately estimates the spatial shifts between low-resolution images to ensure proper alignment.
- **Shift and Add Method:** Implements a straightforward technique to combine aligned images into a single high-resolution output.
- **Wiener Filter Deconvolution:** Applies advanced filtering techniques to enhance the quality of the reconstructed image.
- **MATLAB Implementation:** All algorithms and methodologies are implemented in MATLAB, facilitating easy access for educational purposes.

## Code Structure

```
/ImageSuperResolution
│
├── main.m                     # Main script to execute the reconstruction process
├── estimate_shifts.m          # Function to estimate spatial shifts
├── shift_and_add.m            # Function that combines aligned images
├── wiener_deconvolution.m      # Function for Wiener filtering
└── Donnees1.mat                # Dataset containing low-resolution images
```

## Usage Instructions

1. **Load Data:** Load low-resolution images from the provided dataset (`Donnees1.mat`).
2. **Estimate Shifts:** Run `estimate_shifts.m` to calculate necessary shifts for image alignment.
3. **Shift and Add:** Use `shift_and_add.m` to create an initial super-resolved image.
4. **Wiener Filter:** Apply `wiener_deconvolution.m` for further enhancement of the image quality.

### Example Code Snippet

```matlab
% Load data
load('Donnees1.mat');

% Estimate shifts
decalages = estimate_shifts(data);

% Perform shift and add
image_sr = shift_and_add(data, decalages);

% Apply Wiener deconvolution
image_final = wiener_deconvolution(image_sr, RI);

% Display results
figure;
subplot(1,2,1); imshow(ImaVrai); title('Original Image');
subplot(1,2,2); imshow(image_final); title('Reconstructed Image');
```

## Requirements

- MATLAB R2019b or later
- Image Processing Toolbox

This README provides a clear overview of the project’s objectives, features, structure, usage instructions, and contact information, making it suitable for potential users and contributors interested in image processing techniques.

