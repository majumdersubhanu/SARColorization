# SAR Image Processing Pipeline - Dataset Information

## Overview

This project uses a specific dataset to train and test the SAR Image Processing Pipeline, which involves despeckling,
colorization, and super-resolution of SAR images. The dataset provides the necessary SAR and optical image pairs
segregated by terrain, crucial for training the deep learning models used in each stage of the pipeline.

## Dataset Source

The dataset used in this project has been downloaded from Kaggle:

- **Dataset Name**: Sentinel-1 & 2 Image Pairs Segregated by Terrain
- **Author**: requiemonk
- **Kaggle Link**: [Dataset](https://www.kaggle.com/datasets/requiemonk/sentinel12-image-pairs-segregated-by-terrain)

## Dataset Description

### Structure

The dataset is organized into folders based on different terrains:

- **Agricultural Land**:
  - SAR images: `/v_2/agri/s1`
  - Optical images: `/v_2/agri/s2`

- **Barren Land**:
  - SAR images: `/v_2/barrenland/s1`
  - Optical images: `/v_2/barrenland/s2`

- **Grassland**:
  - SAR images: `/v_2/grassland/s1`
  - Optical images: `/v_2/grassland/s2`

- **Urban Areas**:
  - SAR images: `/v_2/urban/s1`
  - Optical images: `/v_2/urban/s2`

Each folder contains pairs of SAR and optical images that correspond to the same geographic area, facilitating the
training and evaluation of models designed for SAR image processing.

### Dataset Details

The dataset includes:

- **SAR Images**: Captured by the Sentinel-1 satellite, these images provide synthetic aperture radar (SAR) data, which
  is useful for understanding the surface structure and texture of the terrain.

- **Optical Images**: Captured by the Sentinel-2 satellite, these images provide optical data in various bands, helping
  to establish a colorized representation of the terrain.

### Usage

The images from this dataset are used as follows:

1. **Despeckling**: The SAR images (`/s1`) are processed to remove noise and enhance clarity.
2. **Colorization**: The despeckled SAR images are then colorized using the optical images (`/s2`) as ground truth.
3. **Super-Resolution**: The colorized images are upscaled to high resolution to enhance details.

## How to Download the Dataset

To download the dataset, you can use the Kaggle API or manually download it from the Kaggle webpage. Here’s how you can
download it using the Kaggle API:

1. Install the Kaggle CLI:

   ```bash
   pip install kaggle

2. Authenticate with Kaggle:
   Place your Kaggle API token in the `~/.kaggle/kaggle.json` file.

3. Download the dataset:

   ```bash
   kaggle datasets download -d requiemonk/sentinel12-image-pairs-segregated-by-terrain
   ```

4. Unzip the downloaded file:

   ```bash
   unzip sentinel12-image-pairs-segregated-by-terrain.zip -d /path/to/your/dataset
   ```

## Acknowledgements

We are grateful to the author `requiemonk` for providing this well-organized dataset, which has been instrumental in the
development and testing of this SAR Image Processing Pipeline.

## License

Please refer to the Kaggle dataset page for any licensing information associated with the data.
