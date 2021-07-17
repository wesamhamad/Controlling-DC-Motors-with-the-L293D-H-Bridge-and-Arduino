# Controlling DC Motors with the L293D H Bridge and Arduino
## Pre requirement
* Create an account in [TINKERCAD](https://www.tinkercad.com/join)
* Create a new Circuit

## Tools: 
1. Breadboard.
2. Arduino Uno R3.
3. DC Motors.
4. Wires.
5. L293D H Bridge.
<img width="722" alt="Screen Shot 1442-12-07 at 7 31 11 AM" src="https://user-images.githubusercontent.com/74800962/126025503-9585c978-9fe4-44d1-a189-04eda20e7190.png">


## What is L293D H Bridge?
A motor driver is an integrated circuit chip which is usually used to control motors in autonomous robots. Motor driver act as an interface between Arduino and the motors . The most commonly used motor driver IC’s are from the L293 series such as L293D, L293NE, etc. These ICs are designed to control 2 DC motors simultaneously. L293D consist of two H-bridge. H-bridge is the simplest circuit for controlling a low current rated motor.L293D has 16 pins.

![L293D-Pins](https://user-images.githubusercontent.com/74800962/126024531-2352ce31-70c4-43a8-b05c-1f0a9c5078bd.png)

## Steps :
#### step1: Connect Enable1&2,Enable3&4 and power1 with (5v) pin on Arduino.
#### step2: Connect input1 with 13 pin, input2 with 12, input3 with 8 pin pin, input4 with 7 pin on Arduino.
#### step3: Ground pins (4,5,12,13) on L293D connected to GND pin on Arduino.
#### step4: Connect Output1&Output2 with DC Motor1, Output3&Output4 with DC Motor2.

NOTE: DC Motor will rotating in clockwise direction and if you want to run DC motor in anticlockwise direction we need to some change in the code (Replace HIGH to LOW and vice versa).
```c++
void loop()
{
  digitalWrite(13, LOW);
  digitalWrite(12, HIGH);
  digitalWrite(8, LOW);
  digitalWrite(7, HIGH);
 }
 
```
But, if you want it to rotate in both directions with a while in between, then you need to set a delay for number of millisecond then the direction of rotation changes to other side.
```c++
void setup()
{
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(7, OUTPUT);
}

void loop()
{
  digitalWrite(13, HIGH);
  digitalWrite(12, LOW);
  digitalWrite(8, HIGH);
  digitalWrite(7, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(13, LOW);
  digitalWrite(12, HIGH);
  digitalWrite(8, LOW);
  digitalWrite(7, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
 
}
```
#### step5: Finally, connect power 2 with positive pin of battery and the negative pin with GND on Arduino.


# Output Sample


https://user-images.githubusercontent.com/74800962/126025030-f19bd8ca-4e74-48f0-8d39-b3ede9217616.mov

### YOU CAN [TRY IT](https://www.tinkercad.com/things/d93VBBPUqW0-smooth-fyyran) !

# Learning references:
1. [Click here](https://www.youtube.com/watch?v=qJeAo4zo0IY)
2. [Click here](https://www.youtube.com/watch?v=9GhyRfEPu8k&t=322s)
3. [Click here](https://www.youtube.com/watch?v=bQZzUdMp57s) 
