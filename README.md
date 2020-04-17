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

Samaritan is a security system that is designed to ease the stresses and complexities of monitoring your business or company. Security is one of the top priorities that any company will have, because of the need to protect valuable company assets and goods. What is exhausting about this, however, is that monitoring these assets take time, effort, and money. The goal of Samaritan is to help make the duanting task of securing your company easier.

Samaritan is intended for business or company usage. The main scenario we are considering is identifying and alerting when an unknown person has entered a secured area in the business area. To cater to such settings, we developed Samaritan to include facial recognition capabilities that will allow it to, in real time, alert the user if anyone other than a registered employee has entered the company office. Samaritan could be expanded and catered to more specific settings, however, this is the scenario under which the project was initially conceptualized.

### 1.1 Acknowledgement

Samaritan Security is a self proposed project, and is available open sourced to the public under the *license name here* license.

## 2. Executive Summary

In this section, we will go more into depth relevant standards used to develop this project, and also go into more depth on what practices were used specifically and how they were utilized. We will also cover how classes taught at Iowa State helped prepare us to succeed in the development of this project.  In addition, we will cover some of the main features and requirements that Samaritan accomplished. 

### 2.1 Development Standards and Practices Used

This project was developed using an Agile development strategy and test driven development (TDD). We first started with the planning stage of Agile by holding weekly meetings with both our project advisor and the team in order to break the project into smaller user stories and gather information relevant to those stories. Weekly advisor meetings helped scope the vision of our project and narrow down our requirements. During the second semester, these meetings were held online. It proved to be extremely useful during the transition to online work during the end of our project. 

Sprints were broken up into 2-week increments, and furthermore broken down into front-end and back-end requirements. After each weekly meeting, we assigned tasks to developers based on the sprint retrospective. We utilized Github to host our repo and also our project backboard. In order to ensure accuracy of code, we also utilized code reviews. Code reviews were done both online Github (by submitting pull-requests), and also in-person during our weekly meetings.

### 2.2 Summary of Requirements

The requirements of the project can be summarized in the following list. The system must be able to: 

- Display camera feeds to the user

- Recognize if it knows a person or does not know a person

- Alert the user when it recognizes someone who is unauthorized

- Central dashboard for viewing camera feeds

- Ability to add new users to database

Collectively these requirements define the intended functionality of our system. These requirements are intended to be viewed as the generalized requirements of our system with the intent that our software will be able to run on any pre-existing hardware. 

### 2.3 Applicable Courses from Iowa State Curriculum

The following courses from within the Iowa State Curriculum have given the development team the necessary skills to complete this project: 

- SE/CprE 414X
- DS 201
- SE/Com S 309
  - This project-based class gave an in-depth look into Agile development practices by allowing students to come up with a self-proposed project and to develop it from start to finish. This class is probably the most relevant skills to complete Samaritan because of the hands-on skills we gained from creating a self-proposed project from start to finish
- SE/Com S 319
  - In a similar fashion to Com S 309, SE 319 taught students about Agile development but rather in a smaller scale. This solidified our development practices and gave us skills to write better code and to work as a team on a smaller scale
- SE/Com S 329
  - This course covers project management which gave us the necessary skills to plan and work together as a team on a project of such a large scale
- CprE 489

### 2.4 New Skills/Knowledge Acquired Outside of University Teachings

The following list briefly covers some of the skills that were acquired throughout the development of this project that have not been formally taught: 

- Backend development in Python
  - **<u>insert stuff here about backend cuz idk exactly what ya'll used</u>**
- Frontend development with React
  - Utilized TypeScript instead of JavaScript because TypeScript allows for more productive development as it includes features such as static checking
  - For component building, Storybook was used. Storybook allows rendering of each individual React component so that development may be done in smaller, incremental chunks without having to deal with components that aren't relevant to the current sprint
  - Ant Design was also utilized for basic front-end design

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

In the following sections, we will describe the key modules that make up our software. These modules consist, in a broad sense, of the Facial Recognition module, the Security Camera module, the back end API, and the front end React Client. At the start of our project, we had a lot of ideas as to what should be included in our final product and how we would be able to distinguish ourselves from anything else that was already on the market. There were some changes that needed to be made to what should be included in our product as it took slightly longer than expected to fully flush out our business plan as well as working around the loss of a team member. Ultimately though, we developed a list of the key modules to make up our minimum viable product (MVP). Documentation for the code discussed in these modules can be found [here](https://3.14.117.253).

#### 4.3.1 Facial Recognition Module

The Facial Recognition Module encompases the core functionality of our back end code. This module is made up primarily of the [RecogScript.py](https://github.com/samaritan-security/samaritan-backend/blob/master/RecogScript.py) and [FacialRecog.py](https://github.com/samaritan-security/samaritan-backend/blob/master/FacialRecog.py). The RecogScript is the *main* of our backend, where we first get all of the cameras that are connected to our system as well as all of the information on the people we have in the database. Then we loop through those cameras, collecting a frame from each camera and attempt to locate and identify any faces within the frame. This leads us into the FacialRecog file as where most of the heavy lifting of the back end takes place. Within the FacialRecog code, we process the encoded frame and person images to compare if there is a match, and if there is a match whether or not that person is known to the organization. From there, the data that is to be sent to the front end is built into a JSON object as the known and unknown matches are checked. While we are are building that JSON object we are also checking to see if there have been any alerts associated with a person as well as marking where they were last seen. This allows us to give security personell the ability to track people throughout the organization if there was ever a need to know where a person went in a building. 

This functionality of our Facial Recognition Module is aided in part by various technologies and libraries such as: [openCV](https://pypi.org/project/opencv-python/), [face-recognition](https://github.com/ageitgey/face_recognition), [NumPy](https://numpy.org/), and [ImageZMQ](https://github.com/jeffbass/imagezmq). 

#### 4.3.2 Security Camera Module

The code the comprises our Facial Recognition Module makes use of a large amount of code that enables us to tap into the camera feeds of an organization's security cameras. When working with an organization's security cameras, one of the assumptions made was that the cameras are running locally so to only allow access to security personell on the premises. In order to work around this assumption as well as allow our code to be scalable and accessible from anywhere for any given organization we came up with one of the unique features of our project; that is forwarding the local camera feeds onto an organization's backend infrastructure. Since our back end code is running remotely on an AWS EC2 instance, we implemented a forwarding script based off an example for a local forwarder script that can be ran on any computer or even a Raspberry Pi connected to the organization's network. 

This allows forwarder allows us to distinguish our product and appeal to organizations since there is no need to purchase or configure additional servers for each organization that uses our product. Additionally, it allows us to keep our code as specific as possible in order to implement our core functionality but also allows it to be configurable to each organization's cameras. 

#### 4.3.3 API

The API module consists of Samaritan's CRUD API, which allows for us to bridge functionality between the Facial Recognition module and the Security Camera module with our front end. Additionally, the API is where the client for MongoDB support is hosted and is responsible for database retrieval/posting functionality. If separate modules need to adjust contents in the database, they make an internal call to ```app.py```, which also hosts the Flask setup and is where HTTPS calls are made. Having an API allows for a smoother transition for communication between the backend and the front end.

The API uses [Flask](https://pypi.org/project/Flask/) to create the CRUD functionality and [PyMongo](https://pypi.org/project/pymongo/) + [MongoEngine](https://pypi.org/project/mongoengine/) for the database functionality to [MongoDB](http://www.mongodb.org). We chose using a NoSQL database to focus on scalability of Samaritan, and because our product does not require the utilization of schema (Samartian does not require lots of JOINS for example).

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









### Concluding Material 

### 6.1 Conclusion

Securing company assets is a timely and expensive business. Companies need to monitor their office space and goods in a timely and efficient manner, which can often prove to be difficult with the current market standard. Samaritan Security aims to ease these issues by providing a seamless automation security system that can be added on to any current company security system for an added layer of security.

Samaritan utilizes features such as facial recognition to ensure that only employees and authorized guests are allowed to enter the facilities that are being monitored. Samaritan does this by matching people's faces spotted on the camera feed with the company’s database of known people and employees to distinguish if someone caught on the premises is authorized to be there. By moving this detection process to an automated system, the company removes an element of human error from their security, making it more efficient and secure.

### 6.2 Recommendation for Future Work

In the future Samaritan can be improved with a feature that helps track the movements of unidentified people. As an unknown person moves from one area to another, the separate cameras pick up the same person and send separate alerts. Samaritan could be made to record more information about the unknown person and record where that person is moving. Another feature that could be added to Samaritan is additional protection against people wearing masks or any other facial obstructions. A feature to help Samaritan recognize a person without being able to see their face would allow the system to flag an individual as an unknown person without being able to see their face. It is important to note that this feature should only be used to flag people as unknown. A confirmed match through the facial recognition should be the only way the system flags someone as a known person, and thus does not send an alert.