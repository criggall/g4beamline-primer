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
G4beamline is available for download as an application from here: https://muonsinc.com/G4beamlineDownload.php. (Note that you may be prompted to complete a survey before being permitted access to the download page.)

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
where ```file-name.in``` is your G4beamline input card. Subsequent arguments can be added to this command; for more on this consult the Users Guide.

To launch the GUI from terminal,
```
g4blgui
```
opens the GUI in a separate window. (Note that this will not work with Docker!) The GUI can also be accessed by launching G4beamline like a traditional application.




## Using the GUI
[coming soon]




## Examples
[coming soon]



## Useful Scripts
[coming soon]



## Integrating with ICOOL
[coming soon]
