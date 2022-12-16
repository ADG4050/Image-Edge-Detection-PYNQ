# Image-Edge-Detection---PYNQ
Image Edge Detection Sobel Filter Hardware Implementation on PYNQ FPGA Board

This code was developed for purely academic purposes by (ADG4050) as part of the module of Integrated systems design (EE5M01) in Trinity College Dublin
This was inspired from the project : https://github.com/ADG4050/Image-processing-PYNQ

## PYNQ FPGA BOARD 

PYNQ is an open-source project from Xilinx which integrates software and hardware components for faster development using Zynq devices. PYNQ combines the Python language with FPGA-based Programmable Logic (PL) and an Arm-based Processing System (PS) for building electronic systems. The PYNQ framework allows for user interaction through Jupyter Notebooks. ‘Notebooks’ are interactive documents containing live executable code organized into cells. PYNQ’s Jupyter Notebooks are hosted on the Zynq’s Arm processor and we can access them using a web browser (so long as the PYNQ board and the PC with the web browser are connected to the same network).


<img src="PYNQ.PNG" width="600">

## Edge Detection in Vivado HLS

1) Following files are added in Vivado HLS from the above Github link (sobel.cpp and sobel.h as Design Files, type sobel_accel as the top function then, tb_sobel.cpp as the TestBench File.
2) pynq-z2 is selected as the board by clicking the 3 dots next to Part Selection. Note: If you cannot find the PYNQ-Z2 board, navigate to
C:/Xilinx/Vivado/2019.2/data/boards/board_files and ensure the pynq-z2 board files are present.
3) C Synthesis is run by clicking the green ‘play’ button in the toolbar. Information such as the timing, latency and the utilization of the FPGA resources is dsiplayed in the end.
4) Desired Image is uploaded in the testbench code. tb_sobel.cpp is opened and file paths of the source image and the filter output are edited.
To run the TestBench, ‘C/RTL Cosimulation’ is run. The result is available after this in the directly.  

Export the RTL by clicking Solution→ Export RT

<img src="Image1.PNG" width="1000">
<img src="Image2.PNG" width="1000">



## Hardware implementation in Vivado PYNQ Board

An Overlay is created in Vivado with the following IP's 

a. ZYNQ7 Processing System
b. AXI Video Direct Memory Access (x2)
c. Processor System Reset
d. Concat
e. AXI Interrupt Controller
f. AXI Interconnect
g. AXI Smart Connect

The Sobel IP is added from the HLS directory that is exported.

<img src="Image3.PNG" width="1000">

An HDL Wrapper is created around the source design and the bitstream is exported (.bit and .hwh files for jupyter notebook implementation in PYNQ)

The .bit & .hwh files are uploaded to Jupyter and Harware implementation is processed as the Code in the jupyter notebook

Final Output is Below

<img src="Image4.PNG" width="1000">
<img src="Image5.PNG" width="1000">

























