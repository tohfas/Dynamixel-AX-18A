# Dynamixel-AX-18A
The Dynamixel servos have good feedback mechanism and better torque and speed compared to some other servos. This project deals with controlling Dynamixel using Arduino.
#include <AX12A.h>

#define DirectionPin  (1u)
#define BaudRate    (1000000ul)
#define ID    (3u)

void setup()
{
 ax12a.begin(BaudRate, DirectionPin, &Serial);
 ax12a.setEndless(ID, ON);
 
}

void loop()
{
    ax12a.ledStatus(ID, ON);
    ax12a.turn(ID, LEFT, 500);
    delay(5000);
   ax12a.ledStatus(ID, OFF);
    ax12a.turn(ID, RIGHT, 500);
    delay(5000);}
