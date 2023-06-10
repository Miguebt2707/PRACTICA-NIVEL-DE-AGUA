# PRACTICA NIVEL DE AGUA 
## MIGUE
```
// defines pins numbers
const int trigPin = 4;
const int echoPin = 15;
const int led1 = 22;
const int led2 = 21;
const int led3 = 19;
const int led4 = 18;

// defines variables
long duration;
int distance;
int safetyDistance;


void setup() {
pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
pinMode(echoPin, INPUT); // Sets the echoPin as an Input
pinMode(led1, OUTPUT);
pinMode(led2, OUTPUT);
pinMode(led3, OUTPUT);
pinMode(led4, OUTPUT);
Serial.begin(9600); // Starts the serial communication
}


void loop() {
// Clears the trigPin
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

// Reads the echoPin, returns the sound wave travel time in microseconds
duration = pulseIn(echoPin, HIGH);

// Calculating the distance
distance= duration*0.034/2;

safetyDistance = distance;
if (safetyDistance>=2 && safetyDistance<=10)
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=10 && safetyDistance<= 21 ) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=21 && safetyDistance<=31) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=31 && safetyDistance<=50) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, HIGH);
}
else  
{
  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
// Prints the distance on the Serial Monitor
Serial.print("Distance: ");
Serial.println(distance);
delay (2000);
}
 ## EN ESTA PRACTICA LO QUE SE REALIZO FUE HACER EL CORRECTO USO PARA PODER SIMULAR CORRECTAMENTE EL NIVEL DE AGUA, DEPENDIENDO DE LA DISTANCIA A LA QUE SE ENCUENTRE LOS LEDS PODRAN MARCAR EL NIVEL ASI PRENDIENDO TODOS SI YA ESTA LLENO O APAGANDOSE CONSECUTIVAMENTE CUANDO ESTE VACIO 
# LOS MATERIALES FUERON:

 # - ESP32
 # - 4 LEDS
 # - 4 RESISTENCIAS
# - SENSOR ULTRASONICO

![](https://raw.githubusercontent.com/Miguebt2707/PRACTICA-NIVEL-DE-AGUA/e500a7ab6a1891e21af34150646785fbe6ba026a/Captura%20de%20pantalla%202023-06-10%201147441.png)

![](https://raw.githubusercontent.com/Miguebt2707/PRACTICA-NIVEL-DE-AGUA/e500a7ab6a1891e21af34150646785fbe6ba026a/Captura%20de%20pantalla%202023-06-10%201148262.png)

![]https://raw.githubusercontent.com/Miguebt2707/PRACTICA-NIVEL-DE-AGUA/e500a7ab6a1891e21af34150646785fbe6ba026a/Captura%20de%20pantalla%202023-06-10%20114923.png)

![](https://raw.githubusercontent.com/Miguebt2707/PRACTICA-NIVEL-DE-AGUA/e500a7ab6a1891e21af34150646785fbe6ba026a/Captura%20de%20pantalla%202023-06-10%201150154.png)

![](https://raw.githubusercontent.com/Miguebt2707/PRACTICA-NIVEL-DE-AGUA/e500a7ab6a1891e21af34150646785fbe6ba026a/Captura%20de%20pantalla%202023-06-10%20115055.png)

```