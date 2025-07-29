# Getting Started with G4beamline
This repository contains everything you need to establish your first G4beamline setup! Here you will find instructions for installing and running G4beamline, links to documentation, example files, and some skeleton code to get you started with your project.



## How to Use this Repository

- Fork this repository to use as a template for your next project or to work through the examples.
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
g4bl file-name.in
```
where ```file-name.in``` is your G4beamline input card. Subsequent arguments can be appended to this command; for example, the ```viewer=``` argument can be used to visualize your configuration geometry on or offline (i.e., export to a file). To see the supported viewer options, see the table on page 22 of the Users Guide.

To launch the GUI from terminal,
```
g4blgui
```
opens the GUI in a separate window. (Note that this will not work with Docker!) The GUI can also be accessed by launching G4beamline like a traditional application.



## Using the GUI
The GUI can be used to access the visualizer -- a useful tool for viewing the geometry and placement of your configuration. It is highly recommended that you use this option!

<div align="center"><img width="791" height="623" alt="g4blgui" src="https://github.com/user-attachments/assets/0cfa8907-6fdc-48d5-9e45-7b9cf9b4c1ce"/></div>
<div align="center"> G4beamline GUI </div> <br>

The visualizer will be selected by default. Running with this selected will bring up a second window with an interactive 3D model of your configuration. 

<div align="center"><img width="925" height="358" alt="g4bl_visualizer_tracks" src="https://github.com/user-attachments/assets/d84cc8f6-d106-45dc-afcc-21518e04e9c2" /></div>
<div align="center"> G4beamline Visualization Window </div> <br>

To add particle tracks to the render, type the desired number of events in the top left window and hit "Next Image" to see the tracks appear in the model.

Note that utilizing the visualization tool will prevent some data write out. To properly run a file with full output, uncheck the "Visualization" box first.



## Examples
Example G4beamline input files can be found in the ```examples``` directory. The provided examples include:
- [coming soon]



## Useful Scripts
Some general python scripts for use in your G4beamline project are located in the ```functions``` directory. The functions included are as follows:
- [coming soon]



## Integrating with ICOOL
[coming soon]
