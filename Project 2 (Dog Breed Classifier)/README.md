# Dog Breed Classifier

A pipeline of neural networks to process real-world, user-supplied images. If given an image of a dog, the algorithm will identify an estimate of the canine’s breed else if supplied an image of a human, the code will identify the resembling dog breed.

Open and view the Project using the `.zip` file provided or at my [Github Repository](https://github.com/madhur-taneja/Predicting-Bike-Sharing-Data)

The project has been hosted on [Github](https://madhur-taneja.github.io/Dog-Breed-Classifier/report.html)

## Table of Contents
- [Overview](#overview)
- [Getting Started](#getting-started)
	- [Tools Required](#tools-required)
	- [Instructions](#instructions)
		- [Setting up the Codebase](#codebase)
		- [Setting up the Dataset](#dataset)
		- [Installation](#installation)
- [Running the App](#running-the-app)
- [Development](#development)
- [Stopping the App](#stopping-the-app)
- [Evaluation](#evaluation)
- [Submission](#submission)
- [References](#references)

## Overview

Welcome to the Convolutional Neural Networks (CNN) project in the Deep Learning Foundations Nanodegree! In this project, I learned how to build a pipeline that can be used within a web or mobile app to process real-world, user-supplied images.  Given an image of a dog, the algorithm will identify an estimate of the canine’s breed.  If supplied an image of a human, the code will identify the resembling dog breed.  

![Sample Output][image1]

Along with exploring state-of-the-art CNN models for classification, I made important design decisions about the user experience for your app. The goal is that by completing this lab, I understood the challenges involved in piecing together a series of models designed to perform various tasks in a data processing pipeline. Each model has its strengths and weaknesses, and engineering a real-world application often involves solving many problems without a perfect answer.  My imperfect solution will nonetheless create a fun user experience!

## Getting Started

### Tools Required

You would require the following tools to develop and run the project:

* [Pip](https://pip.pypa.io/en/stable/installing/)
* [Python](https://www.python.org/downloads/)
* [Anaconda](https://www.anaconda.com/products/individual) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)

### Instructions

#### <a name="codebase">Setting up the Codebase</a>

The starter project can be downloaded from [here](https://github.com/udacity/dog-project)

1. Clone the repository and navigate to the downloaded folder.

	```	
	git clone https://github.com/udacity/dog-project.git
	cd dog-project
	```

#### <a name="dataset">Setting up the Dataset</a>

2. Download the [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/dogImages`. 

3. Download the [human dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/lfw`.  If you are using a Windows machine, you are encouraged to use [7zip](http://www.7-zip.org/) to extract the folder. 

4. Donwload the [VGG-16 bottleneck features](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogVGG16Data.npz) for the dog dataset.  Place it in the repo, at location `path/to/dog-project/bottleneck_features`.

#### Installation

Start by installing python and anaconda

5. (Optional) __If you plan to install TensorFlow with GPU support on your local machine__, follow [the guide](https://www.tensorflow.org/install/) to install the necessary NVIDIA software on your system.  If you are using an EC2 GPU instance, you can skip this step.

6. <a name="6"> </a> (Optional) **If you are running the project on your local machine (and not using AWS)**, create (and activate) a new environment.

	- __Linux__ (to install with __GPU support__, change `requirements/dog-linux.yml` to `requirements/dog-linux-gpu.yml`): 
	
	```
	conda env create -f requirements/dog-linux.yml
	source activate dog-project
	
	```  
	- __Mac__ (to install with __GPU support__, change `requirements/dog-mac.yml` to `requirements/dog-mac-gpu.yml`): 
	
	```
	conda env create -f requirements/dog-mac.yml
	source activate dog-project
	```  
	**NOTE:** Some Mac users may need to install a different version of OpenCV
	
	```
	conda install --channel https://conda.anaconda.org/menpo opencv3
	```
	- __Windows__ (to install with __GPU support__, change `requirements/dog-windows.yml` to `requirements/dog-windows-gpu.yml`):  
	
	```
	conda env create -f requirements/dog-windows.yml
	activate dog-project
	```

7. (Optional) **If you are running the project on your local machine (and not using AWS)** and Step 6 throws errors, try this __alternative__ step to create your environment.

	- __Linux__ or __Mac__ (to install with __GPU support__, change `requirements/requirements.txt` to `requirements/requirements-gpu.txt`): 
	
	```
	conda create --name dog-project python=3.5
	source activate dog-project
	pip install -r requirements/requirements.txt
	```
	**NOTE:** Some Mac users may need to install a different version of OpenCV
	
	```
	conda install --channel https://conda.anaconda.org/menpo opencv3
	```
	- __Windows__ (to install with __GPU support__, change `requirements/requirements.txt` to `requirements/requirements-gpu.txt`):  
	
	```
	conda create --name dog-project python=3.5
	activate dog-project
	pip install -r requirements/requirements.txt
	```
	
8. (Optional) **If you are using AWS**, install Tensorflow.

	```
	sudo python3 -m pip install -r requirements/requirements-gpu.txt
	```
	
9. Switch [Keras backend](https://keras.io/backend/) to TensorFlow.
	- __Linux__ or __Mac__: 
	
		```
		KERAS_BACKEND=tensorflow python -c "from keras import backend"
		```
	- __Windows__: 
	
		```
		set KERAS_BACKEND=tensorflow
		python -c "from keras import backend"
		```

10. (Optional) **If you are running the project on your local machine (and not using AWS)**, create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `dog-project` environment.
 
	```
	python -m ipykernel install --user --name dog-project --display-name "dog-project"
	```

11. <a name="11"> </a> Open the notebook.

	```
	jupyter notebook dog_app.ipynb
	```

12. (Optional) **If you are running the project on your local machine (and not using AWS)**, before running code, change the kernel to match the dog-project environment by using the drop-down menu (**Kernel > Change kernel > dog-project**). Then, follow the instructions in the notebook.

__NOTE:__ While some code has already been implemented to get you started, you will need to implement additional functionality to successfully answer all of the questions included in the notebook. __Unless requested, do not modify code that has already been included.__

## Running the App

To run the project:

1. Activate the conda environment as mentioned in the [6th and 7th point](#6) of the Installation section
2. Start the Jupyter Notebook as mentioned in the [11th point](#11) of the Installation section
3. Press the `play`  :arrow_forward:  icon to start the execution of cells. The output will be visible right below the cells.

## Development

Follow the instructions in the notebook; they will lead you through the project. You'll be editing the `dog_app.ipynb` file.

## Stopping the App

Once you're done with the app, stop it gracefully using the following command:

1. Select `File -> Close and Halt` inside jupyter notebook 
2. Press `Ctrl+c` in the cli
3. Deactivate and Delete (if finished with the project) the environment
	```
	>> conda deactivate dog-project           # Deactivate the environment
	>> conda remove --name dog-project --all  # Delete the environment
	```

## Evaluation

The project will be reviewed by a Udacity reviewer against the CNN project [rubric](https://review.udacity.com/#!/rubrics/810/view).  Review this rubric thoroughly, and self-evaluate your project before submission.  All criteria found in the rubric must meet specifications for you to pass.

## Submission

When you are ready to submit your project, collect the following files and compress them into a single archive for upload:
- The `dog_app.ipynb` file with fully functional code, all code cells executed and displaying output, and all questions answered.
- An HTML or PDF export of the project notebook with the name `report.html` or `report.pdf`.
- Any additional images used for the project that were not supplied to you for the project. __Please do not include the project data sets in the `dogImages/` or `lfw/` folders.  Likewise, please do not include the `bottleneck_features/` folder.__

Alternatively, your submission could consist of the GitHub link to your repository.

## References

* Keras Docs on [Convolutional](https://keras.io/layers/convolutional/)
* Loss Functions on [Andrej Karpathy's tumblr](https://lossfunctions.tumblr.com/)
* [Keras Cheat Sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Keras_Cheat_Sheet_Python.pdf)
* [Batch Normalization](https://arxiv.org/pdf/1502.03167v2.pdf)


[//]: # (Image References)

[image1]: ./images/sample_dog_output.png "Sample Output"
[image2]: ./images/vgg16_model.png "VGG-16 Model Keras Layers"
[image3]: ./images/vgg16_model_draw.png "VGG16 Model Figure"