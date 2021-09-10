---
title: "Python and Jupyter"
date: 2019-08-13T03:15:18+02:00
weight: 3
draft: false
---


## Downloading Anaconda

Fortunately, there is a convenient all-in one solution for our Python needs: the Anaconda distribution, which comes with all the tools and libraries we will need for scientific computing. 

Download the appropriate version for your operating system from [here](https://www.anaconda.com/distribution/) and install it on your system. 

{{%notice warning%}}
Make sure to get the **version 3.8 of Python**! Python v2.7 is being phased out. 
{{% /notice %}}

## Installing Anaconda
The main installation steps for Anaconda are very similar on the different operating systems.

1. After starting the installer, a license agreement will pop up on screen. Accept it.
2. Install for All Users (this assumes you have admin privileges; it avoids later problems if you can do this). Allow the installation if your virus protection software asks you.
3. It is suggested you accept the suggestion for the installation location (e.g., C:\ProgramData\Anaconda3 on Windows).
4. **(Windows only)**: Make sure that the select Advanced Options include "Register Anaconda as my default Python 3.7" and click **Install**.
5. The installer will give you the option to install Microsoft's VSCode editor. Jupyter has its own editor "built in", so it is not necessary to install an additional tool for our purposes. You may want to consider VSCode as an option for other coding efforts.
6. If everything worked, you will get a message thanking you for installing Anaconda. There will be **two already-checked boxes**: You ***do not*** need to sign up for Anaconda Cloud, so uncheck this, but you may want to read "Getting Started with Anaconda". Hit **Finish** to complete the installation.

{{%notice warning%}}
You ***do not*** need an Anaconda Cloud account to download and use the distribution!! 
{{% /notice %}}

## PHY422/820 Tutorial

This [tutorial](jupyter_intro.ipynb) demonstrates much of the functionality of Jupyter that will be used throughout the course.

{{%notice tip%}}
Certain browsers will save Jupyter notebooks with an additional `.txt` extension - the files are intact, just rename them in order to do your work. 
{{% /notice %}}

## Reference Materials

Here we collect some useful **cheat sheets** on basic Python and Jupyter usage, as well as the most important libraries we are going to use for computational work.

### Python and Jupyter Basics
<b>[Python Cheat Sheet](pdfs/Beginners_Python_Cheat_Sheets_from_PCC.pdf):</b> This is a useful compilation of essential Python/Jupyter commands for common computing tasks (checks, loops, etc.). 

<b>[Python Basics](pdfs/Python_Basics-Python_cheatsheets_Datacamp.pdf):</b> Another collection of the essential Python language constructs.

<b>[Jupyter Notebooks](pdfs/Jupyter_Notebook-Python_cheatsheets_Datacamp.pdf):</b> Essentials of Jupyter notebooks - think Mathematica, but powered by Python.

<b>[Debugging Python](pdfs/debugging_python_flowchart.pdf):</b> Sooner or later you will have to do some debugging. This flowchart will hopefully help you to make sense of the Python error messages, and remind you of rudimentary debugging procedures.


### Libraries

<b>[Matplotlib](pdfs/Matplotlib-Python_cheatsheets_Datacamp.pdf):</b> Matplotlib is one of the most popular libraries for plotting in Python. Use it in your Jupyter notebooks.

<b>[SciPy](pdfs/SciPy_Linear_Algebra-Python_cheatsheets_Datacamp.pdf):</b> Python's collection of routines for scientific computing (special functions, linear algebra etc.). Interfaces with NumPy for efficiency.

<b>[NumPy](pdfs/NumPy_Basics-Python_cheatsheets_Datacamp.pdf):</b> NumPy, and in particular the NumPy data structures, are used for efficient numerical computation in Python. NumPy provides wrappers for many highly optimized numerical libraries, allowing you to exploit features like parallelization from your Python code - today, there are high-performance applications running on supercomputers that are written in Python, using NumPy for their numerical heavy lifting!
