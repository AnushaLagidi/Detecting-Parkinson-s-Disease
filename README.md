# Detecting-Parkinson-s-Disease
To implement the Parkinson’s detector the Histogram of Oriented Gradients (HOG) for image descriptor along with a Random Forest classifier is used since there is limited amount of training data. HOG descriptors are implemented inside the OpenCV and scikit-image library. The latter is chosen due to its flexibility. By extracting the features from each input image HOG will naturally be able to quantify how the directions of both spirals and waves change. This will capture the “shake” present in a drawing done by a Parkinson’s patient. The resulting features are a feature vector quantifying the wave or spiral.

Random Forest classifier is trained with the features of all images from the dataset. Predictions are made on the training data and the statistics are computed. The trained model is now passed with random sample images from the testing data which will be automatically classified into healthy or Parkinson patient’s drawings.

The Parkinson's detector is trained by passing the data through command line arguments for both spiral test and wave test. The testing data images are then classified by the trained model for both spiral and wave tests.

After extracting features from the input images, we trained a Random Forest classifier, obtaining:
      • 83.33% accuracy for spiral
      • 71.33% accuracy for the wave
It’s also interesting to note that the Random Forest trained on the spiral dataset obtained 76.00% sensitivity, meaning that the model was capable of predicting a true positive (i.e., “Yes, the patient has Parkinson’s”) nearly 76% of the time.

It’s important that we measure both sensitivity and specificity as:
    1. Sensitivity measures the true positives that were also predicted as positives.
    2. Specificity measures the true negatives that were also predicted as negative.
When automatically detecting Parkinson’s disease in hand drawings, at least when utilizing this particular dataset, the “spiral” drawing seems to be more useful and informative.


dataset: https://www.kaggle.com/kmader/parkinsons-drawings

detect_Parkinson.py--code to detect parkinson's disease


Future Enhancements:
• Accuracy of the model can be improved if more test data is provided • Once the accuracy of the model is increased it could be used as a replacement for the DaTscan, which allows doctors to see the detailed pictures of the brain’s dopamine system.
• The model must predict the accurate results in the early stage of the disease.
• In future, this system is expected to be improved with a greater number of patients and complex data analysis techniques.
