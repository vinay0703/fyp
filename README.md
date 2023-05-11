# Fully end-to-end visual odometry Minidrone
[![Python3](https://img.shields.io/badge/python3-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/)

[![Tensorflow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)](https://www.tensorflow.org/)

[![MATLAB](https://img.shields.io/badge/MATLAB-SIMULINK-blue.svg)](https://www.mathworks.com/help/simulink/)

## Project Motivation
Using an airborne vehicle to explore an inside environment is a burgeoning topic, whether for equipment maintenance or greenhouse monitoring. Indoor aerial vehicles may play a key role in situations when human access is impossible. However, driving an aerial vehicle in an interior environment is difficult, particularly because the GPS sensor cannot provide positional information. This is where odometry might be useful; it aids in estimating the change in location by analyzing the change in sensor readings. Using sensor data such as an Inertial Measurement Unit (IMU), camera, etc., the approach estimates the change in position as the vehicle travels through space.


## Project Description
Design a visual-inertial odometry system for a tiny aerial vehicle using MATLAB and Simulink. 
Utilize the downward-facing camera on the DJI Tello Minidrone in conjunction with the 6-axis IMU data to construct the method that will enhance state estimates and replace the presently employed optical flow modeling approach.

## Libraries
These are few Libraries which have been used in this project.
```
djitellopy==2.4.0
et-xmlfile==1.1.0
numpy==1.23.4
matplotlib==3.6.3
numpy==1.23.4
opencv-python==4.6.0.66
openpyxl==3.0.10
pandas==1.5.1
pygame==2.1.2
tensorflow==2.12.0
scipy==1.10.1
```

## Installation

This entire project is developed in Ubuntu (Debian Linux) Operating System. Below installation steps are for Ubuntu OS. If you use another OS, then choose the alternative installation steps accordingly in "setup.py" file. 
```
1. Fork the repository and pull it into your local machine.

2. Install all the required packages by simply typing 
        "python3 setup.py install"
   in the terminal opened inside the root folder.

3. Setup the tensorflow-gpu in order to  make the prediction faster by typing the following commands
        conda install -c conda-forge cudatoolkit=11.8.0
        python3 -m pip install nvidia-cudnn-cu11==8.6.0.163 tensorflow==2.12.*
        mkdir -p $CONDA_PREFIX/etc/conda/activate.d
        echo 'CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
        echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
        source $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
        # Verify install:
        python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
   in the terminal opened inside the root folder.

4. Run main.py file from root folder by simply typing
        "python3 visual_odometry/main.py"
   in the terminal openend inside the root folder.
```
**Note:** 
- Step 2 will download the trained weights from the [GDrive link](https://www.mathworks.com/help/simulink/) and will place them in the "visual_odometry/files/Model_weights" location automatically. If any error occurs, do this step manually by downloading from the [GDrive link](https://www.mathworks.com/help/simulink/) and place them in the "visual_odometry/files/Model_weights" location.
- Step 3 is optional, but recomended for faster prediction since it uses GPU.

## Documentation
For more information about this project, read the [Thesis.pdf](https://drive.google.com/file/d/1-siPP2ZfyZjvaSePzHGXWjshNIiLmaMB/view?usp=share_link). 

## Implementation demo
This is for ConvNext model indoor prediction:


https://github.com/vinay0703/fyp/assets/68630619/f8c944d9-db4f-4544-a3d9-11303303f70f


## Contributing
Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.
If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star!
Thanks again!


### Authors
- [@vinay0703](https://github.com/vinay0703)
- [@utkarsh-vats-2000](https://github.com/Utkarsh-Vats-2000)
