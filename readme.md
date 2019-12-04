
## Scan Image Version

Using ScanImage 'SI5.6R1', download from here:

https://vidriotechnologies.com/download-scanimage/#free

Most of what we need to do with scanimage is documented here:

https://vidriotechnologies.com/resources/#faq


## New hardware

See the 'resonant scanning - required' section on the followinig page:

http://scanimage.vidriotechnologies.com/display/SI2019/Supported+Microscope+Hardware

1. Chassis controller, **NI PCIE-8361**

Plugs inside computer and then is wired to the chassis.

2. Chassis, 	**NI PXIe-1073**

NII box that holds all other cards

3. Scan Control DAQ, **NI PXIE 6341**

Inside chassis, wired to NII 2090a breakout, then BNC input from pmts

4. Digitizer, **NI 5732** (14B 80M 2AI)

Inside chassis, output to scanners

5. FPGA Module, **NI PXIE 7961R,66** (LVDS PAIRS, 5VSX5OT)

Inside chassis, not sure on connections? connects to 'digitizer'?

6. Pockels control, **NI PXIE 6341**

Inside chassis, wired to NI 2090a breakout, then BNC to both pockels in/out and shutter out


## Wiring the system

Machine Data File (configuration)

http://scanimage.vidriotechnologies.com/display/SI2019/Machine+Data+File

Resonant scanners

http://scanimage.vidriotechnologies.com/pages/viewpage.action?pageId=28377185

Pockels cell (Conoptics)

http://scanimage.vidriotechnologies.com/display/SI2019/Beams

Shutter

http://scanimage.vidriotechnologies.com/display/SI2019/Shutter+Configuration

Objective motor controller (MP-285)

http://scanimage.vidriotechnologies.com/display/SI2019/Stage+Controllers+%28Motors%29+Settings

Acquisition triggering

http://scanimage.vidriotechnologies.com/display/SI2019/Acquisition+Triggering

## General notes

#### Split the objective motor serial port into two virtual serial ports.

This is so both Matlab and Igor Pro can both communicate with the objective motor controller (MP-285) serial port. They  never actually communicate at the same time.

Download and install Eltima 'virtual serial port driver pro'

https://www.eltima.com/products/vspdxp/#vspd-versions

We previously used older 'serial port splitter' version

https://www.eltima.com/products/serialsplitter/

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

#### Saving to disk

Need to save to disk other than system disk c:\. Should be a solid-state-drive and run at >= 300Mb/second.


## Progress and plan

### Monday, 1pm-6pm

- [x] Pulled out old equipment and cables
- [x] Installed Igor Pro 7
- [x] Installed video driver to aquire analog video
- [x] Verified Igor Pro 7 could show a video window

### Tuesday (to do)

#### Hardware

- [x] Pull 2x old NI PCI cards out of computer
- [x] Install new NI PCI card (PCIE-8361) in computer and connect to NI box
- [x] Put all NI cards in NI box
- [x] Attach two (2x) NI 2090a breakouts to NI box
- [x] Remove existing NI breakouts from small rack on floor.
- [x] Get NI Box and 2x NI 2090a breakouts in small rack on floor, maybe move conoptics box to the side.
- [x] Move computer back under table
- [ ] Decide if we should use periscope or mirror on table. First find the periscope.

The reason to use the periscope is it moves front/back with the scanner/mirrors as image size and brightness is optimized. Problem is with original design of the light path (my fault) where the laser comes in from the right (not the back). Thus, when scanners are moved front to back, two mirrors need to be moved on the table. A parsomonious solution would be to reroute the laser to come in the back of the light box and use the periscope.

#### NI/Matlab/ScanImage Software

- [x] See if we need to install NI drivers. What exactly did Sutter do with the computer?
- [ ] Try to fire up matlab/scanimage and create first 'Machine Data File (MDF)'.

#### Igor Canvas software

- [x] Ensure video aquisition works in Igor Pro 7 on Windows 10
- [ ] Rewrite Igor code to be compatible with Igor 7, use: NewCamera, ModifyCamera and GetCamera.
- [ ] Make sure serial port splitter works and Igor canvas cann control MP-285 motor
- [ ] Add code to read SI5.6R1 Tiff headers

Video driver for xxx video to usb card was downloaded from yyy.

## 20191203

1. installed new ni driver to talk to **NI PXIE 7961R** and maybe **NI 5732**.

It is called 'FlexRIO 19.5'

download here:

https://www.ni.com/en-us/support/downloads/drivers/download/packaged.flexrio.329052.html
 
2. installed ni serial driver, **ni 232**

https://www.ni.com/en-us/support/downloads/drivers/download/packaged.ni-serial.329032.html

## scanimage updated as of 12/3 (today), this is the updates:

```
Support for vDAQ
New Motor Controls
New Stack Controls
Live motor position update (MP285, Zaber, Thorlabs MCM3000, Scientifica Stages)
Introduction of global Coordinate System
Add support for DAQmx 19.5
Channel window: add crosshair for each ROI
Introduction of Error Log and GUI Log
```

## todo 20191204

1. See if Igor can talk to mp285 (to check the mp285 serial is working at all)
2. See if manually entering mp285, baud etc in machine file fixes ScanIgor error
3. If that does now work, downgrade to

 - SI5.6R1	June 7, 2019
 - NI DAQmx 19.0


Download ni drivers called 'ni DAQmax 19.0' here,

http://www.ni.com/en-us/support/downloads/drivers/download.ni-daqmx.html#301173

