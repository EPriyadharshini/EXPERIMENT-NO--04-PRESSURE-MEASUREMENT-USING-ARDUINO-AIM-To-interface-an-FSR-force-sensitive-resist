# EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resistor

# DATE :28/02/2024
# NAME :E.PRIYADHARSHHINI
# ROLLNUMBER :212223230159
# DEPARTMENT:B.TECH (AIDS)

## AIM: 
To interface an FSR(force sensitive resistor) and scale the output voltage obtained to pressure applied 
 
### COMPONENTS REQUIRED:
1.	FSR  (force sensitive resistor)
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
FSRs are basically a resistor that changes its resistive value (in ohms Ω) depending on how much it is pressed. These sensors are fairly low cost, and easy to use. They also vary some from sensor to sensor perhaps 10%. FSR's resistance changes as more pressure is applied. When there is no pressure, the sensor looks like an infinite resistor (open circuit), as the pressure increases, the resistance goes down. This graph indicates approximately the resistance of the sensor at different force measurements.
 

![image](https://user-images.githubusercontent.com/36288975/163532939-d6888ae1-4068-4d83-86a7-fc4c32d5179e.png)

### FIGURE 01 GRAPH OF FORCE vs RESISTANCE **




![image](https://user-images.githubusercontent.com/36288975/163532957-82d57567-a1c3-48c5-8a87-7ea66d6fca49.png)




### FIGURE 02 FORCE SENSITIVE RESITOR FOIL DISC TYPE  

FSRs are often a polymer with conductive material silk-screened on. That means they're plastic and the connection tab is crimped on somewhat delicate material. The best way to connect to these is to simply plug them into a breadboard.

The easiest way to measure a resistive sensor is to connect one end to power and the other to a pull-down resistor to ground. Then the point between the fixed pull down resistor and the variable FSR resistor is connected to the analog input of a microcontroller such as an Arduino The way this works is that as the resistance of the FSR decreases, the total resistance of the FSR and the pull down resistor decreases from about 100Kohm to 10Kohm. That means that the current flowing through both resistors increases which in turn causes the voltage across the fixed 10K resistor to increase.

 ![image](https://user-images.githubusercontent.com/36288975/163532972-2b909551-12c9-485d-adb1-d1e988d557bd.png)

### TABLE -01 FORCE AND OUTPUT VOLTAGES**
	
  Table -01 indicates the approximate analog voltage based on the sensor force/resistance w/a 5V supply and 10K pull down resistor.

### Vo = Vcc ( R / (R + FSR) )								Eq-01

****Where R= 1KΩ in this experiment 
****That is, the voltage is proportional to the inverse of the FSR resistance.










![image](https://user-images.githubusercontent.com/36288975/163532979-a2a5cb5c-f495-442c-843e-bebb82737a35.png)



### FIGURE-03 CIRCUIT DIAGRAM

![Screenshot 2024-02-29 114211](https://github.com/EzhilsreeJ/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/144870412/485491b1-6625-44a5-b5a0-5b6d58f06c14)

![image](https://github.com/EzhilsreeJ/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/144870412/03f271e7-b7ac-43d8-99a4-f8bd039a95a3)


### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 
 NAME: EZHIL SREE J
 
 ROLL NO:212223230056
 
 DEPT AND YEAR: AIDS(1st Year)
 
 ```
int fsr;
int LED = 7;
float m;
void setup()
{
  pinMode(LED, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  fsr=analogRead(A0);
  Serial.print("Raw value = ");
  Serial.println(fsr);
  delay(1000);
  m=map(fsr,0,159,0,10);
  Serial.print("Mapped value = ");
  Serial.println(m);
  delay(1000);
  
  if(m>5)
  {
    digitalWrite(LED,HIGH);
    delay(500);
    digitalWrite(LED,LOW);
    delay(500);
  }
}
```
 
 
 
 
 
 
 
 
 
 
 ![Screenshot 2024-02-29 183557](https://github.com/EzhilsreeJ/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/144870412/e98bdf8a-69b7-455a-a65d-455cd9e1d111)

 
 
 
 
 
![Screenshot 2024-02-29 182135](https://github.com/EzhilsreeJ/EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resist/assets/144870412/e539e890-40b9-468a-907d-53b4cf7e332e)





### TABLE -02 standard deviation table 
### Population Standard Deviation
The population standard deviation, the standard definition of σ, is used when an entire population can be measured, and is the square root of the variance of a given data set. In cases where every member of a population can be sampled, the following equation can be used to find the standard deviation of the entire population:



Where
xi is an individual value
μ is the mean/expected value
N is the total number of values

For those unfamiliar with summation notation, the equation above may seem daunting, but when addressed through its individual components, this summation is not particularly complicated. The i=1 in the summation indicates the starting index, i.e. for the data set 1, 3, 4, 7, 8, i=1 would be 1, i=2 would be 3, and so on. Hence the summation notation simply means to perform the operation of (xi - μ)2 on each value through N, which in this case is 5 since there are 5 values in this data set.

EX:         
μ = (2+3+4+5+6+7+8+8+9+10) / 10 = 6.2      
σ = √[(1.05-6.2)2 + (2.02-6.2)2 + ... + (10-6.2)2)]/10
σ = √(26.5225+17.4724+9.6721+....+14.44)/10 = 0.92















### RESULTS :
Arduino uno is interfaced with FSR and output values are indicated on a graph.
