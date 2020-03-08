# Object-Size-Detector

![app image](./docs/images/object-size-detector.png)

## What It Does

 This application demonstrates how to use CV to detect and measure the approximate size of assembly line parts. It is designed to work with an assembly line camera mounted above the assembly line belt. The application monitors mechanical parts as they are moving down the assembly line and raises an alert if it detects a part on the belt outside a specified size range.

## Requirements


### Software
* [Ubuntu\* 16.04 LTS](http://releases.ubuntu.com/16.04/)

## How It Works

This object size detector works with a video source, such as a camera. The application captures video frames and processes the frame data with OpenCV* algorithms. It detects objects on the assembly line and calculates the area (length x width) the objects occupy. If the calculated area is not within a predefined range, as specified via command line parameters, the application raises an alert to notify the assembly line operator. Optionally, the application sends data to a message queuing telemetry transport (MQTT) machine, or machine messaging server, as part of an assembly line data analytics system.

![Code organization](./docs/images/arch3.png)

The program creates three threads for concurrency:

- A main thread that performs the video I/O
- A worker thread that processes video frames using the deep neural networks
- A worker thread that publishes MQTT messages

