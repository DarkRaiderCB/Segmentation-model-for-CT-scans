# 3D Segmentation of Abdominal Organs from CT Scans

## Overview

This project focuses on building a 3D segmentation model to accurately segment the Liver, Right Kidney, Left Kidney, and Spleen from CT abdominal scans. The model aims to assist in medical image analysis by providing precise organ segmentation, crucial for various diagnostic and treatment planning processes.

## Dataset

The dataset used in this project is the **CT Abdomen Organ Segmentation Dataset**. It contains CT scans labeled with multiple organs, but our focus is on the following organs:

- Liver
- Right Kidney
- Left Kidney
- Spleen

The dataset can be accessed [here](https://zenodo.org/records/7860267).

## Model Architecture

### VNet

The model architecture chosen for this task is **VNet**, a 3D Convolutional Neural Network (CNN) designed for volumetric medical image segmentation. VNet is particularly well-suited for handling the complex and varied shapes of internal organs. Key architectural features include:

- **3D Convolutions**: Captures the spatial relationships within the 3D volume.
- **Residual Connections**: Enhances the flow of gradients, improving model convergence.
- **Dice Loss Function**: Optimized for segmentation tasks to address class imbalance by focusing on overlap between predicted and true segments.

## Training Process

### Data Preprocessing

The preprocessing pipeline involves:

1. **Normalization**: Standardizing the pixel intensities to have a mean of zero and a standard deviation of one.
2. **Resampling**: Resampling all volumes to have the same voxel dimensions, ensuring consistent input size for the model.
3. **Augmentation**: Applying random transformations such as rotations, flips, and zooms to improve model robustness.

### Training

- **Split Strategy**: The dataset is split into training, validation, and test sets to ensure unbiased performance evaluation.
- **Training Configuration**: The model is trained with defining batch size, and for `15` epochs.

### Validation and Inference

- **Dice Score Calculation**: The primary evaluation metric is the Dice score, calculated for each of the target organs. This score measures the overlap between the predicted segmentation and the ground truth, with a score of 1 indicating perfect overlap.
- **Inference**: The trained model is used to predict segmentation masks on the test set, which were not seen during training. The predictions are then evaluated to ensure the model's generalization capability.

## 3D Visualization

Below is an embedded animation video that demonstrates the segmented organs. This visualization helps in qualitatively assessing the model's performance and provides insights into the segmentation quality.

![3D Visualization Video 1](https://drive.google.com/file/d/1B87M4YHVxkC3hcJq5X9aWpALtMk4A8AL/view?usp=drive_link)

![3D Visualization Video 2](https://drive.google.com/file/d/1pSawp8AzUd50BeWpRc8gXomLC6p_clkj/view?usp=drive_link)

## Setup Instructions

### Prerequisites

Ensure that you have the following installed:

- Python 3.8+
- CUDA Toolkit (for GPU acceleration)
- Libraries: PyTorch, NumPy, nibabel, matplotlib, and scikit-learn

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/3d-segmentation-ct-organs.git
   cd 3d-segmentation-ct-organs
   ```

2. Create a virtual environment and activate it:
  ```
    conda create --name myenv
    conda activate myenv
  ```

3. Install the required packages:
  ```
    pip install -r requirements.txt
  ```

## Running the Code

The code is in a `.ipynb` file. It should be run in `Jupyter` environment.

## Saved Model File

The model file has also been saved. Hence, ready to use in other codes too.


## Thanks for visiting the repo!
