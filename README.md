

# FITS Image Star Photometry Tool

## Overview

This tool performs aperture photometry on stars in a FITS image to calculate their magnitudes, errors, signal-to-noise ratios (SNR), and fluxes. It finds the optimal flux for each star and uses a reference star to calculate magnitudes.

## Features

- Reads FITS images.
- Performs aperture photometry to find optimal flux.
- Calculates magnitudes, errors, SNRs, and fluxes for specified stars.
- Adjusts aperture size for stars near nebulae.

## Dependencies

- `astropy`: For handling FITS images.
- `numpy`: For numerical operations.
- `photutils`: For aperture photometry.

You can install these dependencies using the following command:

```sh
pip install astropy numpy photutils
```

## Usage

1. Clone the repository:

```sh
git clone https://github.com/yourusername/fits-star-photometry-tool.git
cd fits-star-photometry-tool
```

2. Place your FITS image file in a `data` directory inside the project folder and name it `stars.fits`.

3. Run the script:

```sh
python main.py
```

## Example Output

```
Reference Star:
Reference Star Magnitude: 8.88
Reference Star Raw Flux: 12345.67

Reference Star Analysis:
Reference Star at position (425.01049660550996, 786.8934083356211): 
Magnitude = 8.88, Error = 0.01023, SNR = 25.78, Flux = 12345.67
```

## How It Works

### Calculating Magnitudes

The `calculate_magnitude` function calculates the magnitude of a star given its flux, using a reference star's magnitude and flux.

### Finding Optimal Flux

The `find_optimal_flux` function performs aperture photometry on a star to find the optimal flux and SNR by trying different aperture sizes.

### Main Function

The `main` function:
1. Loads the FITS image.
2. Defines the reference star's position and magnitude.
3. Finds the optimal flux for the reference star.
4. Prints the magnitude, error, SNR, and flux for the reference star.
