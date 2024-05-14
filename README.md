# ZDCOnlineMonitoring
This contains scripts to run over the 2023 data and plot their results needed for performing the online monitoring of the ZDC. It is divided into the following subdiretories.

## Python
The python directory contains the code that can be used to run over the raw data as it comes in. In order to monitor the timing information, please refer to the  `recHitRaw` instructions below. In order to check the unpacker vs. emulation code or the digis, use `l1Ntupele2023.py`. In order to adapt this depending on the run, refer to the [ZDC Online monitoring Twiki](https://twiki.cern.ch/twiki/bin/view/CMS/ZDCRun3OnlineMonitoring). and [ZDC Software](https://twiki.cern.ch/twiki/bin/viewauth/CMS/ZDCSoftwareHome)


## recHitRAW (src)
This config file in the python folder produces a root file with the ADC and Charge in each channel of the ZDC, it also produces plots related to timing under the fC_vs_BX folder.
To run this file emap_2023_newZDC.txt, QWZDC2018Producer_cfi.py, ZDC2018Pedestal_cfg.py, and all the source files are required.

## Plotting
This directory contains plotting macros used for processing the L1Ntuples produced by the code in the python directory. The two main plotting functionalities include plotting the emulator vs. unpacker comparisons as well as the per digi plots. 

## LUT Conversion
The code in this directory is useful for converting the LUT provided by HCal experts (Michael Krohn) to the format used by the L1T ZDC emulation. Note that this conversion code would quickly become obsolete once [PR # 42818](https://github.com/cms-sw/cmssw/pull/42818) is merged. Note that for OOTPU subtraction the idea is to create two different LUTs and then use both of these in the code. Full instructions are included in the [L1 ZDC Emualtor Twiki](https://twiki.cern.ch/twiki/bin/view/CMS/ZDCL1TEmulator). The text files for the most recent versions of the LUTs (v4) are included in the file. 
