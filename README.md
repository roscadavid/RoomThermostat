                                                                                              Room thermostat
  The project consists of a device capable of measuring the ambient temperature of a room, maintaining a constant temperature within a specified range, and signaling if the temperature exceeds the set limits. In this project, we covered the following chapters: Block Diagram of the Thermostat, Temperature Sensors, Conditioning Circuit for the Temperature Sensors, Display, Microcontroller Selection and Programming in C and Assembly, Keypad, Relay, and the Final Circuit in Proteus. For the implementation of this project, we used Proteus for circuit design and Keil microVision for writing the code in C as well as Assembly for programming the microcontroller.
  Lastly, I will discuss the project chapters: 
  1. Block Diagram.
      In this chapter, I created the block diagram of the microcontroller with the following components: ambient temperature, power supply, control panel, LCD, temperature sensor, ADC, heating and cooling system, with the microcontroller at the center of the block diagram.

2.Temperature Sensors. 
In this chapter, we discussed:
What is temperature? 
Temperature is a fundamental state parameter that characterizes the thermal state of a body, specifically its thermodynamic equilibrium state. Temperature measurement is based on various physical phenomena and effects, where changes in temperature lead to modifications in properties or characteristics of materials, such as variations in geometric dimensions, changes in electrical resistance, or the generation of an electromotive force across the junction of two metals, among others. The accuracy of temperature measurement is crucial for most applications involving the control of various technological processes. 
What is a temperature sensor? 
A temperature sensor is a device that collects temperature data from a particular source and converts it into a form intelligible to a device or observer. We also mentioned several types of temperature sensors, including: Resistance Temperature Detectors (RTDs), Thermocouple Temperature Sensors, Thermistor Temperature Sensors, and Semiconductor Sensors. At the end of Chapter 2, we created a table comparing multiple temperature sensors and chose the LM35 sensor for our project because of its good accuracy and suitable temperature range for implementing a room thermostat.

3. Temperature Sensor Conditioning Circuit.
    In this chapter, we discussed the chosen temperature sensor. The temperature sensor selected is the LM35. It is a precision temperature sensor with an analog voltage output that is linearly proportional to the measured temperature in degrees Celsius. The output has an impedance of 0.1 ohms, and the sensor is calibrated inherently in degrees Celsius.
The amplifier used is an AD8541AS because it operates within the temperature range of the sensor and has a supply voltage of 5V. Characteristics of AD8541AS include:

Low power consumption
Operating voltage from 2.7V to 5V and +/-5V for differential supply
High speed
Slew rate of 30V/us
Rail-to-rail input and output
Operating frequency up to 80MHz
Output current of 1.5mA
The analog-to-digital converter used is ADC0808, chosen because it operates on 8 bits, requires a 5V supply voltage, has an error of 0.5LSB and 1.5LSB, conversion time of 100us, and consumes only 15mW. ADC0808 is an 8-bit A/D converter with data lines D0-D7, operating on the successive approximation principle. It features 8 analog input channels, each selectable via addressing lines A, B, and C. In this case, input IN0 is selected by grounding lines A, B, and C.

Typically, control signals EOC (end of conversion), SC (start conversion), ALE (address latch enable), and OE (output enable) are processed through a microprocessor. However, the presented circuit operates continuously without using a microprocessor. Input control signals OE and ALE are active high and tied to +5Vcc. The SC input control signal, active low (logic 0), initiates conversion on the falling edge of the pulse, while the output signal becomes 1 after the conversion process ends. The EOC output is connected to the SC input, where the falling edge of the EOC output acts as the SC input to command the start of conversion. Once conversion starts, EOC becomes 1.

Upon the next clock pulse, EOC returns to 0, allowing SC to initiate a new conversion. Thus, the converter continuously provides 8-bit digital output signals corresponding to the instantaneous value of the analog input signal. The maximum value of the analog input voltage should not exceed the reference level of +5V.

The ADC0808 requires a clock signal with a typical frequency of 550kHz. To visualize the output signal, 8 LEDs were used, each connected to an output line. Because the ADC operates continuously, it displays the output signal as soon as the input signal is applied.

4.Display. What is a display?
A display is an optoelectronic device used to show letters, numbers, or images temporarily, without permanent recording, and is considered a peripheral of the computer. Types of Displays: Electroluminescent Display (EL), Liquid Crystal Display (LCD), Light-Emitting Diode Display (LED), Plasma Display. Choosing the type of electronic display
For my project, I will choose an LCD electronic display because:
✓ Can be used at high altitudes
✓ Low power consumption
✓ Lightweight screens
✓ Long lifespan
✓ Good brightness and superior visibility under direct sunlight
Criteria for choosing an LCD display include:
✓ Price
✓ Number of characters/number of lines
✓ Power consumption
✓ Lifespan
✓ Supply voltage Based on the research done, I chose to use an LCD display. The LM016L display is one of the most widely used on the market and is ideal for my project.
LM016L LCD is a 16x2 display, meaning information will be displayed in 16 columns and two rows. This display is powered by a 5V source and allows the writing of main alphanumeric characters. LM016L includes a standard HD44780 controller chip that receives data from an external source and communicates directly with the LCD.

In conclusion, we programmed the microcontroller in both C and assembly languages across the following chapters. If the room temperature falls below the user-set temperature, the central LED will turn on, and if the room temperature exceeds the user-set temperature, the LED will turn off.




