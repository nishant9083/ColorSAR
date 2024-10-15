# ColorSAR: SAR Image Colorization

## SAR Image Colorization using Deep Learning
### Project Overview
This project aims to develop a deep learning model for colorizing grayscale Synthetic Aperture Radar (SAR) images. SAR images are typically represented in grayscale and lack the natural color information present in standard optical images. Our project enhances the interpretability of these images by converting them into colorized versions, which are useful for applications such as geological studies, environmental monitoring, and surface feature analysis.

### **Project Workflow**

#### **Step 1: Load and Slice Images into Patches**
- The SAR images are loaded from the dataset and divided into smaller patches. This allows the model to focus on localized details, improving the accuracy of colorization.

#### **Step 2: Convert Patches to Lab Color Space**
- The grayscale image patches are converted to Lab color space. This enables the model to work with the **a** and **b** channels, which represent the chromaticity information needed for colorization.

#### **Step 3: Combine and Load Data**
- The processed image patches are merged and loaded into batches. This optimizes memory usage and ensures efficient training of the model.

#### **Step 4: Implement the Encoder and Decoder**
- The encoder extracts important spatial and texture features from the SAR images, while the decoder maps these features to the **a** and **b** channels, resulting in colorized images.

#### **Step 5: Training**
- The model is trained using the prepared dataset. Various hyperparameters are adjusted to optimize the learning process and improve the accuracy of colorization.

#### **Step 6: Prediction**
- After training, the model generates colorized images by predicting the chromatic information for each patch.

#### **Step 7: Evaluation**
- The model's predictions are evaluated using several metrics. These include both quantitative measures and visual inspection to ensure that the colorized images are accurate and aesthetically pleasing.

### **Future Work**
- **Improving Denoising**: Enhance the denoising techniques to reduce noise in the SAR images, ensuring cleaner inputs and more accurate colorization.
- **Fine-tuning the Model**: Further optimize the model architecture and hyperparameters to improve the quality and accuracy of the colorized images.
- **Extended Evaluation**: Perform a comprehensive evaluation using additional metrics and visual inspection to ensure high-quality results.
- **Final Predictions**: Generate the final set of colorized SAR images using the improved model.
 
### **Technologies Used**
- Python
- PyTorch
- NumPy
- OpenCV
- Matplotlib 
- Pillow
- Scipy Image
