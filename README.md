This repository contains python programs developed during iNTUition 5.0, a one-day hackathon held by NTU Open Source Society and iEEE Student Organization in Nanyang Technological University, Singapore. 

# Base website [here.](https://www.pyimagesearch.com/2017/04/24/eye-blink-detection-opencv-python-dlib/)

# Detailed information about this project on [DevPost!](https://devpost.com/software/blinkception)

# Installation instructions on Windows

1) Download the latest version of Anaconda from https://www.anaconda.com/download/

2) While installing, add Anaconda to PATH environment AND register Anaconda as default Python.

3) Open command prompt and execute the following instruction: 

```conda create --name opencv-env python=3.7 ```

4) After installing whatever it prompts you to install, activate the environment you just created with: 

``` activate opencv-env ```

5) Execute the following commands:

``` pip install numpy scipy matplotlib scikit-learn jupyter ```

``` pip install opencv-contrib-python ```

``` pip install cmake setuptools dlib ```

7) Now add the .dat file into the same directory as your project from https://github.com/AKSHAYUBHAT/TensorFace/blob/master/openface/models/dlib/shape_predictor_68_face_landmarks.dat

8) You are finally set! Run the program by executing the following command from your open cv environment:

``` python eyeControl.py --shape-predictor shape_predictor_68_face_landmarks.dat ```

Libraries for speech-to-text conversion and face-recognition: 

``` pip install pyaudio (for mac) ```

``` pip install SpeechRecognition ```

``` pip install face_recognition ```

### Made by [@RohanGautam](https://github.com/RohanGautam) , [@ShirleyHan6](https://github.com/ShirleyHan6) , [@laksh22](https://github.com/laksh22) , [@Atrik-Das](https://github.com/Atrik-Das)
