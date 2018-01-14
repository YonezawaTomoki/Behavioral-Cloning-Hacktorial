# Behavioral-Cloning-Hacktorial-Files
All the files needed for the Terrapin Hackers Hacktorial on Behavioral Cloning (End to End Learning) for Self Driving Cars. 

The presentation is available to view [here](http://goo.gl/XtIBNg).

The [model.py](/model.py) is a template for the hacktorial and the final code is available to view in [final_model.py](/final_model.py). [drive.py](/drive.py) contains the code needed to connect your model and the simulator.

Model inspired by [Nvidia's End to End Learning Paper](https://devblogs.nvidia.com/parallelforall/deep-learning-self-driving-cars/). Project idea, [drive.py](/drive.py), and training data from Udacity Self Driving Car Nanodegree program.

For those new to deep learning or computer vision, here are some good blog posts to give you a solid basis for understanding convolutional neural networks, max pooling, etc. Included is a sample tutorial which guides you through installing Keras and guides you through creating a CNN that recognizes handwritted digits.

- [A Beginners's guide to CNNs](https://adeshpande3.github.io/adeshpande3.github.io/A-Beginner%27s-Guide-To-Understanding-Convolutional-Neural-Networks/)
- [Inituitive Explanation of CNN](https://ujjwalkarn.me/2016/08/11/intuitive-explanation-convnets/)
- [Chris Olah's blog on CNNs](http://colah.github.io/posts/2014-07-Understanding-Convolutions/)
- Sample Handwritten Digit recognition Project using Keras tutorial [here](http://machinelearningmastery.com/handwritten-digit-recognition-using-convolutional-neural-networks-python-keras/).
- Great resource for computer vision tutorials that are easy to follow in Python [here](http://www.pyimagesearch.com/).

## Installation
To run the models and code make sure [Python](https://www.python.org/downloads/) installed. **All the setup should be done in the conda env as well as running the model**.

Clone the repo onto your local machine and cd into the directory.
```
git clone https://github.com/sujithv28/Behavioral-Cloning-Hacktorial.git
cd Behavioral-Cloning-Hacktorial
```

Make sure you have conda installed to make this setup easier. Create a new conda environment for this hacktorial in the repo.
```
conda create -n hacktorial python=2.7
source activate hacktorial
```

Install Tensorflow following the instructions [here](https://www.tensorflow.org/install/).
```
conda install -c conda-forge tensorflow
```

Install all the python dependencies:
```
pip install -r requirements.txt
```
Set Keras to use Tensorflow as backend:
```
python
import keras
quit()
nano ~/.keras/keras.json
```
Change your values to look something like:
```
{
    "image_dim_ordering": "tf", 
    "epsilon": 1e-07, 
    "floatx": "float32", 
    "backend": "tensorflow"
}
```
Also make sure you have OpenCV installed either through pip or homebrew. You can check if this works by running and making sure nothing complains:
```
python
import cv2
```
Download Udacity's training data and extract it to the main directory by running in the directory.
```
wget https://www.dropbox.com/s/3cwc2atg1qorzg4/data.zip?dl=0
unzip -a data.zip?dl=0
rm data.zip?dl=0
```

Download the simulator [here](https://github.com/udacity/self-driving-car-sim).

## View the Instructional Guide Notebook
To view the notebook run
```
jupyter notebook
```
and open [Model_Guide_and_Visualization.ipynb](/Model_Guide_and_Visualization.ipynb)

## Create training data
To create your own training data, open the simulator and select any track and the training option. All the data will be saved to the location you specify.

## Train the Model
To train the model run
```
python model.py
```

## Test Model on Simulator
To run your trained model on the simulator, open up the simulator application and start an autonomous session on either track. Then run in the env
```
python drive.py model.json
```

## Output
![Image of Nvidia Model](/images/self_driving.gif)

GIF from [here](https://medium.com/self-driving-cars/more-udacity-self-driving-car-students-in-their-own-words-193b99ee66eb).

## Nvidia's End to End Model:
Our model differes only slightly as we add maxpooling layers at the end of each convolution to speed up computation.
![Image of Nvidia Model](/images/nVidia_model.png)

## Other resources.
Here are some other great blogs written going over their approach to the Udacity Behavorial Cloning Project and explaining the logic behind their approach.
- [Udacity Self-Driving Car Nanodegree Project 3 — Behavioral Cloning](https://medium.com/udacity/udacity-self-driving-car-nanodegree-project-3-behavioral-cloning-446461b7c7f9#.9asxk3lyu)
- [How Udacity’s Self-Driving Car Students Approach Behavioral Cloning](https://medium.com/udacity/how-udacitys-self-driving-car-students-approach-behavioral-cloning-5ffbfd2979e5#.q00ni6o4j)
- [6 Different End-to-End Neural Networks](https://medium.com/self-driving-cars/6-different-end-to-end-neural-networks-f307fa2904a5#.ef5pz6i3f)
