
## Scan Image
Using ScanImage 'SI5.6R1', download from here:

https://vidriotechnologies.com/download-scanimage/#free

Most of what we need to do with scanimage is here

https://vidriotechnologies.com/resources/#faq

## To get scanimage up and running

- [ ] Plug in all hardware
- [ ] Specify a 'Machine Data File (MDF)'?

see [machine data file][machine-data-file]

machine-data-file: http://scanimage.vidriotechnologies.com/display/SI2019/Machine+Data+File

## Split the objective motor serial port into two virtual serial ports.

This is so both Matlab and Igor Pro can both communicate with the objective motor controller (MP-285) serial port. They  never actually communicate at the same time.

eltimaa serial port splitter

 - [ ] Download and install 'virtual serial port driver pro'

https://www.eltima.com/products/vspdxp/#vspd-versions

#### Notes

was called 'serial port splitter'

https://www.eltima.com/products/serialsplitter/


## To upgrade igor-canvas

- [x] Ensure video aquisition works on Windows 10
- [ ] Rewrite video image acquisition code to be compatible with Igor 7.x
- [ ] Make sure serial port splitter work
- [ ] Add code to read the header of ScanImage 'SI5.6R1' files

#### Notes

 - Video driver for xxx video to usb card was downloaded from yyy.

## New hardware

See the 'resonant scanning - required' section on the followinig page:

http://scanimage.vidriotechnologies.com/display/SI2019/Supported+Microscope+Hardware

1. Chassis controller, ****PCIE-8361**

Plugs inside computer and then is wired to the chassis.

2. Chassis, 	**PXIe-1073**

Box that holds all other cards

3. Scan Control DAQ, CCA NI **PXIE 6341**

Inside chassis, wired to 2090a breakout, then BNC input from pmts

4. Digitizer, CCA **NI 5732** (14B 80M 2AI)

Inside chassis, output to scanners

5. FPGA Module, CCA, **PXIE 7961R,66** (LVDS PAIRS, 5VSX5OT)

Inside chassis, not sure on connections? connects to 'digitizer'?

6. Pockels control, CCA NI **PXIE 6341**

Inside chassis, wired to 2090a breakout, then BNC to both pockels in/out and shutter out


## Wiring the system

resonant scanners

http://scanimage.vidriotechnologies.com/pages/viewpage.action?pageId=28377185

shutter

http://scanimage.vidriotechnologies.com/display/SI2019/Shutter+Configuration

acquisition triggering

http://scanimage.vidriotechnologies.com/display/SI2019/Acquisition+Triggering

## General notes

#### PMT Amplifiers

The PMT amplifiers are 'VARIABLE GAIN HIGH SPEED CURRENT AMPLIFIER DHPCA-100' and can be found here

https://www.femto.de/en/products/current-amplifiers/variable-gain-up-to-200-mhz-dhpca.html

From the ScanImage documentation

```
Photomultiplier tubes require a transimpedance amplifier for recording by ScanImage.

The optimal bandwidth depends on the sample rate and shortest pixel durations. 

For resonant scanning a bandwidth of at least 30 Mhz is recommended.
The Femto DHCPA-100 is a commercial off-the-shelf option suited for ScanImage 5 and later, at its 80MHz setting.
```

#### Objective motor controller

Using the Sutter MP285

https://www.sutter.com/MICROMANIPULATION/mp285.html

how to configure in scanimage

http://scanimage.vidriotechnologies.com/display/SI2019/Stage+Controllers+%28Motors%29+Settings

#### Pockels cell

see following notes on using a Pockels cell with scannimage

http://scanimage.vidriotechnologies.com/display/SI2019/Beams

#### Saving to disk

Need to save to disk other than system disk c:\. Should be a solid-state-drive and run at >= 300Mb/second.


## Progress and plan

Monday, 1pm-6pm

- [x] Pulled out old equipment and cables
- [x] Installed Igor Pro 7
- [x] Installed video driver to aquire analog video
- [x] Verified Igor Pro 7 could show a video window

Tuesday (to do)

- [ ] Pull 2x old NI PCI cards out of computer
- [ ] Install new PCI card (PCIE-8361) in computer and connect to NI box
- [ ] Put all cards in NI box
- [ ] Attach two (2x) NI 2090a breakouts to NI box
- [ ] Remove existing NI cards from small rack on floor.
- [ ] Get NI Box and 2x NI 2090a breakouts in small rack on floor
- [ ] Move computer back under table

- [ ] See if we need to install NI drivers. What exactly did Sutter do with the computer?
- [ ] Try to fire up matlab/scanimage and create first 'Machine Data File (MDF)'.

- [ ] Decide if we should use periscope or mirror on table. First find the periscope.

The reason to use the periscope is it moves front/back with the scanner/mirrors as image size and brightness is optimized. Problem is with original design of the light path (my fault) where the laser comes in from the right (not the back). Thus, when scanners are moved front to back, two mirrors need to be moved on the table. A parsomonious solution would be to reroute the laser to come in the back of the light box and use the periscope.


