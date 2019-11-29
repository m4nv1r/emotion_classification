# Emotion Classification

I will be working on a computer vision problem that involves classifying human emotions. Deep learning algorithms will be applied to the KDEF dataset. The KDEF data set can be found here: http://kdef.se/

The 'Digital_Filters' jupyter notebook applys various  digital filters to images from the KDEF dataset. 

The 'Facial_Landmarks' jupyter notebook shows the image preprocessing steps that will be used and gives an example of how 68 landmarks on a face will be identified.

## Methods
First, a Gaussian filter, with kernel of size 3x3 with sigma set to zero, was applied to each of the images and Contrast Adaptive Histogram Equalization was used to deal with differences in illumination. The faces in the images, and 68 points of interest were located using a model trained by GitHub user italojs (which can be found here: https://github.com/italojs/facial-landmarks-recognition-/blob/master/shape_predictor_68_face_landmarks.dat). Two different approaches were taken to feature engineering. The first approach to feature engineering involved calculating the distances between the 68 points of interest which served as features (The code can be found in Facial_Emotion_Recognition_1st_approach.ipynb). The second approach involved determining the difference between a neural face and a face where the subject is expressing an emotion. The neutral faces were then removed from the dataset (the code can be found in Facial_Emotion_Recognition_2nd_approach.ipynb). 
The classification algorithms that were used included support vector machine (with different kernels) and artificial neural networks (ANNs) with different amounts of hidden layers. The Keras library was to create the nueral networks and RandomizedGridSearch was used to tune the hyperparameters of the neural networks.
Test accuracy, f1-scores and Matthew’s correlation coefficients were used to compare the different classification algorithms.
