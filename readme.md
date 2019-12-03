
## Scan Image
Using ScanImage SI5.6R1	

download from here:

https://vidriotechnologies.com/download-scanimage/#free

be sure to follow the links:

 - documentation
 - readme
 - hardware requirements
 
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

#### Notes

 - Video driver for xxx viideo to usb card was downloaded from yyy.

## New hardware

See the 'resonant scanniing - required' section on the followinig page:

http://scanimage.vidriotechnologies.com/display/SI2019/Supported+Microscope+Hardware

1. Chassis/controller, 	**PXIe-1073**

The chassis has a PCIIe controller card in the computer

    PCIe x1 for MXI controller connecting to the PXI chassis

2. Digitizer, CCA **NI 5732** (14B 80M 2AI)

3. FPGA Module, CCA, **PXIE 7961R,66** (LVDS PAIRS, 5VSX5OT)

4. Pockels control, 2x CCA NI **PXIE 6341**

5. CCA, **PCIE-8361**



## General notes

#### PMT Ampliifiers

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

#### Objective motor controller

Using the Sutter MP285

https://www.sutter.com/MICROMANIPULATION/mp285.html

#### Pockels cell

see following notes on using a Pockels cell with scannimage

http://scanimage.vidriotechnologies.com/display/SI2019/Beams


