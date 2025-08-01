# Getting Started with G4beamline
This repository contains everything you need to establish your first G4beamline setup! Here you will find instructions for installing and running G4beamline, links to documentation, example files, and some skeleton code to get you started with your project.



## How to Use this Repository

- Fork this repository to use as a template for your next project.
- Work through the examples.
- Consult the [Issues](https://github.com/criggall/g4beamline-tutorial/issues) page for solutions to common problems and questions.



## G4beamline Documentation
Official Muons, Inc. Users Guide for G4beamline version 3.08: https://www.muonsinc.com/Website1/Muons/G4beamlineUsersGuide.pdf



## Installing G4beamline
G4beamline can be installed via Docker or locally as an application. For access to the GUI, a local installation is required.

### Docker Installation
If you do not have already have Docker installed on your machine, you can download it here: https://www.docker.com/get-started/. Once Docker is installed, the ```docker-compose.yml``` provided in this repository will do the rest.

G4beamline Docker image used: https://hub.docker.com/r/valetov/g4bl

### Local Installation
G4beamline is available for download as an application here: https://muonsinc.com/G4beamlineDownload.php. (Note that you may be prompted to complete a survey before being permitted access to the download page.)

In order to run G4beamline from terminal, you will need to provide a path to the installation. A template ```.bash_profile``` doing so has been provided in this repository, but you will need to add the installation path depending on your setup. For example, on Mac this may look like ```/Applications/G4beamline-3.08.app/Contents/MacOS```.

### Source Code
If you are inclined to compile G4beamline from source, it is available here: https://github.com/lawrenceleejr/g4beamline.



## Running G4beamline
G4beamline can be run via terminal command or, if installed as such, launched as an application. The GUI can be used to both run scripts and access the visualizer tool.

### Running the Docker Container

If you are using Docker, start by running the container in the background with,
``` 
docker compose up -d
```
Then execute the container via,
```
docker exec -it g4bl bash
```
This will establish a bash environment in which you can now run G4beamline commmands!

### G4beamline Terminal Commands
To run G4beamline from terminal use the syntax,
```
g4bl input.g4bl
```
where ```input.g4bl``` is replaced by the name of your G4beamline input card. Subsequent arguments can be appended to this command; for example, the ```viewer=``` argument can be used to visualize your configuration geometry on or offline (i.e., export to a file). For more on this, see the Visualization section below.

### Using the GUI
To launch the GUI from terminal,
```
g4blgui
```
opens the GUI in a separate window. (Note that this will not work with Docker!) The GUI can also be accessed by launching G4beamline like a traditional application.

<div align="center"><img width="791" height="623" alt="g4blgui" src="https://github.com/user-attachments/assets/0cfa8907-6fdc-48d5-9e45-7b9cf9b4c1ce"/></div>
<div align="center"> G4beamline GUI </div> <br>

The visualizer will be selected at the top left by default. Running with this selected will prevent some data write out; to properly run a file with full output, uncheck the "Visualization" box first.


## Visualization

Visualization is a useful tool for viewing the geometry and placement of objects in your configuration. It is highly recommended that you use this option whenever you make adjustments to your build! 

Running with the "Visualization" box selected will bring up a second window with an interactive 3D model of your configuration. 

<div align="center"><img width="925" height="358" alt="g4bl_visualizer_tracks" src="https://github.com/user-attachments/assets/d84cc8f6-d106-45dc-afcc-21518e04e9c2" /></div>
<div align="center"> G4beamline Visualization Window </div> <br>

To add particle tracks to the render, type the desired number of events in the top left window and hit "Next Image" to see the tracks appear in the model.

### Offline Viewers

In leiu of using the native G4beamline visualization window, a model of your configuration can also be output for offline viewing. Appending ```viewer=``` to your run command with one of the options given on page 22 of the Users Guide will write-out the visualization to the given file type. For example,
```
g4bl input.g4bl viewer=VRML2FILE
```
To specify the number of images and events to simulate for the visualization, use the syntax ```viewer=option,images,events``` with the respective arguments replaced by the desired numbers. For example,
```
g4bl input.g4bl viewer=VRML2FILE,1,10
```
will output a .wrl file with 1 image containing 10 particle tracks. Failing to specify these parameters will open a command line (```Idle>```) where the running ```/run/beamOn events``` (with events replaced by the desired number of events) will have the equivalent effect -- i.e., producing a file of the specified type.

A popular approach to creating visuals is by using [Blender](https://www.blender.org) to generate renderings of your model. An outline of the procedure for doing so is given below.

<img width="976" height="514" alt="Screenshot 2025-07-31 at 10 13 13 PM" src="https://github.com/user-attachments/assets/cb1ed098-2cc8-415f-8233-c11e51d27cb8" />



## Building the Input File
The configuration of your G4beamline simulation is specified in the text input file (```*.g4bl```) you provide. A template file, ```template.g4bl```, has been provided here to get you started in constructing your input!



## Automating G4beamline
When iteratively running simulations over a parameter scan, it is useful to automate the procedure with scripting. The ```automate-g4bl.py``` file serves as a skeletal python script for building your automated G4beamline setup.



## Examples
The ```examples``` directory contains a compilation of the example input cards given in the Users Guide, presenting demonstrative simulations such as a simple cooling channel, MICE, a target, etc. 

Future versions of this repository will include more advanced examples designed to feature some of the more nuanced functionalities of G4beamline that are difficult to parse from the Users Guide. A few of the features planned to be included in these examples are:
- Defining macros
- Setting custom output names
- Using loops and if statements
- Generating field maps



## Coming Soon
Ideas for future versions of this repository:
- Examples of muon cooling channels (such as HFOFO and rectilinear)
- Infrastructure, instructions, and examples for integrating G4beamline with ICOOL/ECALC9

If there is anything else you would like to see included, please reach out with suggestions!
