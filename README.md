# lindensutter
How to manual for Linden Sutterm 2P microscope

### Starting up the scope

1. Turn on all equipment
 - Scanners - MDR-6
 - Objective motor - MP285
 - PMT and mirrors - PS-2
 - Pockels cell - Conoptics 302RM (power strip under table)
 - Laser - Turn key on front of Mai-Tai box (laser is not active until software is run)

3. Start software
 - MaiTai.
 Serial port needs to be correct, as of Sept 2015 it is COM4

 - Serial Splitter.
 COM1 is split into COM13 and COM14

 - Matlab.
   Start ScanImage by typing 'scanimage' in Matlab command prompt.
   Select a valid .ini file, needs to have "port='COM13'".

 - Igor.
   Run 'mp285_2p.ipf'.
   In Igor, activate menus by clicking in Igor command window.
   Select menu 'mp285 -> Init User'.
   Open a user .txt file.

### Downloads
 - Example ScanImage .ini file

   Critical to share objective motor serial port between Matlab and Igor.

 - Serial Splitter software
 Serial Splitter 5.0 by Etima Software

 - Igor code for mp285_2p
 - Example mp285_2p user .txt file
 
### Wiring diagram
 - [upload images of how it is wired]
 - [link to scan image documentation]
 

### Parts list
 - **Laser**, MaiTai Deep-See
 - **Lamdba Half-Wave Plate**, xxx
 - **Glan Polarizer**, xxx
 - **Pockels cell**, xxx
 - **Beam Expander**, xxx
 - **Mirror Mounts**, xxx
 - **Mirrors**, xxx
 - **PMTs**, 2x Hamamatsu xxx, GaAsp
 - **PMT Filters**
  - red, xxx
  - green, xxx
 - **Scope Body**, Sutter MOM [link]
 - **Scanners**, Cambridge xxx, 6mm mirrors
 - **Objective**, Zeiss 20x, xxx
 - **Software**, ScanImage 3.8, Igor Pro, Serial Splitter, MaiTai Control
 
