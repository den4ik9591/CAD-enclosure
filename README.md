Starbie

A tiny star-shaped desk pet with its own custom PCB and 3D printed case.

A XIAO ESP32-C3 draws a wandering pet on a 0.96" OLED. Press a button to open a radial menu, tilt the board to pick an action, and check the room temperature and humidity on a stats screen.

Made for Half Life, following the Starbie guide and then changed to make it my own.

<img width="1128" height="690" alt="Screenshot 2026-10-15 204012" src="https://github.com/user-attachments/assets/ec19e035-5e0e-4fc2-bb67-5701eeabd12b" />
<img width="1753" height="1050" alt="Screenshot 2026-10-15 194416" src="https://github.com/user-attachments/assets/5c94f812-a6af-4b10-814b-e1b728adc99c" />


What I made
PCB (KiCad): a custom star-shaped board. I added the 10k pull-up resistor for the DHT11 that the guide forgot, and exported the Gerbers.
Firmware (Arduino): a new DANCE action, a sparkle effect behind the pet, and my own 32x32 pet sprite.
Case (Fusion 360): a two-part star case that follows the PCB outline. It's built around imported STEP models of the real parts, with tolerances, an engraved "Starbie" lid, and heat-set inserts and screws to hold the PCB. Files and renders are in CAD-enclosure.
Hardware

XIAO ESP32-C3, 0.96" I2C OLED, MPU6050 (GY-521), DHT11 with a 10k pull-up, and 2 Cherry MX style switches.

Part	XIAO pin	GPIO
OLED and MPU6050 SDA	D4	6
OLED and MPU6050 SCL	D5	7
DHT11 data	D1	3
Button 1	D2	4
Button 2	D3	5
Controls
Button 1: opens the menu, then confirms the action. Tilt to move the selector (NAP, PLAY, FEED, DANCE).
Button 2: shows or hides the stats screen.
Shake: gives the pet a shake reaction.
Files
HalfLife10weeks/Hardware/Starbie/: KiCad project
HalfLife10weeks/Gerbers/: manufacturing files
HalfLife10weeks/Firmware/StarbieCode/: Arduino sketch
HalfLife10weeks/Images/: screenshots
Build it

Firmware: in the Arduino IDE, add the ESP32 board package (https://espressif.github.io/arduino-esp32/package_esp32_index.json), select XIAO_ESP32C3, install the Adafruit GFX, Adafruit SSD1306, Adafruit MPU6050 and DHT sensor libraries, then open StarbieCode.ino and upload.

KiCad: add Hardware/Imported Parts.pretty (footprints) and Hardware/Starbie/Seeed_Studio_XIAO_Series.kicad_sym (symbols) under Preferences > Manage Footprint/Symbol Libraries before opening the project.

Status
 Schematic, PCB and Gerbers
 Case designed in Fusion 360
 Case printed and test fitted
 Parts ordered and board built
Credits

Based on the Starbie example project and Week 1 guide from Half Life by SharKingStudios: https://github.com/SharKingStudios/Starbie
