# UCS2523 – Image Processing and Analysis

## Digital Image Processing Assignment

This repository contains a Jupyter Notebook that implements an end-to-end digital image processing pipeline as per the course assignment `IPA_Assignment.pdf`. The workflow covers image acquisition, noise simulation, preprocessing and enhancement, denoising, segmentation and edge detection, and feature extraction, concluding with a 6-panel pipeline visualization.

Name: Thirumurugan RA \
Class: CSE C \
Register No: 3122 23 5001 149

## Notebook

- File: `IPA_Assignment.ipynb`
- Input image used in the notebook: `Table.jpg` (expected to be placed in the same folder as the notebook)
- Main outputs are saved under the `images/` folder next to the notebook (see the Outputs section below). The folder is created automatically when you run the notebook.

> Note: The markdown in the notebook outlines the assignment expectations for each stage. Run the cells sequentially to generate intermediate artifacts and the final composite visualization.

## Pipeline Stages (what the notebook does)

1. Image Acquisition
   - Loads the color image `Table.jpg`.
2. Noise Simulation
   - Adds Gaussian noise and optionally Salt-and-Pepper noise.
3. Preprocessing & Enhancement
   - Converts to grayscale, resizes to 512×512, applies histogram equalization and contrast stretching.
4. Noise Filtering & Denoising
   - Compares Gaussian blur and Median filtering.
   - Computes objective metrics: PSNR and SSIM.
5. Segmentation & Edge Detection
   - Performs Otsu’s thresholding and Canny edge detection.
6. Feature Extraction & Evaluation
   - Finds contours, filters by area, computes centroids, and plots RGB color histograms for the largest objects for Canny Edge Image.
7. Final Visualization
   - Produces a 2×3 grid that summarizes the pipeline: Original → Noisy → Enhanced → Denoised → Edges → Labeled features.

## Dependencies

The notebook uses the following Python libraries:

- OpenCV (`opencv-python`)
- scikit-image (`scikit-image`)
- Pillow (`Pillow`)
- NumPy (`numpy`)
- Matplotlib (`matplotlib`)
- Jupyter (for running the notebook)

A `requirements.txt` file is provided.

## Setup (Windows)

1. Ensure Python 3.10+ is installed and available on PATH.
2. Create and activate a virtual environment, then install dependencies from `requirements.txt`.

Commands:

```powershell
# Create a virtual environment in .venv
python -m venv .venv

# Activate it (PowerShell)
.\.venv\Scripts\Activate

# Install dependencies
pip install -r requirements.txt
```

Place `Table.jpg` in the same folder as `IPA_Assignment.ipynb` before running the notebook.

## How to Run the Notebook

- Open the folder in VS Code and open `IPA_Assignment.ipynb`.
- Select a Python interpreter with the required packages installed.
- Run all cells top-to-bottom to generate intermediate images and the final figure.
- If you see a message like "Could not load image ...", make sure earlier cells ran successfully and that the expected files exist in the working directory.

## Outputs (generated files)

Running the notebook will save the following images (file names as written by the code):

- Noise simulation:
   - `images/gaussian_noise_color.jpg`
   - `images/salt_and_pepper_noise_color.jpg`
- Preprocessing / Enhancement:
   - `images/grayscale.jpg`
   - `images/grayscale_resized.jpg`
   - `images/histogram_equalized.jpg`
   - `images/contrast_stretched.jpg`
- Denoising:
   - `images/gaussian_filter.jpg`
   - `images/median_filter.jpg`
- Segmentation / Edges:
   - `images/otsu_threshold.jpg`
   - `images/canny_edges.jpg`
- Feature extraction and summary:
   - `images/canny_color_histograms_grid_top6.jpg`
   - `images/canny_contours_numbered_result.jpg`
   - `images/pipeline_visualization_6_panel.jpg` (final 6-panel overview)

Console outputs include PSNR and SSIM comparisons for Gaussian vs. Median filtering.