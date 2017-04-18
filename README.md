# Pulse Input Processor and Logger 

This project is a Penn State Behrend Senior Design Project for TechnipFMC. This project employs the use of the BeagleLogic library to capture data at 8Ms/s on the BeagleBone Black. The application in its current state is used to analyze quadrature encoded signals up to 10khz. Every second the application will publish its data to a MQTT Mosquitto broker to be analyzed on separate devices to are subscribed to the broker. 

## Getting Started

In order to run the Pulse Input Processor and Logger on your BeagleBone Black you will need to first configure the BeagleBone Black. The easiest way is to use the prebuilt image for the BeagleLogic library, details of which can be found [here](https://github.com/abhishek-kakkar/BeagleLogic/wiki/BeagleLogic-%22no-setup-required%22-setup:-Introducing-System-Image!). 

* Note that this project does not use the last two pins 20 and 21 on the BeagleBone Black due to bus conflicts with the EEPROM. 


### Prerequisites

To build this app you will need quite a few libraries 

Since the application publishes to MQTT your BeagleBone will need to have MQTT Mosquitto installed
```
apt-get install mosquitto mosquitto-clients  
```

The application also uses libssl-dev for communicating with the broker 
```
apt-get install libssl-dev  
```

To publish to the broker the application is dependent on MQTT Paho libraries which can be found
[here](https://eclipse.org/paho/clients/c/) along with an easy to follow tutorial on how to build it. 

### Building
Once you have Paho up and running you should be able to build the PIPL application after cloning this repo on to the BeagleBone run the following 

```
cd PIPL/quadCount
make
./PIPL
```
## Built With

* [BeagleLogic](https://github.com/abhishek-kakkar/BeagleLogic/wiki) - The kernel driver and PRU assembly code 
* [Paho](https://eclipse.org/paho/clients/c/) - MQTT libraries 

## Authors

* **Daphne Cruz**     - [Daphne](https://github.com)
* **Kevin Brenneman** - [kalvin66rocks](https://github.com/kalvin66rocks)
* **Michael Stumpf**  - [pro585code](https://github.com/pro585code)

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE.md](LICENSE) file for details

## Acknowledgments

* Big thanks to [abhishek-kakkar](https://github.com/abhishek-kakkar), his BeagleLogic library made this possible
* Also thanks to Fred Weiser and TechnipFMC for sponsoring this project and providing the necessary hardware 




