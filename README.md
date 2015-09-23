# lindensutter
How to manual for Linden Sutterm 2P microscope

### Starting up the scope

1. Turn on all equipment
 - Scanners - MDR-6
 - Objective motor - MP285
 - PMT and mirrors - PS-2
 - Pockels cell - Conoptics 302RM (power strip under table)

2. Turn on laser
 - Turn key on from of MaiTai laser
 - Run Mai-Tai software
 
3. Start software
 - MaiTai
 Serial port needs to be correct, as of Sept 2015 it is COM4

 - Serial Splitter
 COM1 is split into COM13 and COM14

 - Matlab.
   Start ScanImage by typing 'scanimage' in Matlab command prompt.
   Select a valid .ini file, needs to have "port='COM13'".

 - Igor
  
   Run mp285_2p.ipf
 
   In Igor, activate menus by clicking in Igor command window
 
   Select menu 'mp285 -> Init User'
 
   Open a user .txt file

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
 - 

### Parts list
 - PMT filters
  - red
  - green
 
