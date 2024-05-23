# Liver-Tumor-Segmentation
This project focuses on liver tumor segmentation using a modified U-Net architecture combined with Sobel edge detection. The objective is to improve segmentation accuracy by incorporating edge detection techniques.

To install the necessary libraries, run the following command:
pip install pynrrd tensorflow scikit-image

Dataset
The dataset consists of NRRD files containing liver tumor images and their corresponding segmentation masks. The dataset should be organized in folders where each folder contains both segmented and unsegmented files.

Usage

Finding NRRD Files
The function find_nrrd_files(folder) reads segmented and unsegmented files from a given folder and organizes them into a dictionary.

Loading and Preprocessing Volume
The function load_and_preprocess_volume(image_path, mask_path, target_size=(256, 256), num_slices=5) loads and preprocesses NRRD files, selecting informative slices based on Sobel filter scores.

Model Architecture
The model is a modified U-Net architecture. The key components of the architecture are:

Input layer
Multiple convolutional layers with ReLU activation
MaxPooling layers
Dropout layers
Conv2DTranspose layers for upsampling
Concatenate layers for merging features
Final output layer with sigmoid activation
Training
The training process involves:

Splitting the data into training and validation sets using train_test_split or KFold.
Using ImageDataGenerator for data augmentation.
Compiling the model with an appropriate loss function and optimizer.
Implementing early stopping to prevent overfitting.
Evaluation
The evaluation metrics include:

Dice Coefficient: A measure of overlap between the predicted and true segmentation masks.
AUC and ROC: For evaluating the classification performance.
Results
Results include the Dice Coefficient and AUC scores, along with visualizations of the segmented images compared to the ground truth.
