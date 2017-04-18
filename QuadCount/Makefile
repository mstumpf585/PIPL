OBJS = PIPL.o beaglelogic.o seniorDesign.o 
CC = gcc
DEBUG = -g
CFLAGS = -c -pthread $(DEBUG)
LFLAGS = -pthread -lpaho-mqtt3c $(DEBUG)

PIPL : $(OBJS)
	$(CC) $(LFLAGS) $(OBJS) -o PIPL

PIPL.o : seniorDesign/seniorDesignLib.h libbeaglelogic.h PIPL.c 
	$(CC) $(CFLAGS) PIPL.c

beaglelogic.o : libbeaglelogic.h beaglelogic.c
	$(CC) $(CFLAGS) beaglelogic.c 

seniorDesign.o : seniorDesign/seniorDesignLib.h seniorDesign/seniorDesign.c
	$(CC) -L/home/debian/paho.mqtt.c/build/output $(CFLAGS) -lpaho-mqtt3c seniorDesign/seniorDesign.c
clean:
	\rm *.o 

