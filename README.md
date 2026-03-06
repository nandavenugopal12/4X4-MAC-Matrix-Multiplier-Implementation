# 4X4-MAC-Matrix-Multiplier-Implementation
This reposity serves as a log to record our progess for an implementation of a 4x4 Matrix Multiplier using MAC units.

Hardware for processing complex AI/ML has recently gained immense popularity in the. One of the most important operations in Machine Learning is matrix multiplication. So, we decided to . By the end of this project, we hope to successfully implement a matrix multiplication module that can be easily integrated into various processing units, such as DSPs, GPUs, etc. 

Inputs of the Matrix Multiplier are as follows:
4 x 4 Matrix of weights
4 x 4 Matrix of activation values

For the implementation of the Multiplication we referenced an existing implementation of a Systolic multiplier.

<img width="1118" height="711" alt="image" src="https://github.com/user-attachments/assets/8ed5630b-7002-47bb-b9cb-aeef60142508" />

A Multiply-Accumulate (MAC) unit is a critical computational component that performs the operation in a single cycle.

MAC=(a×w)+partial sum

The first stage of this project will be the design if the MAC unit itself. To achieve this, we will break down the individual mathematical operation that make up the function. In the equation MAC=(A X B) + C, following the BODMAS rule, we will first implement A X B. A and B are two 8 bit numbers. The output of the multiplication is a 16 bit number. Our design for this is as follows:

<img width="796" height="533" alt="image" src="https://github.com/user-attachments/assets/f9d1a507-56d9-46ef-b5b9-54b110cac9eb" />

Next week, we will focus on writing the Verilog code to implement this.

