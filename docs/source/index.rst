.. Caravel User's Project Example Documentation documentation master file, created by
   sphinx-quickstart on Wed Apr 27 15:15:14 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Caravel User's Project Example Documentation's documentation!
========================================================================
Introduction
------------
Caravel [2] is an SoC that has a space for implementing a project by the user. This project can be used as a peripheral by the management core.
In this document, the SPM is implemented inside the user project area. This document is going to explain how this was implemented. 
The SPM takes two numbers, multiplies them and returns the result. The details on how the SPM is implemented can be found in [3]. 
In order for the SPM to communicate with the Management SoC, the wishbone bus is used. In our case, the SPM has 4 registers as wishbone slaves. 
For more details about how a wishbone slave is implemented, please read [4]. 

Environemnt Setup
-----------------
For this project, there is a need to set up Caravel User’s Project. 
Caravel User’s Project is where you can implement your own project in the user project area (refer to Figure 1).
In order to install Caravel User’s Project, follow the instructions used in [5]. There are a few points to take care of here:
- Openlane[6] is a tool used to harden[7] an RTL(Register Transfer Level or code written in verilog) design. 
OpenLane is automatically installed in the directory referred to by OPENLANE_ROOT, not the directory named openlane inside the caravel_example directory
- Caravel is installed by default so you don’t have to install it yourself. 
- The last two commands of the precheck are probably going to fail because you’re not allowed to submit the example of the counter provided in the example.
- As a user, you can put your verilog design in the directory /verilog/rtl/ 
- Make sure that the input/output ports of the module are kept the same as the example given in /verilog/rtl/user_proj_example.v 

MakeFile
--------
A process can be automated using a MakeFile. A MakeFile is a script composed of a set of “rules”. A rule is a target, coupled with some prerequisites and a recipe.  
A target in the context of a MakeFile is the name of the file generated or the action that is requested. 
The prerequisites are the files or other targets that are required to be available before the target is requested. 
The recipe is the set of commands or tasks to be done when a target is requested.  The way you call a specific target is by writing in the terminal 
make <target name>
Accordingly, the recipe for the make <target name> is executed if the prerequisite files are available. If the prerequisite files are not available, then MakeFile is searched for rules that have these files as targets and accordingly, these recipes are executed to produce the required prerequisites for the originally requested target. We are going to use the targets of the MakeFile in section 7. 



.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
