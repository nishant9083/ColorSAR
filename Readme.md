# ColorSAR: SAR Image Colorization

## SAR Image Colorization using Deep Learning

### Project Overview
This project aims to develop a deep learning model for colorizing grayscale Synthetic Aperture Radar (SAR) images. SAR images are typically represented in grayscale and lack the natural color information present in standard optical images. Our project enhances the interpretability of these images by converting them into colorized versions, which are useful for applications such as geological studies, environmental monitoring, and surface feature analysis.

#### **What are SAR Images?**
Synthetic Aperture Radar (SAR) images are produced by radar systems that utilize microwave signals to create detailed images of the Earth's surface. Unlike traditional optical imaging, SAR operates independently of sunlight and can penetrate through clouds, providing valuable data for various remote sensing applications. However, SAR images are generally monochromatic and do not convey color information, which can limit their usability in certain analyses. Colorization can help reveal features that are not easily distinguishable in grayscale images, improving interpretability and analysis.


### **Project Workflow**

![Workflow](https://github.com/user-attachments/assets/6e280a7a-e9fd-4fc4-b810-4fddf56a57cd)


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

### **Model Comparison**

In this section, we compare the results of two different trained models. Each model has been evaluated based on its performance in colorizing the SAR images. Below are the images produced by each model, showcasing the differences in colorization quality and accuracy.

#### **Model 1: Trained on L and AB Channels of Original Color SAR Images**

![Model 1 Result](https://github.com/user-attachments/assets/df049178-7010-4e2a-ba98-065e963bdaa7)
![Model 1 Result2](https://github.com/user-attachments/assets/6fabe51c-476c-4f10-b8f7-4c93e31534c1)


*This model was trained using both the **L** (luminance) and **AB** (chrominance) channels of original color SAR images as input-output pairs. As a result, the colorization output is highly accurate, demonstrating that this model effectively captures the underlying color information. The successful performance in this model proves the efficacy of the colorization approach.*

#### **Model 2: Trained on L Channel of Noisy, Uncolored SAR Images (Post-Denoising) with AB Channel of Original Color SAR Images**

![Model 2 Result](https://github.com/user-attachments/assets/e5716ae3-d267-40d2-ab6c-a369d55c7f9f)
![Model 2 Result2](https://github.com/user-attachments/assets/377bdffa-ca74-44a2-b93b-7802f9c1b6e2)


*In this model, training was conducted on the **L** channel of noisy, uncolored SAR images after applying denoising, combined with the **AB** channel of original color SAR images as input-output pairs. Consequently, while the color prediction remains fairly good, the overall results do not match the original due to the noise present in the **L** channel. This noise has impacted the preservation of structural definition in the images, leading to less accurate representations compared to Model 1.*

#### **Comparison Summary**
- **Model 1** demonstrates superior color accuracy due to the use of original color data, effectively proving the robustness of the colorization model.
- **Model 2**, while showing decent color predictions, suffers from structural fidelity issues caused by noise in the luminance channel, indicating that further refinement in denoising processes may be necessary for future iterations.

### **Future Work**
- **Improving Denoising**: Enhance the denoising techniques to reduce noise in the SAR images, ensuring cleaner inputs and more accurate colorization.\
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
