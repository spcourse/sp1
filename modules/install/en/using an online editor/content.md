# Using an online editor

There are a couple of online editors available that let you write and run Python code without any installation from your part. We recommend this if installing Python on your computer gives you trouble.

## CS50 IDE

The CS50 IDE is an "integrated development environment", meaning that it includes everything you need to write Python code. It is one of the best online editors we know. Complete the following steps to gain access:

To gain access to the development environment you can do the following:

1. Register for a GitHub account at <https://github.com/join>. GitHub is an online service where developers from all over the world share (open source) software. Many scientists use it, too! In your case, you'll only use their login facility to get into the online development environment.

2. Log on to <https://ide.cs50.io/>. It will redirect you to GitHub, asking permission to transfer your basic details to CS50. Don't worry though! CS50 is a Harvard course and they will not spam you. After logging in, it will create your online IDE.

> At the time of writing, the CS50 IDE only works in Chrome or Firefox browsers and not in Safari. So you may need to switch browsers if all you get is a blank screen!

After creating the workspace you should see this in the screen of your browser:

![cs50](cs50.png)

## Testing

At the top left you see a folder icon with behind it the text **~/**. Right click or ctrl+click it and subsequently select **New Folder**. Call this folder **module1**.

Toward the bottom of the screen you may find the **terminal**, where you can type commands. Try and type the following command after the `$`:

    ls

The `ls` command is short for "list". This command shows a list of all files and folders that can be seen from your "current" folder. By default the terminal starts in the folder `~/workspace`, and by executing the command `ls` you should only see the folder `week1` that you've just created. Let's now change the "current folder" by executing the following command:

    cd week1

The command `cd` is an abbreviation of the word compact disc... uh, no... *change directory*. It changes the current folder to another folder, in this case the folder `week1`. If you were to execute `ls` again, there would be no results yet (so you will be shown no visible results). Let's change that fact by running the following command:

    touch hello.py

Now we've created a file called `hello.py` inside of the folder `week1`. To verify that actually happened, you can execute another `ls`. The command `touch` checks whether a file (in this case `hello.py`) already exists, and if not creates that file.

To open the file `hello.py` you have to use your mouse pointer to open the folder icon at the left hand side of the screen. First open the folder `~/workspace`, by clicking the triangle in front of it. Then do the same thing for the folder `week1`, and finally double click the file `hello.py`. Now a new tab has opened up called `hello.py` and this is where we can start programming!

Add the following line of code to the `hello.py` file:

    print("Hello, World!")

Then save your newly written program and ta-da! You've written your first (Python-)program. You can then execute that program using the following command in the terminal:

    python hello.py

If everything is in order you should see directly below that command the words: `Hello, World!`.

## Extra tips

Good to know is that you can also move one folder back up with `cd`:

    cd ..

Here `..` stands for the folder directly 'above' the current one. Want to go back even further up? You can with `../..`. You can also tell `cd` not to move relatively to your current position, but instead move to an 'absolute' path in respect to your login folder:

    cd ~/workspace/week1

That immediately brings you back to the folder `week1` inside of `workspace`.

## Installing Matplotlib and Checkpy

We use a program to check whether your assignments are implemented correctly. We expect you to be very precise when you give the correct output. To do so, we have written a program called `checkpy`, which is not standard in your developing environment. Aside from that we'll get to work with plotting graphs and for that we need a specific module in Python called `matplotlib`. Both of these need to be downloaded additionally.

To download both `matplotlib` and `checkpy` you have to run the following command separately in your terminal:

    pip install matplotlib
    pip install checkpy
    checkpy -d uva-sp/sp1

It can take quite a while for each command and a lot of text will move over your screen. In case there is relatively little text on your screen, try to find a message stating something went wrong or ask for assistance! 

To test if everything is in working order and whether `hello.py` is implemented correctly, run the following command in the terminal:

    checkpy hello

Is everything colored green and do you see only happy smileys? That means you've done a-okay, and that you've met our requirements for the assignment! Should there still be some red smileys, no worries! Carefully examine your code and verify it with each of the specifications. And don't forget you can always send us an email if your stuck.
