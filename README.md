# BAE-305-WaterSensor
## Project Summary
For this project, we created a device that could be inserted into a water sample and read the pH and turbidity. These values could then be displayed to the user and alert them as to whether or not the liquid is safe to consume based on the pH and clarity. The device contains a pH probe that the user can insert into the liquid and a LED and phototransistor that can be shined into the liquid and have the phototransistor pick up on the amount of light that shines through.

As a result of completing this project, we are able to accurately determine the pH of a sample as well as use the values obtained from the phototransistor and LED to scale an appropriate value for the turbidity reading. This allows the user to determine whether a sample of water is safe for consumption based on these parameters. We would, however, use additional testing in order to determine other concentrations of possible contaminants/pollutants.
## Design Description
For this design, we used a pH probe, 5mm green LED, clear NPN phototransistor, potentiometer, LCD display, and a RGB LED. We began the circuitry by allowing analog pins A0 and A1 to be connected to the two sensors. From there we used our knowledge of these ciruit elements and connected them to group and voltage supply in a way that was aided by our code. We used Arduino to write the code and a breadboard and Redboard to do the wiring and construction.

To use the device the user must pour 1 cup of the desired liquid into the cup for sensing. Once all liquid has been pored in, then the user can run the accompanying code and the system will display the data on the LCD and warn the user with a red LED if the sample is unsafe for drinking.

### Wiring Diagram
![Wiring Diagram](https://user-images.githubusercontent.com/82110677/117020273-49673480-acc4-11eb-8b9e-b7e0d93d6151.PNG)

### Engineering Drawings

The device used to house the sensors and test the water is a simple modified cup, blacked out with spray to avoid any unwanted light interference. The LED and phototransistor were then placed in small holes directly across from each other in the cup. Waterproof glue was used to seal the sensors to keep the cup water tight. Any other waterproof bonding substance would work. The images below are CAD recreations of the cup. 

Bottom View

![Bottom View](https://user-images.githubusercontent.com/82110677/117024674-322a4600-acc8-11eb-9e24-5cfc375694d8.PNG)

Front View

![Front View](https://user-images.githubusercontent.com/82110677/117025744-2c813000-acc9-11eb-9c60-3f014a640669.PNG)

Side View

![Side View](https://user-images.githubusercontent.com/82110677/117026072-723df880-acc9-11eb-911f-781c4a60c87b.PNG) 

Top View

![Top View](https://user-images.githubusercontent.com/82110677/117026191-91d52100-acc9-11eb-8985-7e683aca9790.PNG)

### Code
![Code 1](https://user-images.githubusercontent.com/82110677/117055201-e6d45f80-ace8-11eb-93fc-384321561d6a.png)




## Design Decision
In order to create this system, we went through a lot of different design ideas before landing on our final design. Initially, we thought we would be able to heat the water, after determining it was unsafe to drink, but after further investigation into this process decided against it. We also decided to leave out any moving parts, such as servo motors, as this would take a lot of power and putting together two breadboards can get difficult. In the end, we determined that a pH sensor and a LED with a phototransistor would be best at determining values we could use to determine water quality. A big decision we had to make was whether to use a phototransistor or a photoresistor as they both perform similar functions. After some research and talking to Dr. Dvorak, we determined that the phototransistor would be best as it gives slightly more accurate readings. 
	
The testing device was difficult as we had to consider the fact that the wires and sensors are not water resistant (except for the pH probe). For the container/cup, we originally had planned to use a clear plastic cup with the LED and phototransistor stuck to the outside combined with a blackbox to get our readings. This idea, however, did not seem like it would give the best results. After much discussion, we determined we could use a black cup and drill holes in the sidies to insert the LED and phototransistor. We could then add putty or glue around the edges of the holes to prevent water from escaping. We were able to solder the LED and phototransistor to some wire and connect them directly to our breadboard without having to string multiple pieces of wire from the Sparkfun kit together.

Ulimately, if anyone wants to improve on the design we have made there are turbidimeters that can actually measure the turbidity of a sample directly. These devices were out of our price range because our goal was to make the design as cheap as possible. Using the phototransistor coupled with an LED allowed us to introduce some unique design ideas and learn more about how the circuitry relates to the code.

## Materials
-SparkFun Inventor Kit (Redboard Arduino, Breadboard, Resistors, LCD, RGB LED, Potentiometer)

-5mm Green LED

-NPN Phototransistor

-Gravity: Analog pH Sensor

## Testing Description
In order to test our device, we had to measure what acceptable values for turbidity would be so that the user could understand whether or not the water is safe. In order to do this, we got water and measured the value. Additionally, we tested water with the addition of dirt to analyze how our turbidity values changed, and make the appropriate thresholds within our code. We also used a multimeter to ensure that the voltage value being read from our circuit was appropriate. In order to read this value, we placed the probes of the multimeter into our circuit. The values obtained was between 4 and 5 volts, which is acceptable for our circuit. The pH meter didn't require any outside devices for testing. We calibrated it based on the known pH of the buffer solution it was provided with. To back up our thoughts we tested lemon juice and saw that it fell within 2-3pH which was expected.

## Testing Results
This system required testing of the two different sensors. The pH sensor testing was very straightforward. Our sensor came in a neutral solution and therefore it was simple to calibrate. We created the code to perform the readings which used an analog pin on the Redboard Arduino to read a voltage displayed in millivolts on the LCD screen. The pH sensor was designed to take multiple readings over a short time so our code incorporated this by allowing multiple readings to be taken. The readings would then be averaged and eventually calibrated to output a pH value of 7. We conducted a few more tests on regular tap water to ensure that it was close to 7. We also tested lemon juice which has a known pH value between 2 and 3. This assured that our pH sensor was calibrated and working properly. We couldn’t find any strong bases to test but based on our results the sensor works properly.

The second sensor was our turbidity sensor which was made up of a phototransistor and LED. To begin, we exposed the phototransistor fully to the LED and then covered it completely to ensure that we got a large enough range in voltages that we didn’t need an op amp. The range was over 4v so we concluded there was no need for an op amp. Then we tested a few samples of tap water to understand what our range would be for perfectly clear water. Next, to ensure the device was working properly we added ¼ tsp of fine dirt into 1 cup of the water sample and observed the cloudiness in the water alongside a big jump from the readings it showed with clear water. This made it clear that our system could detect the presence of suspended solids in the sample. As time elapsed, more of the debris settled and caused the clarity of the water to increase and eventually the sensor indicated that it was drinkable again.


## Testing Results Discussion
This system is capable of reading the pH and turbidity of different water samples and displaying the results on a LCD display to the user. This design would work best for small scale functions such as personal use and activities such as hiking or camping. The system works well for testing the pH pretty accurately and the turbidity of fresh water versus water with dirt in it can be accurately distinguished. The turbidity sensor is a phototransistor that detects the difference in light intensity. This is directly related to turbidity as it is the intensity of scattered light in a sample. More light is scattered due to the presence of particles which means that turbidity increases as a result of more suspended partciles. However, since we are using the phototransistor, our values decrease because the phototransistor reads voltages and acts as a variable resistor. This problem was alleviated by setting a threshold in the output for clear water and once the sensor read that the threshold was surpassed then the RGB would flash red and the LCD would display unsafe. The pH sensor can read the pH of a sample up to three significant figures. The safe range was guided by EPA standards to be within 6-8 on the pH scale.

One limitation of this system is that every time the user wants to test a different sample, the holding chamber has to be dumped and the pH probe needs to be cleaned off with some deionized water in order to get accurate readings for the next sample. This system cannot be fully trusted in determining if a sample is safe to drink. Just because the pH is appropriate and the water seems clear, there can be other contaminants that would harm the user. Additionally, if the user wanted to test a sample other than water it would not be accurate as other liquids have different pH and turbidity readings and are still completely safe to drink.
