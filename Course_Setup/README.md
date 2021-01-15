# CS 4475/6475 Computational Photography: Course Setup

## Instructions

This course setup document is designed to help you get started in the course during the start of the semester. This is not a graded assignment, but it is important that you complete it by the end of the second week of the semester at the latest. Do not wait until Assignment0 to start setting up your environment, otherwise you might waste time trying to resolve any technical issues. 

For this course setup, you will perform the following:
#### 1. Review the Syllabus and Schedule on the Course Website
#### 2. Confirm you have access to the course Canvas and Piazza
#### 3. Clone the course repository
#### 4  Set up the course python3 environment
#### 5. Log in to Gradescope 
#### 6. Log in to Peerfeedback
#### 7. Log in to Overleaf - LaTeX report tool
#### 8. Review Course Policies and GT's Honor Code and take the Plagiarism Quiz
#### 9. Take the Exemplary Report Permission Quiz
#### 10. Cameras, Tripods and EXIF data
#### 11. Complete Assignment 0 
#### 12. Complete Notebook 1 and Quiz 1

## 1. Review the Syllabus and Schedule on the Course Website

It is very important that you review the [CS 4475/6475: Computational Photography Course Website](https://omscs6475.cc.gatech.edu). This site has all of the course information, including the course syllabus, complete course schedule, and required reading materials. If you have any questions regarding any of the information on the website, please ask on Piazza.

## 2. Confirm Canvas and Piazza Access 

Review the [Course Policies, Section 3F: Official Course Communication](https://omscs6475.cc.gatech.edu/course-syllabus/) for important information regarding Piazza.  

**Canvas** - If you have not already, please check that you have access to CS-6475-001 on Canvas. This is the Canvas for both Atlanta on-campus and OMSCS students. If you just enrolled in the course, it might take some time for you to see the course in Canvas, so give it a couple days. If you still do not see the course after waiting, message the Instructors on Piazza.

**Piazza** - Make sure that you have access to the course Piazza. We will add site access for folks who are registered for this class via the GT Registrar. You should have received an invite from Piazza to your gatech.edu email address. Please make sure that your first name, last name, and email address on Piazza match the info we have with GA Tech. This is IMPORTANT as we need to match you across these two systems. We will remove folks who do not match with Canvas after the add/drop deadline.

We will be re-syncing the Piazza roster multiple times during the next week to get students added and we will finalize the roster at the end of the first week once the registration deadline has passed. If you logged into Piazza using a different email address than the GaTech one listed on ou course roster, you will probably be dropped from Piazza, and you will have to rejoin. To avoid this, **include your primary GaTech email address first, and then link multiple email addresses to your GaTech account under Piazza's Account/Email Settings, located by clicking on the gear on top right of Piazza**.  

Once you have access to Piazza, go ahead and introduce yourself!

## 3. Clone the Course Repository

Throughout the course, assignments and projects will be released via the course GitHub repository. To clone the course repository to your local machine, make sure you have [Git](https://git-scm.com/downloads) installed and the executable is on your system PATH. You can verify that you have Git installed and on your system PATH by executing the command `git --version` from a terminal. Clone the repository by issuing the command `git clone https://github.gatech.edu/omscs6475/assignments.git`.

Note: If you want to use the Git repository locally to track your changes, you should checkout a new branch immediately after cloning: `git checkout -b <branch>`. See [here](https://git-scm.com/docs/git-checkout) for more information on git-checkout. 

#### Receiving Updates

Updates can be retrieved by running `git pull` in the root directory of the repository from either your host or VM terminal. You should regularly pull and merge from the remote to ensure you have the most up-to-date commits. It is important to pull the latest changes when an assignment/project is released, or when the Instructors make an announcement that there have been updates. See [here](https://git-scm.com/docs/git-pull) for more information on git-pull.


## 4. Set up the Virtual Environment

This course uses several third-party libraries (NumPy, SciPy, OpenCV, etc.) for assignments and projects. In order to standardize the execution of your code between your local environment and the remote autograding environment, we provide the specification for an Anaconda virtual environment that includes the correct version of all required software and libraries.

**NOTE: ALTHOUGH THE CONDA ENVIRONMENT HAS BEEN TESTED FOR CROSS-PLATFORM COMPATIBILITY WITH THE AUTOGRADER ENVIRONMENT, THE CONDA ENVIRONMENT IS NOT THE EXACT ENVIRONMENT YOUR CODE IS RUN IN BY THE AUTOGRADER. YOU ARE RESPONSIBLE TO ENSURE YOUR CODE WORKS ON THE AUTOGRADER SYSTEM. IT IS NOT ENOUGH THAT IT WORKS ON YOUR SYSTEM IN THE CONDA ENVIRONMENT.**

- This course uses Python 3.6, so download and install the latest Python3 supported version of Anaconda for your OS [here](https://www.anaconda.com/download) (scroll to the bottom to see the list of installers). Do NOT download a Python2 version. Downloading the latest Python3 version of Anaconda and creating an environment with the `cs6475.yml` (which specifies Python 3.6), should work. 

**Resources:** Anaconda Documentation for installation on [Windows](https://docs.anaconda.com/anaconda/install/windows/), [macOS](https://docs.anaconda.com/anaconda/install/mac-os/), and [Linux](https://docs.anaconda.com/anaconda/install/linux/)

- From the local course repository directory you created when you cloned the remote, create the CS6475 virtual environment by running `conda env create -f cs6475.yml`.

You can then activate the CS6475 virtual environment from a terminal by executing the following command:

```
~$ conda activate CS6475
(CS6475) ~$
```

**NOTE 1:** `conda activate` and `conda deactivate` only works on conda 4.6 and later. For conda versions prior to 4.6, Linux and macOS users should use `conda source activate` and `conda source deactivate`.

**NOTE 2:** If, for whatever reason, your initial CS6475 environment gets messed up and you need to recreate it again, make sure that you remove the environment first by running `conda env remove --name CS6475`. 

**Resource:** Anaconda Documentation - [Creating an environment from an environment yml file](https://conda.io/docs/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file)

Once the virtual environment has been activated, you can execute code from the same terminal. It's worth mentioning that popular Python IDEs, such as PyCharm, VSCode or Atom, facilitate using an Anaconda environment as the interpreter for your project or repository. This course setup will not go over those steps, as they will vary from tool to tool.


### Validate Environment Setup

You can test that your environment is setup correctly by opening a terminal, activating the virtual environment, and running the `test.py` file in the root folder of this repository. The test file performs basic checks to confirm that the required versions of all packages are correctly installed.

```
~$ source activate CS6475
(CS6475) ~$python3 test.py
.....
----------------------------------------------------------------------
Ran 5 tests in 0.272s

OK
```

**NOTE:** While we encourage students use the provided virtual environment, some prefer to manage their own environment. We will not provide support for students who choose to do so, but in any event, we are providing the list of libraries and their respective version numbers that you will use for the assignments. These libraries are packaged with the Anaconda environment, so only students who choose to use their own environment will need to adhere to this list. You will need the following libraries **and any dependencies**:
- Python 3.6
- MatPlotLib 3.0.0
- Nelson 0.4.2
- OpenCV 4.0.0.21
- NumPy 1.15.2
- SciPy 1.1.0


## 5. Log in to Gradescope 

Log in to [Gradescope](https://www.gradescope.com/) using your GT username and password and you should be able to see the course listed in your dashboard. This might take a 3-4 days to take effect if you were just enrolled into the course, so be patient.

We will be using Gradescope to process assignment/project submissions in this course. Each assignment/project will normally require submission of a report and resources (code files, images, etc). The report will be submitted separately from the resources, each under its corresponding assignment on Gradescope. When you submit code to the Gradescope autograder, you should be able to see the output of the autograder within a few minutes. Each assignment/project will have submission instructions, so make sure you pay really close attention to them.


## 6. Log in to Peer Feedback

Log in to [Peer Feedback](https://peerfeedback.gatech.edu/app/home) with your GT username and password and make sure that you are able to see this course. You will be assigned Peer Feedback tasks starting with Assignment 1. The Instructors normally assign Peer Feedback after an assignment closes (usually after the 2-late day submission deadline passes). A Piazza announcement will be made when Peer Feedback is released for each assignment/project. 

Instructions on Peer Feedback tasks for this course are given on the course website [here](https://omscs6475.cc.gatech.edu/peer-feedback/). 


## 7. Log in to Overleaf Professional for LaTeX reports

Your assignment and project reports will be formatted in LaTeX, in the same style as technical papers. The TeX format provides a small font with plenty of writing space and compact image handling.  No other format will be accepted. We will provide a detailed template for each assignment via the GitHub repository to make this easier for you and the TA graders. If you already use a TeX program that you like, you may continue to use it with our templates. 

If you have never used LaTeX, Georgia Tech has a contract with Overleaf, and a free Overleaf Professional account is available for each student. Overleaf is an online program with excellent help available that can be sync'd with Dropbox, provides storage, and retains your version history. [Access Overleaf here.](https://www.overleaf.com/edu/gatech) 

### Registering for a Professional Overleaf Account through Georgia Tech
1. Register using your ___@gatech.edu email: [Access GaTech overleaf from the Register or Sign Up buttons](https://www.overleaf.com/edu/gatech) 
2. Respond to the confirmation email that is sent to your GaTech email after registering.
3. Done! 

### Importing a Report Template into Overleaf 
Upon creating your account, you will have a welcome page (left) with a button to **Create First Project** or if you already have an account, you may have the normal dashboard with a button to create a **New Project**. 

Select **Create First/New Project → Upload Project**. 

This opens a window asking for a .zip file. Upload the *assignment0-Introduction_template_term.zip* provided for A0-Introduction in the repo. Always use this term's report template, they change each term. You can keep a clean copy in Overleaf by immediately making a copy, since you may overwrite code or information. After Overleaf finishes uploading you should see the template project in your menu; click on it and take a look at your report! 

For more information on how to use specific LaTeX commands, please refer to the official user guide [here.](https://www.latex-project.org/help/documentation/usrguide.pdf)


## 8. Review the Course Policies and Georgia Tech's Honor Code and take the Plagiarism Quiz

We take Academic Integrity very seriously and it is very important that our students understand the [Course Policies](https://omscs6475.cc.gatech.edu/course-syllabus/) (see Section III of the Course Syllabus) and [Georgia Tech's Honor Code](https://osi.gatech.edu/content/honor-code). Once you review the information, take the Plagiarism Quiz on Canvas. This graded quiz has about 16 multiple choice questions with an aim to help students understand our policies in depth. The scenarios have all occurred in this class over time. You are allowed unlimited attempts, open sources, and only your highest score will count towards your participation grade. See the Course Schedule or Canvas for the quiz's due date.

The Instructors will make an announcement on Piazza once the Plagiarism Quiz is available on Canvas. 

## 9. Take the Permission Quiz on Canvas

After we finish grading the assignments, we will pick a few reports and share them as Exemplary Reports on Canvas. In the past, before work was shared, we had to email every student in order to get permission, which delayed the sharing of the reports immediately after grades were released. 

To make things easier and faster, we need you to complete a “Yes/No” quiz that will give our entire CS6475 staff permission beforehand to share any of your assignments and projects with the class, if chosen. If you are not comfortable sharing your reports with your peers, do not hesitate to select “No”. You will not be penalized. If, for whatever reason, you select “Yes” in the quiz, but then you change your mind for a certain assignment or project and want your work removed from Canvas, if chosen, please message the Instructors on Piazza and your report will be removed immediately. If you select "No" or do not take the quiz at all (we assume the answer is "No" if you don't), but change your mind later on and wouldn't mind having your work shared, if chosen, feel free to take the quiz again.

**This quiz is ungraded and already available on Canvas. You can access this quiz by going to Canvas → Quizzes and it will show up under "Surveys".**

After the semester is over, we will not share your work in future semesters.  
 
## 10. Cameras, Tripods, and EXIF Data

You are allowed to use any kind of camera  -- anything from smartphones to high-end DSLR cameras -- for this class. Many students have successfully completed assignments using only a smartphone, so do not feel that you need to go and buy a fancy camera (although many students have used this class as an excuse to buy the camera of their dreams). 

### Required Manual Controls
Many assignments have specific setting requirements for **aperture, exposure time, and ISO.** Information is available online on camera settings, so we expect you to find it for your device. You will need to be able to manually control exposure time, aperture and ISO for several assignments. There are apps that can help smartphones, but since apps constantly change, we cannot make much recommendations for them. Feel free to share names of apps with your classmates on Piazza.

  - Exposure time in seconds (ex: 1/2000 s, 1/30 s)
  - Aperture (ex: f 2.8, f16) 
  - ISO (ex: ISO 100, ISO 1600)

### EXIF Metadata
To help you get used to your camera and its settings, you will be asked to provide some technical information about your photograph on A0. You should immediately find out how to get the EXIF data for the camera you plan to use in this course. 

EXIF data is recorded as a part of digital images, and can generally be found on your phone, in your digital camera, or on your computer. Image editing can affect the data, so record the settings before playing with your image. Search online for information on finding EXIF data for your device if you are not sure how to find it or do not know what it is. You can also discuss EXIF data and where to find it on Piazza.

**Location privacy:** When including or sharing images, make sure there are no data contained in the EXIF metadata that you do not want shared (i.e. GPS). If there is, make sure you strip it out before submitting your work or sharing your photos with others. You may use the python [pypi-exif](https://pypi.org/project/exif/) library to write a python file to strip GPS data if you wish.  Make sure you do not use an app that strips all EXIF from the image. 

### Required Stable Camera Position: Tripods or Supports
Some assignments require long exposures or keeping the camera motionless between successive shots, which is challenging. Learning to use your time delay feature will help prevent camera motion during individual shots. You can either use a tripod or an improvised support. Students have successfully created homemade tripods to stabilize their smartphones if they did not have a tripod.  Google homemade camera tripods for ideas, or check shopping site prices for bargains. Discuss your ideas and sources on Piazza. 

It is harder to improvise for larger cameras and DSLRs. There are bargain tripods that work reasonably well, or try to borrow one.  You may be able to improvise something with ingenuity. 

## 11. Complete Assignment 0

This is a short introductory assignment to help you become familiar with the course submission process. You will be required to write some python code, create a report using a LaTeX template, and submit both your report and resources to Gradescope. It is very important to get Assignment 0 completed ASAP before starting on Assignment 1.

The Instructors will make an announcement on Piazza once Assignment 0 is released.

## 12. Complete Notebook 1 and Quiz 1

This notebook introduces some key aspects of the NumPy and OpenCV APIs as they relate to image manipulation. These techniques are building blocks that can be used extensively throughout the course. Although there are no deliverables for these notebook exercises, there is a **graded Canvas quiz** (see course schedule for due date). You are free to discuss the notebooks on the forums, but make sure that you refrain from giving away quiz questions and answers. **We cannot recommend enough that you start on this first notebook immediately because it can be a great reference for the assignments/projects in this course. If you are unfamiliar with python, reviewing Notebook 1 alongside Assignment0 may be very helpful.**

The Instructors will make an announcement on Piazza once Notebook 1 and its corresponding quiz is released.
