
###  DATE: 21/03/2024

###  NAME:  panduru somu
###  ROLL NO : 212223240111
###  DEPARTMENT:AIML
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
~~~
int enable = 6;
int input1 = 3;
int input2 = 4;
void setup()
{
  pinMode(enable, OUTPUT);
  pinMode(input1, OUTPUT);
  pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable, 255);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(5000); // Wait for 1000 millisecond(s)
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(5000);
}
~~~
### OUTPUT
## circuit diagram
![Screenshot 2024-03-21 114740](https://github.com/somu0831/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/162110820/dab51f88-d967-4b87-babf-a1aecf8f5ca7)

## Schematic diagram
![Screenshot 2024-03-21 114836](https://github.com/somu0831/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/162110820/15e30b47-4d8a-41f6-8930-451e7210689d)

### GRAPH AND TABULATION 

![Screenshot 2024-03-21 114146](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/162110820/4335434f-da33-4cf6-ab8a-3a440ee84d78)

![Screenshot 2024-03-21 113924](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/162110820/b2a8f8f5-c7ac-4d5d-b54b-1b9166a82af0)



### RESULTS AND DISCUSSION 
THUS WE FINISHED CONTROLLING DC MOTOR USING ARUIDNO UNO
