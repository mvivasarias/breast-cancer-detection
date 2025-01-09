This project detects breast cancer from tumor images using machine learning. 
The images are preprocessed, features are extracted, and two classifiers (Linear Discriminant Analysis (LDA) and Random Forest) are trained. 
Based on model evaluation, the LDA model is selected for production to predict tumor types in new images.

Preprocess Images:

Convert images to grayscale
Apply Gaussian blur to reduce noise
Segment the image using Otsu's thresholding
Fill small gaps using closing mask and label connected regions
Extract Features:

Calculate properties like area, perimeter, circularity, eccentricity, solidity, and intensity stats (mean, std, max, min) from the labeled regions.
Train Classifiers:

Train Linear Discriminant Analysis (LDA) and Random Forest classifiers using the extracted features.
Evaluate Models:

Evaluate using accuracy, classification report, and confusion matrix. LDA is selected based on evaluation metrics.
Production:

Load the pre-trained LDA model and make predictions on new images.


Usage
1. Preprocess Images & Extract Features
Run the preprocessing notebook to process the tumor images and extract features.

python TDI_Algorithm.ipynb

This will prepare the image data and extract features such as area, perimeter, and circularity for each labeled tumor region.

2. Train Classifier Models
Run the training notebook to train the LDA and Random Forest classifiers using the extracted features.

python Training_classifier.ipynb

This notebook splits the data, trains the classifiers, and evaluates their performance. The LDA model is saved as lda_model_9_features.pkl.

3. Load the Model & Make Predictions
Run the production notebook to load the pre-trained LDA model and make predictions on new images.

python Production_of_classifier_.ipynb

This will:

Load the trained LDA model from lda_model_9_features.pkl
Process new tumor images
Make predictions and visualize the results by highlighting detected tumors with red rectangles.

4. Visualize Predictions & Save Results
The results (tumor predictions) are visualized, and the predictions are saved in a CSV file for further analysis.

python Production_of_classifier_.ipynb
