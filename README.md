# Rack Detection Test

This file contains my scripts to work with **YOLOv3** (neural network for object detection).

# Setup

## How to install Yolo System:
1. Run these in the terminal accordingly:

>git clone https://github.com/pjreddie/darknet
>cd darknet
>make
2. Check whether the system is installed correctly by running these in the **darknet** directory:
>wget https://pjreddie.com/media/files/yolov3.weights
>./darknet detect cfg/yolov3.cfg yolov3.weights data/dog.jpg

2.1. Then you will see something like this: 
>layer     filters    size              input                output
    0 conv     32  3 x 3 / 1   416 x 416 x   3   ->   416 x 416 x  32  0.299 BFLOPs
    1 conv     64  3 x 3 / 2   416 x 416 x  32   ->   208 x 208 x  64  1.595 BFLOPs
    .......
  105 conv    255  1 x 1 / 1    52 x  52 x 256   ->    52 x  52 x 255  0.353 BFLOPs
  106 detection
truth_thresh: Using default '1.000000'
Loading weights from yolov3.weights...Done!
data/dog.jpg: Predicted in 0.029329 seconds.
dog: 99%
truck: 93%
bicycle: 99%
## How to use the Rack's front legs detection?
1. Download the weight file and the .cfg file required for the leg detection in the **Darknet** directory:
> git clone https://github.com/chua0876/rack_detect.git
2. Run this command in the terminal to test the weight file:
> cd Darknet
> ./darknet detector test rack_detect/yolov3_rack.cfg rack_detect/<....weight> rack_detect/frame0201.jpg

You can also use the weight file to detect any videos by running:
> ./darknet detector demo  rack_detect/yolov3_rack.cfg rack_detect/<....weight>  <video file>
