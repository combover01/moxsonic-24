# moxsonic-24

## To download the BioSignal Max external library, please to go the "releases" page on the side of this page or at this link: https://github.com/combover01/moxsonic-24/releases/tag/v0.0.2
## To make the EEG equipment work with your computer, install OpenBCI GUI:
https://openbci.com/downloads

<img width="787" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/5c69ebe6-7072-49d6-859a-3c531ab11b86">

## Steps to install the BioSignal External Package to your Max:
Once you have the BioSignal external zip file downloaded, unzip it. Then add the "bs.externs" folder to your Max Packages folder:
``` Users / your_username / Documents / Max 8 / Packages ```

Then, in the Max Package Manager, you should see "bs.externs" under the installed packages menu. 
<img width="766" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/3fc558e4-9ce1-407f-acb5-4275c491a1a8">

If your Max looks like this, you're good to go! The three objects included in the library in its current state are ```bs.upsample~```, ```bs.fft~```, and ```bs.leaky_integrator~```. We will go over these in the workshop! Here is a link to my slides for your future reference: https://docs.google.com/presentation/d/1lJjt-IbuzJHRGvhkO0voZgk0wQ6PEVszWW4YU3VxW-U/edit?usp=sharing


## Steps to run OpenBCI_GUI to send LSL on your computer:
0.) MAKE SURE YOUR BOARD IS OFF. No lights should be on. Then plug in the USB dongle and open OpenBCI GUI.

1.) Under "DATA SOURCE" pick "Ganglion" if you have the blue board or "Cyton" if you have the white one.

2.) Transfer protocol is "Bluetooth (BLED112 Dongle) for the blue board (Ganglion), or "Serial (from Dongle)" for the white one (Cyton).

3.) Turn on your board using the switch on the side. Select the correct device if you are using the Ganglion board. For Cyton, do the switch that says "PC" and NOT the switch that says "BLE".

4.) Under "BRAINFLOW STREAMER" click "Network"

### Cyton settings: 
<img width="517" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/1ee4d7aa-75d9-4824-9d8f-101ad60cb3a6">

### Ganglion settings:
<img width="510" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/e1e4405d-7210-4b3e-b458-db1d998c9c3e">

5.) Hit START SESSION

6.) Click "START DATA STREAM"

<img width="411" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/83410bde-d5e1-47de-9b69-7d086dd99693">

7.) Under "LAYOUT" click the 4-square-panels button 

<img width="183" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/8febea3e-0997-47f4-84d1-c9858761b5d3">

8.) Change the accelerometer to "Networking" 

<img width="169" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/b32df7b5-6277-4790-a068-87d39996342f">

9.) Select "LSL" as the protocol

<img width="85" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/cd394f6d-319e-4bfd-ac21-66cf68e12b9b">

10.) Under "Stream1" select "Time Series Raw" to send the raw data on your computer's LSL port.

11.) Click "Start LSL Stream" to start the stream!

<img width="276" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/2b943d79-2936-485f-bd69-5ed3eb7e74f1">

11.) (optional) if you want, change the fourth window in the view to be "Band Power": 

<img width="505" alt="image" src="https://github.com/combover01/moxsonic-24/assets/56941032/8c914888-90b1-40e6-80f3-869386265a76">

12.) Now you should have OpenBCI GUI fully set up and running. If you are wearing a headset, you will be able to see your brainwaves in the GUI. You should be sending LSL on your computer now as well, so we can open Max and check with one of the externals.

13.) Open Max and create an object: ```bs.upsample~ 4``` <- (for Cyton, do ```bs.upsample~ 8```, Gangliong does 4)

14.) You should be able to get the EEG signal out of the outlets! Turn on DSP and attach a live.scope~ object to outlet 1. If it looks empty, attach a number~ object to see what values it is outputting. 

15.) Check the help files for bs.upsample~, bs.fft~, and bs.leaky_integrator~. Have fun!






