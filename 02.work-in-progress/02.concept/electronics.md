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

Calculate the resistence of a LED:

        R = Us-U2/I2

![alt text](images/diode.jpg)

*Turn on a LED*
