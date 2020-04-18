# Samaritan

## Team Number: sdmay20-45

## Client/Advisor: Dr. Goce Trajcevski

## Team Members:

* [Kate Brune](https://github.com/katebrune) 
* [Ryan Goluch](https://github.com/rgoluch)
* [Ann Gould](https://github.com/gould-ann)
* [Thomas Paris](https://github.com/TJParis)
* [Saba Shaarbaf-Toosi](https://github.com/sabatoo) 

[Team Email](mailto:sdmay20-45@iastate.edu)

[Team Website](http://sdmay20-45.sd.ece.iastate.edu/)

## Table of Contents 

## 1. Introductory Material

TODO: write an introduction here

### 1.1 Acknowledgement

Samaritan Security is a self proposed project, and is available open sourced to the public under the *license name here* license.

## 2. Executive Summary

### 2.1 Development Standards and Practices Used

talk about the usual agile bullshit here, but also our git org/repo + using issues + prs 

### 2.2 Summary of Requirements

Samaritan has the ability to:

### 2.3 Applicable Courses from Iowa State Curriculum

The following courses from within the Iowa State Curriculum have given the development team the necessary skills to complete this project: 

- SE/CprE 414X
- DS 201
- SE/Com S 309
- SE/Com S 319
- CprE 489

### 2.4 New Skills/Knowledge Acquired Outside of University Teachings

*write book here*

## 3. Revised Project Design

### 3.1 Problem Statement

### 3.2 Proposed Solution

### 3.3 Operating Environment

### 3.4 Intended Uses and Users

### 3.5 Assumptions and Limitations

### 3.6 Relevant Standards

### 3.7 High Level Block Diagram

## 4. Implementation Details

### 4.1 Functional Requirements

### 4.2 Non-Functional Requirements

### 4.3 Modules

In the following sections, we will describe the key modules that make up our software. These modules consist, in a broad sense, of the Facial Recognition module, the Security Camera module, the back end API, and the front end React Client. At the start of our project, we had a lot of ideas as to what should be included in our final product and how we would be able to distinguish ourselves from anything else that was already on the market. There were some changes that needed to be made to what should be included in our product as it took slightly longer than expected to fully flush out our business plan as well as working around the loss of a team member. Ultimately though, we developed a list of the key modules to make up our minimum viable product (MVP). Documentation for the code discussed in these modules can be found [here](https://3.14.117.253/index.html).

#### 4.3.1 Facial Recognition Module

The Facial Recognition Module encompases the core functionality of our back end code. This module is made up primarily of the [RecogScript.py](https://github.com/samaritan-security/samaritan-backend/blob/master/RecogScript.py) and [FacialRecog.py](https://github.com/samaritan-security/samaritan-backend/blob/master/FacialRecog.py). The RecogScript is the *main* of our backend, where we first get all of the cameras that are connected to our system as well as all of the information on the people we have in the database. Then we loop through those cameras, collecting a frame from each camera and attempt to locate and identify any faces within the frame. This leads us into the FacialRecog file as where most of the heavy lifting of the back end takes place. Within the FacialRecog code, we process the encoded frame and person images to compare if there is a match, and if there is a match whether or not that person is known to the organization. From there, the data that is to be sent to the front end is built into a JSON object as the known and unknown matches are checked. While we are are building that JSON object we are also checking to see if there have been any alerts associated with a person as well as marking where they were last seen. This allows us to give security personell the ability to track people throughout the organization if there was ever a need to know where a person went in a building. 

This functionality of our Facial Recognition Module is aided in part by various technologies and libraries such as: [openCV](https://pypi.org/project/opencv-python/), [face-recognition](https://github.com/ageitgey/face_recognition), [NumPy](https://numpy.org/), and [ImageZMQ](https://github.com/jeffbass/imagezmq). 

#### 4.3.2 Security Camera Module

The code the comprises our Facial Recognition Module makes use of a large amount of code that enables us to tap into the camera feeds of an organization's security cameras. When working with an organization's security cameras, one of the assumptions made was that the cameras are running locally so to only allow access to security personell on the premises. In order to work around this assumption as well as allow our code to be scalable and accessible from anywhere for any given organization we came up with one of the unique features of our project; that is forwarding the local camera feeds onto an organization's backend infrastructure. Since our back end code is running remotely on an AWS EC2 instance, we implemented a forwarding script based off an example for a local forwarder script that can be ran on any computer or even a Raspberry Pi connected to the organization's network. 

This allows forwarder allows us to distinguish our product and appeal to organizations since there is no need to purchase or configure additional servers for each organization that uses our product. Additionally, it allows us to keep our code as specific as possible in order to implement our core functionality but also allows it to be configurable to each organization's cameras. 

#### 4.3.3 API



#### 4.3.4 React Client




## 5. Testing



### 5.1 Aspects of Samaritan Security that will be tested to validate correctness of project:

Samaritan uses Python Unittest and React's *insert framework name here* to validate the correctness of Samaritan. 

#### 5.1.1 Python Unittest

- API tests
  - Confirms databases work as intended through CRUD operations
  - Validates response Status Codes 
  - Validates contents of responses
  - Validates functionality of the API

- Facial recognition tests
  - Validates that the facial recognition works under numerous circumstances
  - Validates facial comparisons from "known" database
  - Validates TimeoutQueue is working 

- Blur detection tests
  - Detects blurry images through tests

- Usage of multiple cameras at once (Multiple camera tests)
  - Runs tests on different camera feeds and validates facial encodings

#### 5.1.2 React testing





### 5.2 Hardware and Software 

### 5.3 Functional Testing

### 5.4 Nonfunctional Testing









### Validates contents of responsesmultiple cameras at once 