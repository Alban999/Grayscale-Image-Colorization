================================================
============== Regression CNN ==============
================================================

This notebook contains the regression CNN model for grayscale image colorization.

Author : MUSIBAU Solomon, DIETRICH Alban, SAHLI Yassine
Date : 04 June 2021


=======================================================================

With this program are given some useful files :


*One images datasets are given :
	* Datasets    (200 training images, 200 test images, 100 validation images, coming from Berkeley dataset)


*One already trained CNN model :
	* Color_Regression_Berkeley_500epch_112.pth (Model trained over 500 epochs,with the Datasets at 112 pixels)


=======================================================================

Step to run the model :

1) Run the imports 


2) Run the GPU Check, verify that the output is "True"


3) Write the input parameters that you want, then run "Input Parameters" 
   NOTE  : By default, all input parameters are written for a training using the Datasets.
	   If you just want to run, no modifications are needed. 
   NOTE2 : Please verify the paths to the respectives files in the input parameters before running.

	Parameters : 

	* size : Size of the images (in pixel) 
	* num_epochs : Number of epochs
	* batch_size : Size of each batch
	* learning_rate : learning rate for the optimizer


	* TRAIN_DATA_PATH : Path to the training dataset
	* TEST_DATA_PATH :  Path to the testing dataset
	* VAL_DATA_PATH :   Path to the validation dataset


4) To load the datasets, run all the cells in "Dataset : Berkeley" in order


5) To define the CNN model, run the cells in "Neural Network model (CNN) for Regression" in order. 


6) To train the model, run the cells in "Training  and validation Loop" in order. 
   NOTE  : This is not needed if you want to use an already trained model (e.g. the pth file given with the code)
   NOTE2 : At the end of the training loop, the model is saved in the path that you specify

7) After the training (ONLY IF the training have been done, ELSE : do not run these cells), you can run the cells below the training cells to visualize the loss results 

8) To test the model :
	IF YOU WANT TO TEST AN ALREADY TRAINED MODEL :
		a) Run the first cell after setting "path_to_state_dict" to the path of the model you want to test
		b) Run the second cell
		NOTE : If you test an already trained model, verify that you use the concording datasets for testing

	ELSE :
		a) Run the second cell only
 




