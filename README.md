This repository contains python programs developed during iNTUition 5.0, a one-day hackathon held by NTU Open Source Society and iEEE Student Organization in Nanyang Technological University, Singapore. 

## Inspiration
What starts with weakness in limbs soon progresses to muscle degeneration, which can rob a person’s ability to walk or use one’s arms. As of 2015, this is the harsh life of over 200,000 ALS patients. Similar conditions affect the day to day functioning of numerous physically disabled people around the world. 

We wished to try and lessen their difficulties. The first idea we thought of was to make their web experience  as seamless as possible. Since the nerve degeneration starts from below the neck, we thought of using Computer Vision to allow users to navigate websites completely hands-free using just their facial movements as captured by their webcams. We therefore built a web control and a typing interface, bundled with a SOS hot key (pattern) for emergencies.

## What it does
Our project is a python program which enables users to interact with websites using just their facial movements such as eye blinks, eyebrow raises, and mouth opens. By using these movements, they can interact with buttons, dropdowns, slideshows, text fields and other web elements. 

Users are able to type text using a set pattern of facial gestures. These patterns are mapped to morse code and the output is shown in the form of text.

Additionally, our program employs facial recognition to remember previous users and is able to run using the pre-saved ratios of their facial features. This means that our software can be used by multiple users. 

Finally, we allow the users to send emergency Emails and WeChat messages. Once the webcam detects no facial patterns for 10 seconds, an emergency message is broadcasted to all their preferred contacts. This is especially useful if people with disabilities happen to face an accident.

## A few screenshots(hover for brief explanation):
![initial testing phase](https://user-images.githubusercontent.com/17317792/46990372-977eb180-d133-11e8-9a7d-796a9a8194a6.png "initial testing phase")
![setup process part one](https://user-images.githubusercontent.com/17317792/46990487-170c8080-d134-11e8-9542-e5453dcdb2fa.png "setup process part one")
![Final control interface](https://user-images.githubusercontent.com/17317792/46990488-17a51700-d134-11e8-969b-d6136c0eb9c6.png "Final control interface")

## How we built it
### Facial Recognition
We use an [existing library](https://pypi.org/project/face_recognition/) for implementing facial recognition of the user. This is used to verify and use pre saved thresholds unique to each user. For the blink, eyebrow raise and mouth open detection, we use a pre trained model that takes in a video frame and returns a list of 68 (x,y) coordinates of the facial landmarks detected. We then perform computations on this data to get the respective thresholds and record changes to trigget an evev.
### Morse Code Decipher
The typing process consists of registering a blink as a dot and an eyebrow raise as a dash. Once the user is satisfied with the current pattern typed, they can open their mouth to enter the string into our decipher function. Thus a sequence of these operations can be used to interpret Morse code and type a complete message. 
###WeChat and Email
The WeChat message is sent using WeChat API, itchat. An emergency message is sent after a user to logs in by scanning the QR code. 
The email is sent using Python’s smtplib library which provides backend features for handling the sending and receiving of emails from one account to another.
### Website
The demo website was made using Materialize which is a CSS library very similar to Google’s renowned Material Design. There are multiple interactive elements which have classes such as ```bc-button``` or ```bc-1```. These help the web control script identify the list of interactive elements and how to interact with them. The [website](https://laksh22.github.io/blinkception-site/index.html) was hosted using GitHub pages.
###Web automation
Selenium was used for web automation. It is used to choose the next “bc-” element and scroll to it. A separate function decides the type of element it is and how to interact with it accordingly. 


## Challenges we ran into
1. Finding a way to take morse code input and show the live changes in the input field.
2. Recognising new faces in different lighting conditions
3. Setting sensitivity thresholds for different facial gestures
4. Merging the web automation and facial recognition software into a logical program flow

## Accomplishments that we're proud of
1. We were able to design functions to identify, iterate through, highlight and interact with specific elements using Selenium.
2. We were able to implement facial gesture recognition only using the desktop’s webcam and without the use of any other external hardware such as LeapMotion. 

## What we learned
1. How to find elements and interact with them in a website through web automation using Selenium.
2. How to implement a seamless and feasible workflow between numerous code modules.
3. How to do facial recognition using OpenCV and optimise parameters.
4. How to implement a pre-trained model.

## What's next for BlinkCeption
1. Adding an autocomplete function using NLTK to the morse code input.
2. Improving accuracy of gesture detection.
3. Finding a method to adapt the scripts to all websites - or to provide easy steps to integrate the system into existing websites.
4. Adding browser control - switching tabs, opening settings, opening history, etc.
5. Switching between pages on the same website


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

### Devpost for this project is [here.](https://devpost.com/software/blinkception)
### See Blinkception on the winner list [here!!!](https://intuitionv5.devpost.com/submissions)

### Made by [@RohanGautam](https://github.com/RohanGautam) , [@ShirleyHan6](https://github.com/ShirleyHan6) , [@laksh22](https://github.com/laksh22) , [@Atrik-Das](https://github.com/Atrik-Das)
