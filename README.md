# Lung-Cancer-Detection-Using-CT-Scan-Images
AN EFFECTIVE APPROACH TO DETECT LUNG CANCER ON CT SCAN IMAGES USING SEGMENTATION AND CONVOLUTIONAL NEURAL NETWORK
Table of Contents
 1.Introduction
 2.Dataset and Visualization
 3.Segmentation with Watershed Algorithm
 4.Models and Performance
 5.System Architecture
 6.Conclusion
 
 1. Introduction
    Lung cancer, classified as non-small cell lung cancer (NSCLC) and small cell lung cancer (SCLC), is a leading cause of cancer-related deaths. While smoking is the primary risk factor, environmental exposures 
    also contribute. Early detection is critical for effective treatment, which may include surgery, chemotherapy, radiation, or targeted therapies.
 
 
 2. Dataset and Visualization
    The LUNA16 dataset was utilized, containing 1,002 labeled CT scan images from 12 patients. The Pydicom library was used to extract metadata (e.g., patient ID, image slices) and construct 3D lung 
    representations, providing insights for cancer detection.
    

3. Segmentation with Watershed Algorithm
   The Watershed algorithm segments CT scans by treating pixel intensities as topographic elevations. Combined with Sobel filters and morphological operations, it removes non-lung regions, isolates internal lung 
   structures, and highlights cancerous cells. This process generated 1,002 labeled images with an equal number of cancerous and non-cancerous cases.



4. Models and Performance
   Two Convolutional Neural Network (CNN) models were tested:

   Sequential_1: Basic CNN with convolution, max-pooling, and dropout layers.
   Training Accuracy: 78.5%
   Validation Accuracy: 74.2%
   Validation Loss: 0.48
   
   Sequential_2: A deeper CNN with additional layers for enhanced feature extraction.
   Training Accuracy: 88.7%
   Validation Accuracy: 85.1%
   Validation Loss: 0.36

  Sequential_2 achieved the best performance with better generalization.


  5. System Architecture
     The system for lung cancer detection follows these stages:

     Input:
     CT scan images from the LUNA16 dataset.
     
     Preprocessing:
     Metadata extraction using the Pydicom library.
     Lung segmentation with the Watershed algorithm integrated with Sobel filters and morphological operations to create binary masks isolating cancerous regions.


     Feature Extraction and Training:
      Preprocessed images are fed into CNN models (Sequential_1 and Sequential_2).
      Models are trained and validated using metrics such as accuracy and loss to evaluate performance.

     Classification Output:
     The system predicts the presence or absence of lung cancer based on the input CT scan image.
     
     Performance Metrics:
     Sequential_2: 88.7% training accuracy, 85.1% validation accuracy, and 0.36 validation loss.
  6. Conclusion and Results
     Sequential_2 outperformed Sequential_1 with 88.7% training accuracy and 85.1% validation accuracy, demonstrating its effectiveness in lung cancer detection. Future work could explore more advanced CNN 
     architectures and larger datasets for improved accuracy.

































