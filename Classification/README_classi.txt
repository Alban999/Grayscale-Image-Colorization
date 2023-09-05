================================================
============== Classification CNN ==============
================================================

This notebook contains the classification CNN model for grayscale image colorization.

Author : MUSIBAU Solomon, DIETRICH Alban, SAHLI Yassine
Date : 04 June 2021


=======================================================================

With this program are given some useful files :


*One file containing the 313 discrete (a, b) pairs "pts_in_hull.npy"


*Two images datasets are given :
	* Berkeley_Datasets    (200 training images, 200 test images, 100 validation images)
	* form_Datasets       (200 training images, 200 test images, 100 validation images)

	The Berkeley datasets contains normal images. The form datasets contains simple images representing 
	regular polygons randomly placed over a white font. 


*Two probability distributions are given :
	* proba_distrib_Berkeley56.txt  (For the Berkley training set at 56 pixels)
	* proba_distrib_Form56.txt     (For the form training set at 56 pixels)


*Two already trained CNN model :
	* color_net_Berkeley_s56_e200_W.pth (Model trained over 200 epochs, with rebalancing, with the Berkley datasets at 56 pixels)
	* color_net_form_s56_e50_W.pth     (Model trained over 50 epochs, with rebalancing, with the form datasets at 56 pixels)


=======================================================================

Steps to run the model :

1) Run the imports 


2) Run the GPU Check, verify that the output is "True"


3) Write the input parameters that you want, then run "Input Parameters" 
   NOTE  : By default, all input parameters are written for a training using the form dataset.
	   If you just want to run, no modifications are needed. 
   NOTE2 : Please verify the paths to the respectives files in the input parameters before running.

	Input parameters :

	* size : Size of the images (in pixel) (does not have to match their original size but must be a multiple of 8)

	* training_size : Size of the training datasets (in number of images)
	* test_size :     Size of the testing datasets (in number of images)
	* val_size :      Size of the validation datasets (in number of images)

	* num_epochs : Number of epochs
	* batch_size : Size of each batch

	* lbda :  Proportion of the uniform distribution in the weights computation
	* sigma : Standard deviation of the Gaussian Kernel during the smoothing of the probabilities

	* weighted : Use classification with rebalancing (weighted = True) or not (weighted = False)

	* TRAIN_DATA_PATH : Path to the training dataset
	* TEST_DATA_PATH :  Path to the testing dataset
	* VAL_DATA_PATH :   Path to the validation dataset

	* DISCRETE_AB_PATH : Path to the txt file containing the discrete (a, b) pairs

	* use_save_proba :  Use a probability distribution from some txt file (use_save_proba = True) 
			    or compute the probability distribution of the current training set (use_save_proba = False)
	* SAVE_PROBA_PATH : Path to the txt file containing the probability distribution if use_save_proba = True. 
			    Otherwise, it is the path to the txt file on which will be saved the computed 
			    probability distribution of the current training set

	* SAVE_MODEL_PATH : Path to the file where the model will be saved after training


4) To load the datasets, run "Encoding and decoding functions" then all the cells in "Datasets loading" in order


5) To get the weights distribution, run the cells in "Probability distribution" in order, then the cells in "Smoothing", 
   then the cells in "Weights computation"
   NOTE : This is not needed if you choose "weighted = False" in the input parameters.


6) To define the CNN model, run the cells in "Model CNN" in order. 


7) To train the model, run the cells in "Training Loop" in order. You can then look at the accuracies evolutions
   by running "Accuracies".
   NOTE  : This is not needed if you want to use an already trained model (e.g. one of the two pth files given with the code)
   NOTE2 : At the end of the training loop, the model is saved in the SAVE_MODEL_PATH that you choose in the input parameters


8) To test the model :
	IF YOU WANT TO TEST AN ALREADY TRAINED MODEL :
		a) Run the first cell after setting "path_to_state_dict" to the path of the model you want to test
		b) Run the second cell
		NOTE : If you test an already trained model, verify that you use the concording datasets for testing

	ELSE :
		a) Run the second cell only
 




