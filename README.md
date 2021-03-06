CarND · T1 · P1 · Lane Lines Detection Project
==============================================

[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/images/final.jpg" width="512" alt="Final result example." />


Project Overview
----------------

When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project you will detect lane lines in images using Python and OpenCV. OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images. You can develop your pipeline on a series of individual images, and later apply the result to a video stream (really just a series of images).

Check out the video clip `examples/videos/raw.mp4` (also contained in this repository) to see what the output should look like after using the helper functions provided in the started code:

<img src="examples/images/raw.jpg" width="512" alt="Preview of examples/videos/raw.mp4." />

Once you have a result that looks roughly like `examples/videos/raw.mp4`, you'll need to get creative and try to average and/or extrapolate the line segments you've detected to map out the full extent of the lane lines. You can see an example of the result you're going for in the video `example/videos/final.mp4`. Ultimately, you would like to draw just one line for the left side of the lane, and one for the right:

<img src="examples/images/final.jpg" width="512" alt="Preview of examples/videos/final.mp4." />


Project Structure
-----------------

The project structure has been changed a bit to have multiple files for multiple purposes instead of a single, massive Jupyter Notebook for all the code.

### `input` and `ouput`

Input and output `images` and `videos` for and from the image processing pipeline. The videos from the 5th project (Advanced Lane Lines Detection), have been as well to evaluate how this basic algorithm behaves with those other harder scenarios.

### `examples`

Example `images` and `videos`.

### `src`

Source files with the actual proposed solution, organised as follows:

- `helpers`: Individual `.py` files that will be used in the Jupyter Notebooks.
  - `imageProcessing.py`: Functions to process and transform the images in different ways (change color space, blur, Hough
    transform...).
  - `lineRegressorWithMemory.py`: Class that uses Linear Regression to extrapolate multiple lines, extracted using the Hough
    transform and already grouped in left or right, and averages it using the ones extracted previously.
  - `plot.py`: Helper functions to create grids for the images.
    
- `notebook`: Actual project code that will use all the functionality in `helpers` to create a lane line detection pipeline.
  - `dataExplorationAndParamCalibration.ipynb`: Notebook that uses multiple image processing functions with different params
    while plotting it's output, to help incrementally build the whole pipeline as the right param values are chosen for each
    step.
  - `videoProcessing.ipynb`: Notebook that will apply the final pipeline built in `dataExplorationAndParamCalibration.ipynb` 
    to the project videos.


Project Evaluation
------------------

The project's writeup can be found [here](WRITEUP.md).

According to the provided guidelines, a great writeup should provide a detailed response to the "Reflection" section of
the [project rubric](https://review.udacity.com/#!/rubrics/322/view) and include images to demonstrate how the pipeline
works. There are three parts to the reflection:

1. Describe the pipeline
2. Identify any shortcomings
3. Suggest possible improvements



Project Results
---------------

The results of the project can be found in YouTube:

1. [001 - Solid White Right](https://www.youtube.com/watch?v=7lb80iyGGQg)
2. [002 - Solid Yellow Left](https://www.youtube.com/watch?v=Z0tW4WkQuX4)
3. [003 - Challenge](https://www.youtube.com/watch?v=297dPtA9Dyo)
4. [004 - Advanced Project](https://www.youtube.com/watch?v=WwJK1KPRNBY)
5. [005 - Advanced Project Challenge](https://www.youtube.com/watch?v=kqs4HaXPYHM)
6. [006 - Advanced Project Harder Challenge](https://www.youtube.com/watch?v=IaIpqANF8XY)


Running The Project
-------------------

**If you have already installed the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) you should be good to go! If not, you can install the starter kit or follow the install instructions below to get started on this project.**

### Step 1: Getting setup with Python

To do this project, you will need Python 3 along with the numpy, matplotlib, and OpenCV libraries, as well as Jupyter Notebook installed. 

We recommend downloading and installing the Anaconda Python 3 distribution from Continuum Analytics because it comes prepackaged with many of the Python dependencies you will need for this and future projects, makes it easy to install OpenCV, and includes Jupyter Notebook. Beyond that, it is one of the most common Python distributions used in data analytics and machine learning, so a great choice if you're getting started in the field.

Choose the appropriate Python 3 Anaconda install package for your operating system <A HREF="https://www.continuum.io/downloads" target="_blank">here</A>. Download and install the package.

If you already have Anaconda for Python 2 installed, you can create a separate environment for Python 3 and all the appropriate dependencies with the following command:

    conda create --name=yourNewEnvironment python=3 anaconda
    source activate yourNewEnvironment

### Step 2: Installing OpenCV

Once you have Anaconda installed, first double check you are in your Python 3 environment:

    python
    Python 3.5.2 |Anaconda 4.1.1 (x86_64)| (default, Jul  2 2016, 17:52:12)
    [GCC 4.2.1 Compatible Apple LLVM 4.2 (clang-425.0.28)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    (Ctrl-d to exit Python)

run the following commands at the terminal prompt to get OpenCV:

    pip install pillow
    conda install -c menpo opencv3=3.1.0

then to test if OpenCV is installed correctly:

    python
    import cv2

### Step 3: Installing moviepy

We recommend the "moviepy" package for processing video in this project (though you're welcome to use other packages if you prefer).

To install moviepy run:

    pip install moviepy

and check that the install worked:

    python
    import moviepy

### Step 4: Opening the code in a Jupyter Notebook

You will complete this project in a Jupyter notebook. If you are unfamiliar with Jupyter Notebooks, check out <A HREF="https://www.packtpub.com/books/content/basics-jupyter-notebook-and-python" target="_blank">Cyrille Rossant's Basics of Jupyter Notebook and Python</A> to get started.

Jupyter is an ipython notebook where you can run blocks of code and see results interactively. All the code for this project is contained in a Jupyter notebook. To start Jupyter in your browser, run the following command at the terminal prompt (be sure you're in your Python 3 environment!):

    jupyter notebook

A browser window will appear showing the contents of the current directory. Click on the file called "P1.ipynb". Another browser window will appear displaying the notebook. Follow the instructions in the notebook to complete the project.
