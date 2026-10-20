# DJI Tello Drone Lab

## Overview
The goal of this lab is to become familiar with the drone controls, its network settings, and the ports it uses to send and receive information. This lab will introduce the DJITelloPy Python library as a method of controlling the drone. 

## Environment Setup
1. Install the Tello and X-Hubsan apps on your mobile device and DJITelloPy Python library on your computer.
2. The DJITelloPy library is an open-source project and can be found here: https://github.com/damiafuentes/DJITelloPy.
3. You can install it using `pip install djitellopy`
4. Use Ubuntu operating system version 20.04. Other versions should be able to work as well.
5. Connect the drone using your Ubuntu VM and run Wireshark to capture the traffic. You can use the sample code on GitHub: https://github.com/damiafuentes/DJITelloPy/blob/master/examples/simple.py.

## Controls
1. For this next step, you will need to control the drone while sniffing network traffic.
2. The best way to do this is to run Wireshark on the device acting as the drone’s controller.
3. Connect to the drone on your computer and use the DJITelloPy library to create a controller for the drone on your computer.
4. You can use the sample code on GitHub as a template in designing your drone controller: https://github.com/damiafuentes/DJITelloPy/blob/master/examples/manual-control-opencv.py.

## Picture
1. Take a photo using this code: https://github.com/damiafuentes/DJITelloPy/blob/master/examples/take-picture.py

## Video
1. Connect to the drone on your computer.
2. Using the DJITelloPy library, fly the drone and capture video from your computer using this code: 
https://github.com/damiafuentes/DJITelloPy/blob/master/examples/record-video.py
3. While you fly the drone, capture the raw data of the video stream using Wireshark.
4. In Wireshark, this can be done by right clicking on a packet that is part of the stream and clicking Follow > UDP Stream.
5. A window with the data stream should pop up. Change the “Show data as” field to “Raw” and click “Save As.”
