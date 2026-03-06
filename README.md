# 4X4-MAC-Matrix-Multiplier-Implementation
This repository documents the progress of our project to implement a 4×4 matrix multiplier using Multiply–Accumulate (MAC) units.

Hardware designed for processing complex Artificial Intelligence (AI) and Machine Learning (ML) workloads has gained significant popularity in recent years. One of the most fundamental operations in machine learning is matrix multiplication, which is widely used in neural networks, convolution operations, and many other ML algorithms.

The goal of this project is to design and implement a hardware-based matrix multiplication module that can efficiently perform these computations. By the end of this project, we aim to develop a 4×4 matrix multiplier architecture that can be integrated into larger processing systems such as Digital Signal Processors (DSPs), GPUs, and other hardware accelerators.

# Log 2

In this log, a technical overview of the project is described.

Inputs of the Matrix Multiplier are as follows:
4 x 4 Matrix of weights
4 x 4 Matrix of activation values

Output

A 4 × 4 matrix representing the product of the input matrices

The multiplication follows the standard matrix multiplication rule:

Y=A×W

Where:

A = Activation matrix

W = Weight matrix

Y = Output matrix

For the implementation of the Multiplication we referenced an existing implementation of a Systolic multiplier.

<img width="1118" height="711" alt="image" src="https://github.com/user-attachments/assets/8ed5630b-7002-47bb-b9cb-aeef60142508" />

A Multiply–Accumulate (MAC) unit is the fundamental building block of the matrix multiplier.

The MAC unit performs the following operation:

MAC=(a×w)+partial sum

Where:

a = activation value

w = weight value

partial sum = accumulated result from previous operations

The first stage of this project will be the design if the MAC unit itself. To achieve this, we will break down the individual mathematical operation that make up the function. In the equation MAC=(A X B) + C, following the BODMAS rule, we will first implement A X B. A and B are two 8 bit numbers. The output of the multiplication is a 16 bit number. Our design for this is as follows:

<img width="796" height="533" alt="image" src="https://github.com/user-attachments/assets/f9d1a507-56d9-46ef-b5b9-54b110cac9eb" />

Next week, we will focus on writing the Verilog code to implement this.
