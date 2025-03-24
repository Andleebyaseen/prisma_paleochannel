This repository provides a basic pipeline for segmenting raster data using a standard UNet model. The workflow includes reading raster and mask files, creating tiles from them, training a UNet model, and performing inference with proper geospatial referencing.

The file **computing_tiles.ipynb** is responsible for reading the raster data and the corresponding mask files. It then creates image and mask tiles from these inputs, which are used for training and inference.
The UNet model is implemented in the **UNET_baseline.ipynb** file. This is a standard baseline model used for segmentation tasks.
The **inference.ipynb** file contains scripts for running predictions on the tiled images and calculate necessary metrics. After prediction, the resulting tiles are projected to their original geospatial location by referencing the original raster's coordinate reference system (CRS).

Basic instructions to get the repository running:

1.	Create a new Anaconda environment with Python and Pip installed, then activate it:
conda create -n <env_name> python=3.11 pip
conda activate <env_name>

2.	Install the required dependencies from the requirements.txt file. Make sure to use the correct PyTorch index URL for your CUDA version.
Example (for CUDA 11.8):
pip install -r requirements.txt --extra-index-url https://download.pytorch.org/whl/cu118
