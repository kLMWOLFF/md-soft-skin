# Notion of Electronics - Pierre 

## Components
- **Soldering Iron** - Make mechanical and electronical connections between components
- **Multimeter** - Measure different values in electronic circuits,  voltage (power), resistence and amperage 
- **Breadboard** - Make quick electrical connections between components to make fast prototypes before soldering them.

 ![alt text](images/breadboard.jpg)
- **Streetboard** - board use to sold components togethet (have copper circuits connections)

 ![alt text](images/streetboard.jpg)
- **PCB (printed circuits board)** - electronic board made 

 ![alt text](images/pcb.jpg)
- **Solder pump** - suck the solder to remove it from a board
- **Solder wire** - melted when heated in order to create a solder
- **Wire (soft - maleable wire /hard - mantain shape)** - to make a bridge from one part of a board to another to pass on information
- **Vice** - hold a piece in place while your hands are being used to build the circuit/soldering

- **Microcontrolers**
    - Arduino (nano, uno, mega)

    ![alt text](images/arduino.jpeg)
    - ESP32 (do the same thing as arduino but is smaller and already come with bluetooth/wi-fi)

    ![alt text](images/esp32.jpeg)
    - ATtiny85 (cosumes less battery than isb32/ can be put in sleep mode and consume almost 0  battery and be activated remotely to wake once a day to make measures and go back to sleep)

    ![alt text](images/attiny85.jpeg)

- **Resistors**
    - Dissipate watts - (loses energy and creates heat)
    - Voltage is kind of a pressure. The battery whants to exit the energy from one point and regain electrycity from the other.
    - Energy does not flows naturaly like water. It stays in the same place unless prompted to move (you cannot just open a tap and eletricity will flow). In other for the energy to move, a circuit is needed; open circuits don't work. 
    - A current = flow of energy

- **Transformers**
    - Transform the energy to higher or lower values

## Resistor
- A voltage across a resistor causes a current;
- The voltage pushes the current out and make it move
- The resistor apply resistence to the current and make it harder for it to pass.
- Higher Voltage = Higher Current
- Higher Resistence > lower Current 
    
        I - intensity of the current (amphère) [A]
        U/V - voltage [V]
        R - resistence [Ω/ohm]

        AC - alternative current (current flows continously bettween 0 - 300v; 50x by second[measured in hz])
        DC - direct current (allways have the same voltage)

**Open circuit x Short Circuit**
- Open circuit 
    - when there is no passage from the positive to the negative poles (infinite resistence)
    - Zero current: the current does not flow
    
- Short Circuit
    - zero resistence/ no limit to the energy going through - current (it will give everything it can and create a lot of heat until it burns)
    - infinite current (theoretically, but not in practice because the resistence is never really 0, even in cooper wire)



Air = has a big resistence (that's why electricity needs wires to pass; it cannot pass throug positive+negative and create a short circuit by itself)
Skin = 1,831MΩ - big resistence
Every component have a resistence

## Ohm's Law
         U  =  R * I
        [v] = [Ω]*[a]

**Voltage**
- Name: U
- Unit: volt
- Symbol: [V]

**Current**
- Name: I
- Unit: amphere
- Symbol: [A]

**Resistence**
- Name: R
- Unit: ohm
- Symbol: [Ω]

  ![alt text](images/OhmLaw.jpg)

  ## Joule Effect (power)
  - A resistor through which a current flow consumes a certain amount of electrical energy and transforms it into heat.
  - Arduino resistors can support up to 0.5W of power. More that that, it will make them heat to much and break.
  - Small wires (arduino) cannot undergo more that 1A for a longt time. The wire will heat too much and melt the insulation 

  **Power**
- Name: P
- Unit: watt
- Symbol: [W]

        P = U * I
        P = R * I²
        P = U²/R

![alt text](images/joules.effect.jpg)

**Voltage divider**
In series, the voltages add up
        U = U1+U2

The current through the two resistors are the same.
The objective is to reduce the voltage in the end (U2) to make sure we don`t have more volt/current then our component can take.
        U1= R1*I
        U2 = R2*I
        U = (R1+R2)*I

![alt text](images/voltage.divider.jpg)

**LED (Light-Emitting Diode)**
- A diode will let a current go in only one direction. In the opposite way, it will block th current (Anode [A] = +/ Cathode [K] = -).
-  It can be used to transform CC to CD (need an array of 4 diodes) - **GRAETZ**
- Normally, diodes don't emite light. LED are bad diodes, that don't block current but, instead, produces light.
- Different Led's colors respond/work in different currents lenghts (mA), in which they will consume different amounts of voltage.
- LED ref: 2,2V/ 20mA
- Arduino maximum current = 

Calculate the resistence of a LED:

        R = Us-U2/I2

![alt text](images/diode.jpg)

* When connecting external components to the arduino (ex. step motor) that requires more energy then the arduino can provide (5V), you can power the component with an external font, but the GND of both Component + Arduino need to be connected, to have the same parameter.

* Arduino mp3 player shield - have a sd card entrance and jack output. When connected to the Arduino, it can be turned into an mp3 player.

                - Vin (Voltage in): pin used to power the arduino with an external battery
                - 2-13 (Digital input/output): digital pins used for both inputs+outputs. Work with two values = 1 or 0 (HIGH and LOW). 
                - Some digital pins have PWM - pulse wave modulation(~): They receive analog messages from 0 (off) to 255 (on). Usually, the PWM function is available on pins 3, 5, 6, 9, 10, and 11.  
                - A0-A5 (analog inputs/outputs):  An analog signal is one that can take on any number of values. The function that you use to obtain the value of an analog signal is analogRead(pin). This function converts the value of the voltage on an analog input pin and returns a digital value from 0 to 1023, relative to the reference value.
                 - TX>0 (info transmiter)/RX>1 (info reception): careful when use, because it keeps sending messages to the arduino through the same entrance this one uses to run the code. It may block the info passage.


### *Blinking a LED*
**Build**
![alt text](images/circuit.blibkLed.png)

**Code**

                int led = 13;

                void setup() {                
                pinMode(led, OUTPUT);  //turn pin13 into an Output
                }

                void loop() {
                digitalWrite(led, HIGH);  //send 5v to pin13
                delay(1000);             
                digitalWrite(led, LOW);  //send 0v to pin13
                delay(1000); 
                }

### *Blinking a rgb LED*
**Build**
![alt text](images/rgb.light.png)
![alt text](images/blinkRGB1.jpg)
![alt text](images/blinkRGB2.jpg)

**Code**

                int redPin = 11;
                int greenPin = 10;
                int bluePin = 9;

                void setup(){
                pinMode(redPin, OUTPUT);
                pinMode(greenPin, OUTPUT);
                pinMode(bluePin, OUTPUT);
                }

                void loop() {
                delay(300);
                setColor(255, 0, 0); //red
                delay(1000);
                setColor(0, 255, 0); //green
                delay(1000);
                setColor(0, 0, 255); //blue
                delay(1000);
                }

                void setColor(int red, int green, int blue) {
                analogWrite(redPin, red);
                analogWrite(greenPin, green);
                analogWrite(bluePin, blue);
                }

## Constant
- Allows you to give a name and a meaning to a value
- The value cannot change during execution 
- Allows you to isolate the numerical values (the configuration) in one place
- Writen with fullupercase and (_) for dividing names
- Constant don't need to end its lines with (;).

                #define LED 13 
                void setup() { 
                  pinMode(LED, OUTPUT);     
                } 



## Variable
- Allows you to assign a name to a value
- The value can change during the execution of the program
- The value is used instead of the name
- Boolean = variable that can only have 2 states (True/False)
- val = variable box where you can store a value

                #define LED 13 
                boolean val = HIGH; 
                void setup() { 
                  pinMode(LED, OUTPUT);     
                  digitalWrite(LED, val); 
                }

- (!) = negative

val = !val; //the value should change to its opposite everytime it is called

                #define LED 13
                boolean val = HIGH;

                void setup() {
                pinMode(LED, OUTPUT);
                
                }

                void loop() {
                digitalWrite(LED, val); //call the variable val (turn the led hight)
                delay (1000);
                val = !val; //call the variable val again but negate it (if the light is on, it turn off. If it is off, it turns on)
                }

### *Button turn on/off LED*
**Build**
![alt text](images/button.Led.jpg)
![alt text](images/arduino.processing.jpg)

**Code**

                #define LED 12
                #define BUTTON 8

                void setup() {
                pinMode(LED, OUTPUT);
                pinMode(BUTTON, INPUT_PULLUP); //connect the button to arduino internal resistor, which connects to the 5v
                
                Serial.begin(9600);
                }

                void loop() {
                boolean val = digitalRead(BUTTON);
                digitalWrite(LED, val);

                //Serial.println("Hello\n\n\n...."); // \n = new line
                //Serial.println("A\tB\tC"); // \t = tab

                Serial.println(val);
                delay(100);
                }