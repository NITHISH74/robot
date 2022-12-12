# robot
### EXP-01-INTERFACING-DIGITAL-INPUT-SENSOR-WITH-ARDUINO-PUSH-BUTTON
```
int ledpin=7;
int pushpin=2;
int val=0;
void setup()

{
pinMode(ledpin, OUTPUT);
pinMode(pushpin, INPUT);
}
void loop()
{
val = digitalRead(pushpin);
if(val==0)
{
digitalWrite(ledpin,HIGH);
}
else
{
digitalWrite(ledpin,LOW);
}
}
```
### EXPERIMENT-NO--02-INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO-
```
void setup()
{
pinMode(A0,INPUT);
pinMode(7,OUTPUT);
pinMode(8,OUTPUT);
Serial.begin(9600);
}
void loop()
{
int Sensorvalue = analogRead(A0);
Serial.println(Sensorvalue);
if(Sensorvalue<=30)
{
digitalWrite(8,HIGH);
digitalWrite(7,LOW);
}
else if(Sensorvalue>=500)
{
digitalWrite(8,LOW);
digitalWritw(7,HIGH);
}
}
```

### EXPERIMENT-NO--03-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resistor
```
#define fsrpin A0
#define led1 2
#define led2 3
#define led3 4
#define led4 5
#define led5 6
#define led6 7
int fsrreading;
void setup()
{
  Serial.begin(9600);
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);
  pinMode(led4, OUTPUT);
  pinMode(led5, OUTPUT);
  pinMode(led6, OUTPUT);
}
void loop()
{ 
  fsrreading = analogRead(fsrpin);
  Serial.println(fsrreading);
  if (fsrreading > 150)
  {
    digitalWrite(led1, HIGH);
  }
  else digitalWrite(led1, LOW);
  if(fsrreading >300)
  {
    digitalWrite(led2, HIGH);
  }
  else digitalWrite(led2, LOW);
  if (fsrreading >450)
  {
    digitalWrite(led3, HIGH);
  }
  else digitalWrite(led3, LOW);
  if(fsrreading >600)
  {
    digitalWrite(led4, HIGH);
  }
  else digitalWrite(led4, LOW);
  if(fsrreading >750)
  {
    digitalWrite(led5, HIGH);
  }
  else digitalWrite(led5, LOW);
  if(fsrreading >900)
  {
    digitalWrite(led6, HIGH);
  }
  else digitalWrite(led6, LOW);
}
```
### EXPERIMENT-NO--04-Distance measurement using Ultrasonic sensor

```
#define echoPin 9
#define trigPin 10
 long duration;
 int distance;
 
 void setup()

{
pinMode(trigPin,OUTPUT);
pinMode(echoPin,INPUT);
Serial.begin(9600);
}
void loop()

{
digitalWrite(trigPin,LOW);
delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;
  Serial.print("DISTANCE: ");
  Serial.print(distance);
  Serial.println(" cm");
}
```
### EXPERIMENT NO 05 INTERFACING ANALOG OUTPUT SERVO MOTOR WITH ARDUINO
```
#include<Servo.h>

Servo myservo;
int value;
double angle;
void setup()
{
  Serial.begin(9600);
  myservo.attach(9);
}
void loop()
{
  value = analogRead(A0);
  angle = map(value, 0, 1023,0,180);
  Serial.println(angle);
  myservo.write(angle);
}
``` 
### Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino

```#define m1 2
#define m2 3

void setup()
{
  pinMode(m1, OUTPUT);
  pinMode(m2, OUTPUT);
}
void loop()
{
  digitalWrite(m1, HIGH);
  digitalWrite(m2, LOW);
  delay(10000);
}
```
