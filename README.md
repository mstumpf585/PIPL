# Pulse Input Processor and Logger 

This project is a Penn State Behrend Senior Design Project for TechnipFMC. This project employs the use of the BeagleLogic library to capture data at 8Ms/s. The application in its current state is used to analyze quadrature encoded signals up to 10khz. Every second the application will publish its data to a MQTT Mosquitto broker to be analyzed on separate devices. 

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

To build this app you will need quite a few libraries 

Since the application publishes to MQTT your BeagleBone will need to have MQTT Mosquitto installed
```
apt-get install mosquitto mosquitto-clinets  
```

The application also uses libssl-dev for communicating with the broker 
```
apt-get install libssl-dev  
```

To publish to the broker the application is dependent apon MQTT Paho libraries which can be found
[here](https://eclipse.org/paho/clients/c/) along with a easy to follow tutorial on how to build it. 

### Building
Once you have Paho up and running you should be able to build the PIPL applicaition after cloneing this repo on to the BeagleBone run the following 

```
cd PIPL/quadCount
```
```
make
```
```
./PIPL
```
## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc



![logo](logo.png)
===========

NEW: The BeagleLogic cape is here! To get more information please click [here]
(https://github.com/abhishek-kakkar/BeagleLogic/wiki/The-BeagleLogic-Cape).

Bootstrapped as a Google Summer of Code 2014 Project with BeagleBoard.org.

For detailed information and usage guide refer to
[the project wiki](https://github.com/abhishek-kakkar/BeagleLogic/wiki)

BeagleLogic realizes a logic analyzer on the BeagleBone / the BeagleBone Black using
the Programmable Real-Time units and matching firmware and Linux kernel modules on the
BeagleBone Black.

The software should also work on the BeagleBone White, but with limited memory support
(only 256 MB instead of 512 MB)

BeagleLogic can also be used in conjunction with the sigrok projects to capture and process
the data on the BeagleBone itself. The libsigrok bindings for BeagleLogic have been accepted
into the upstream libsigrok repository.

Directories:

* beaglelogic-firmware: PRU Firmware
* beaglelogic-kernel-driver: Device Tree overlay source and kernel module source and Makefile.
**The default BeagleBone kernel v3.8.13-bone60 and above ship with BeagleLogic support.
You can verify it using the command** ```modinfo beaglelogic```
* beaglelogic-server: Node.JS backend and static file server for the web interface
* cape: The cape design files (KiCAD schematic and PCB file only. Production Gerbers are available separately.)
* webapp: A minimal web client for BeagleLogic. Uses sigrok-cli internally for data
acquisition
* testapp: A simple test application that shows how to use the userspace API of BeagleLogic
and benchmarks memory copy speeds.
 
Selected binaries and archives related to the project may be downloaded from
[this link](http://goo.gl/770FTZ). Refer to the wiki for more information 
regarding the use of the archives and the binaries.

License
--------

 * **PRU firmware & Device tree overlay** : GPLv2
 * **Kernel Module**: GPLv2+
 * **sigrok bindings**: GPLv3+
 * **Web interface** [/beaglelogic-server and /webapp]: MIT
 * **Cape** : CERN Open Hardware License
 * **Logo** : [Creative Commons Attribution-ShareAlike 4.0 International (CC-BY-SA-4.0)]
(http://creativecommons.org/licenses/by-sa/4.0/)

