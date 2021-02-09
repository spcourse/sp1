# Python on your own computer

To be able to program on your own computer you need a couple different programs:

1. **Anaconda**, a version of Python that is easy to install. There are *a lot* of packages included, which contain functionalities for graphs, statistics and a host of other features.

2. **Atom**, an *editor* to write code in. This is, in a way, just a text writing program, but specifically meant for programming code. For example, it highlights particular parts of your code in specific colors, so can more easily distinguish which part of your code does what.

3. Finally, you will need a *command line interface* from which will provide you with methods to start and interact with your programs. One comes pre-installed with macOS, but Windows users will need to install one.

Stuck? Consult an assistant!

### Step 1: Anaconda

This package can be downloaded at their [website](https://www.anaconda.com/download/). Choose to download the "**Graphical Installer**" for the latest **Python-version**. The download is over 500MB large, so it could take a while before it's done! _You do not need to provide your mail address, even without it you're allowed to use Anaconda._

![Choose the "Graphical installer" for the latest Python version](download.png){:style="max-width:35%"}

As soon as the download is finished, you have to execute the downloaded file (double click?). Follow the installation instructions and choose "Install for me only" where you can; if everything is okay you don't need to alter anything else.

**Note: for Windows always choose the "advanced" installation and tick the following box! If you did not, you have to reinstall anaconda!**

![Tick the box: "Add to PATH" when installing Anaconda](anaconda_vinkje.gif)

The installation can take a while.

![](wait2.gif){:style="max-width:25%"}

### Step 2: Atom

This package can be downloaded at their [website](https://atom.io/). Once again you have to execute the downloaded file. This time though you do not have to alter any settings during the installation process. Are you on a Mac? Just move the file to your applications folder. From there you can simply run it.

### Step 3: Command Line Interface

As a programmer, you will be using a command line interface (also often called terminal or shell) frequently. Through your terminal, you will be able to start and interact with programs, view outcomes of code you've written, and otherwise interact with your computer. What to do now depends on whether you work on a Mac or a Windows machine:

On Mac, the terminal is included with the Operating System, and comes pre-installed. You will be able to open a terminal by clicking on Spotlight (the small magnifying glass) in the upper right corner of your screen, and typing "Terminal" then pressing enter. No further actions are required for this step.

On Windows, it is slightly more complicated and you will want to download and install Git Bash using the [instructions from this website](https://www.stanleyulili.com/git/how-to-install-git-bash-on-windows/). After installation, you will be able to open a terminal by clicking the windows button in the lower left corner, and typing "bash" then pressing enter.

Navigating through your computer using the command line will be a vital skill. Watch the video below to get more familiar with command line commands (_ignore any mentions of nano, as we will be using the much more user-friendly Atom to edit our files_):

![embed](https://www.youtube.com/embed/aKRYQsKR46I)

### Quick installation test

To test whether each of our steps has gone correctly, we will write a small program named "hello". Open Atom and create a new file named `hello.py`. In this program, place the following code:

	print('Hello, world!')

Save your program in a folder that is easily accessable (we recommend you create a folder that will contain all your code from here on out) and open a terminal.

Using your terminal, navigate to the folder containing the file `hello.py`. Remember, use `cd` to change directory, `pwd` to print your current directory, and `ls` to verify that `hello.py` is in the folder you are currently in. Now, run the following command:

	python hello.py

If everything was done correctly, your command line will now show the text `Hello, world!`. Congratulations on your first program!

### Install `checkpy`

To help you verify whether a program functions in compliance with the specifications of an assignment, we have written a program of our own called **checkpy**. This program can be installed from a terminal using the following command (make sure to have Python and PiP installed):

	pip install checkpy

This can take a while and you will see some text move over your screen. Afterwards `checkpy` is installed. In addition `checkpy` we also need the tests that correspond to the assignments that you'll have to make. These tests can be downloaded by executing the following command in the terminal:

	checkpy -d uva-sp/sp1

To test whether your installation of `checkpy` was successful, you can test `hello.py`. If you haven't written that program yet, check out the introductory video above. Then execute the following command:

	checkpy hello

Is everything colored green and do you see only happy smileys? That means you've done a-okay, and that you've met our requirements for the assignment! Should there still be some red smileys, no worries! Carefully examine your code and verify it with each of the specifications. And don't forget you can always send us an email if you're stuck.

### Install other Python libraries

During the course, we will use some other Python libraries. We will download and install all these libraries through conda and place them in their own "environment". This makes sure that everything will work for all the exercises in the coming courses.

First, open a terminal and run the following command:

    conda init bash

This will instruct your terminal to list the current Conda environment it is in. Close the terminal, and open a new one. This will make sure that everything is started correctly. To verify this, you can see if your terminal shows something like `(base)` in front of every line.

Now, with your new terminal, run the following commands:

	curl https://pdp.mprog.nl/course/python/en/installing/computer/environment.env > environment.yml
	conda env create -f environment.yml
	rm environment.yml


This downloads a formatted description of what libraries to download and install, then installs the libraries, and then removes the description (as we no longer need it).

From here on out when you open a terminal we can use the following command to enter the environment, and enable the use of all the libraries we installed:

    conda activate progLab

If everything worked, you will now see that your terminal shows `(progLab)`. 

**Important:** If you want to use all of the libraries you've just installed and `import` them in your own code, you will have to have *this* environment active. We recommend you *always* have this environment active when working on assignments for the minor.
