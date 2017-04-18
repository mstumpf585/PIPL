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

* [BeagleLog](https://github.com/abhishek-kakkar/BeagleLogic/wiki) - The kernel driver and PRU assembly code 
* [PAHO](https://eclipse.org/paho/clients/c/) - MQTT libraries 

## Authors

* **Daphne Cruz **    - [Daphne]()
* **Kevin Brenneman** - [kalvin66rocks](https://github.com/kalvin66rocks)
* **Micahel Stumpf**  - [pro585code](https://github.com/pro585code)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Big thanks to [abhishek-kakkar](https://github.com/abhishek-kakkar), his BeagleLogic library made this possible
* Also thanks to Fred Weiser and TechnipFMC for sponsoring this project and providing the necessary hardware 




