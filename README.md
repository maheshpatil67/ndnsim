# NDNSIM
Our mission is to innovate and develop scalable, efficient, and secure network solutions that prioritize content delivery and accessibility, transforming the way information is shared and consumed across diverse environments.

NDNSIM Version: 2.9
Supported Ubuntu Version: 22.04 with Visualizer, 24.04.1 without visualizer 
Last Updated : 24 Sep 2024

To know more about Information Centric Network visit: 
A Role of Routing, Transport and Security mechanisms in Information Centric Network

NDNSIM is ns-3 based Named Data Networking Simulator. Due to some problems, regular installation from ndnsim.net ends with errors so the following script is developed to install ndnSIM successfully in one step. This post provides a "shell script" that automates the installation of ndnSIM on Ubuntu. It has been tested on Ubuntu 22.04 and 24.04.1 LTS successfully and takes approx. 40 to 45 minutes for installation.

Note 1: This post is updated when a new version of ndnSIM or a new version of Ubuntu is released.
 
Note 2: You must be connected to the Internet while executing the shell script.

Note 3: Visualizer will not work in ubuntu 24.04.1 LTS or higher due to problems in python src / python bindings, ndnSIM will be configured with --disable-python, but program builds successfully. If you need visualizer then use ubuntu 22.04.  

Contributed by: Mahesh R. Patil, VIT University, Vellore, India. 

Steps to install ndnSIM 2.9 on Ubuntu:
 
1. Install Ubuntu 22.04 or higher and perform software update after installation.
 
2. Download the shell script and place it in home folder: 
     For Ubuntu 22.04:          u22ndnsim.sh
     For Ubuntu 24.04.1 LTS:    u24ndnsim.sh

3. Open terminal and enter into superuser mode by typing 'sudo su' then followed by the system password. 
     Above command will grant superuser privilages.

4. Give the following command on terminal:
 
   For Ubuntu 22.04:
   sh u22ndnsim.sh
   For Ubuntu 24.04.1 LTS:
   sh u24ndnsim.sh
  
You are done with it! 

Verifying the installation of ndnSIM:

1. cd ndnSIM/ns-3 
 
2. Give following command:

          sudo ./waf --run=first

If you see " 'build' finished successfully " message, ndnSIM is installed correctly.

3. If you want to verify same program with visualizer then then enter following command (visualizer not supported in ubuntu 24.04.1 LTS)
 
     	sudo ./waf --run=first --vis      
 
This command should open with visualizer.

Simulation scenarios can be written directly inside NS-3 in scratch/ or src/ndnSIM/examples folder.

This script is already configured with -d optimized and will work for examples as well as debug mode for real experimentation.

To execute programs in debug mode save the program with .cc extension in scratch/ and run the program in terminal.
Example: Save program as ndnsimple.cc in scratch/ and enter following command in terminal

            sudo ./waf --run=ndnsimple --vis

Hope it helps. If any problems persist then contact authors.

Regards,
Mahesh Patil. 

[1] https://ndnsim.net/current/getting-started.html
[2] https://www.nsnam.org/docs/tutorial/html/getting-started.html 
