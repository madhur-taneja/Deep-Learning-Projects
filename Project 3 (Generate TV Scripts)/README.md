# Generate TV Scripts

A Recurrent Neural Network (RNN) to generate a new Simpsons TV script for a scene at Moe's Tavern using part of the Simpsons dataset of scripts from 27 seasons

Open and view the Project using the `.zip` file provided or at my [Github Repository](https://github.com/madhur-taneja/Generate-TV-Scripts)

The project has been hosted on [Github](https://madhur-taneja.github.io/Generate-TV-Scripts/dlnd_tv_script_generation.html)

## Table of Contents
- [Getting Started](#getting-started)
	- [Tools Required](#tools-required)
	- [Installation](#installation)
- [Running the App](#running-the-app)
- [Development](#development)
- [Stopping the App](#stopping-the-app)
- [References](#references)

## Getting Started

The starter project can be downloaded from [here](https://github.com/udacity/deep-learning/tree/master/tv-script-generation)

The project will be evaluated by a Udacity code reviewer according to the project [rubric](https://review.udacity.com/#!/rubrics/725/view)

### Tools Required

You would require the following tools to develop and run the project:

* [Pip](https://pip.pypa.io/en/stable/installing/)
* [Python](https://www.python.org/downloads/)
* [Anaconda](https://www.anaconda.com/products/individual) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)

### Installation

#### With Conda
* Start by installing python and anaconda
* Create a new conda environment
	```
	conda create --name generate-scripts python=3
	```
* Enter your new environment:
	* Mac/Linux: `>> source activate generate-scripts`
	* Windows: `>> conda activate generate-scripts`
* Install the requirements using the following command:
	```
	pip install -r requirements.txt
	```

#### Without Conda
If you don't have Conda, a `requirements.txt` file is provided to install all of the necessary packages using pip.

Open CLI in the root directory of the project. Run the following command:
```
python -m venv --system-site-packages .\venv # Creates a virtual environment
.\venv\Scripts\activate                      # Activates the environment
pip install -r requirements.txt              # Installs the required packages
pip list                                     # Show packages installed within the virtual environment
```

## Running the App

To run the project:
1. Activate the Conda or Python virtual environment as mentioned above
2. Start the Jupyter Notebook by running the following command:
	```
	jupyter notebook
	```
	Open your browser and visit localhost:8888 (or the port indicated in the terminal), and you should see all of the contents of the project in `dlnd_tv_script_generation.ipynb` notebook
3. After completing the development, press the `play`  :arrow_forward:  icon to start the execution of cells. The output will be visible right below each respective cells.

## Development

The notebook contains the following functions and configurations:
1. `create_lookup_tables` to create two dictionaries: `vocab_to_int` and `int_to_vocab`
2. `token_lookup` returns a dictionary that can tokenizes the provided symbols.
3. `get_inputs` function to create TF Placeholders for the Neural Network with Input, Target and Learning Rate placeholders.
4. Enough `epochs` to get a near minimum in the training loss but there is no real upper limit for this. Just need to make sure the training loss is low and not improving much with more training.
5. `Batch size` should be large enough to train efficiently, but small enough to fit the data in memory. No real “best” value here, it usually depends on GPU memory.
6. Size of the RNN cells `(number of units in the hidden layers)` should be large enough to fit the data well. No real “best” value.
7. The sequence length `(seq_length)` here should be about the size of the length of sentences you want to generate and should match the structure of the data.

Follow the instructions in the notebook; they will lead you through the project. You'll be editing the `dlnd_tv_script_generation.ipynb` file.

## Stopping the App

Once you're done with the app, stop it gracefully using the following command:

1. Select `File -> Close and Halt` inside jupyter notebook 
2. Press `Ctrl+c` in the cli

#### With Conda
```
>> conda deactivate generate-scripts          # Deactivate the environment
>> conda remove --name generate-scripts --all # Delete the environment
```
#### Without Conda
```
>> deactivate                                 # Deactivate the environment
```

## References

* [RNN and LSTM Lecture](https://www.youtube.com/watch?v=iX5V1WpxxkY) by Andrej Karpathy 
* [Word Embeddings](https://arxiv.org/abs/1507.05523) by Siwei Lai, Kang Liu, Liheng Xu, Jun Zhao
* A recent [Medium article](https://medium.com/coloredfeather/generating-a-tv-script-using-recurrent-neural-networks-dd0a645e97e7) that might help in understanding a similar project
* [Tensorflow](https://www.tensorflow.org/install/pip)
