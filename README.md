## About

This repository contains lab exercises for the [COMP0037 Robotic Systems](https://moodle.ucl.ac.uk/course/view.php?id=48839) module for undergraduate students undertaking the IEP Intelligent Systems Minor, delivered in Spring 2026. Exercises are designed to be attempted in the on-campus lab sessions on Friday afternoon, though you are free to do additional work in your own time if you wish.

Lab attendance will be monitored, but the exercises are **not graded**. You are welcome to discuss and help each other with these tasks and to ask for assistance and clarification from the TAs, but there is nothing to be gained by simply copying each others' work.

## Install the basic software infrastructure

We have tested the software and it runs natively on Windows 11 (10 untested), Mac (Apple Silicon, but we believe Intel should be okay) and Linux. We have run into problems running the code on WSL on Windows due to X-server authentication issues which will be fixed at some point.

* Install [Git](https://git-scm.com) (if you don't already have it).
* Install [Miniconda](https://www.anaconda.com/docs/getting-started/miniconda/main) (the precise version doesn't matter, but the code has been tested on Python 3.8 and above). Instructions for different operating system setups are provided.

In addition we highly recommend using Visual Studio code:

* Download [Visual Studio Code](https://code.visualstudio.com/), an easy-to-use editor.
* Install the [Python Plugin](https://code.visualstudio.com/docs/python/python-tutorial/) and test the hello world example.
* * Install [Ghostscript](https://ghostscript.com/index.html). For Windows, use the [64-bit binary AGPL release](https://ghostscript.com/releases/gsdnld.html). For Mac, use home brew and run ``brew install ghostscript``. For Linux, use ``apt install ghostscript``, ``snap install code --classic`` (or your preferred package manager).

## Install software to support this module and setup the virtual environment

For the next few steps, we'd propose doing the setup in the terminal. How this is configured depends upon the operating system you use. Check the [Miniconda](https://www.anaconda.com/docs/getting-started/miniconda/main) to see how to do this.

* Download the material from GitHub: [COMP0037 Robotic Systems](https://github.com/UCL/COMP0037_25-26) and put the lab material in a folder named, for example, "comp0037-labs":
    ```
    mkdir comp0037-labs
    cd comp0037-labs
    git clone https://github.com/UCL/COMP0037_25-26.git
    ```
* Open the cloned folder in Visual Studio Code: File > Open Folder > select the cloned repository folder
* Open a new terminal in Visual Studio Code and make sure you are in the folder 'comp0037-labs'
* Create and activate the environment:
    ```
    conda env create -f comp0037.yml
    conda activate comp0037-env
    ```
If conda gets stuck on "resolve dependencies" it might indicate a problem with your conda setup, particularly if you are using an existing conda setup on your system.

I found running:
    ```
    conda update
    ```
identified the error. In my case, I had to delete and reinstall conda.

## VS-Code Setup

This will probably vary a lot depending upon the setup for your machine. The main thing you need to do is make sure that the interpreter for the `comp0037-env` which you just created can be found.

* Select the Python interpreter. If you do not do this, then none of the packages you just installed will be recognized. There are the "easy" instructions (which did not work for me, version 1.85.1) and the harder ones.
    
* Easier: On the bottom right of your VS Code window you might see a "Select Interpreter" button or message, or the name of an existing Python interpreter that's being used
    * Click on message
    * A dropdown box will appear in the middle of the screen with all the known Python interpreters on the system
    * Select the one that says it is in the comp0037-env path

* Harder: Press <kbd>ctrl</kbd> + <kbd>shift</kbd> + <kbd>p</kbd>
    * In the dialogue box type ```python: select interpreter```
    * Use the file browser (which might open _behind_ the edit screen), navigate to the ```comp0037``` directory and select ```bin/python```
    * There is no visual update ot say the interpreter has worked but the dependencies seem to be in place.
