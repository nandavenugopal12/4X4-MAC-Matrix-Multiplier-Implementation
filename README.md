# 4X4-MAC-Matrix-Multiplier-Implementation
This reposity serves as a log to record our progess for an implementation of a 4x4 Matrix Multiplier using MAC units.

Hardware for processing complex AI and machine learning workloads has recently gained immense popularity. One of the most important operations in machine learning is matrix multiplication. Therefore, we decided to design and implement a hardware module capable of performing efficient matrix multiplication. By the end of this project, we hope to successfully develop a matrix multiplication module that can be easily integrated into various processing units such as DSPs, GPUs, and other hardware accelerators.

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
This repository documents the progress of our project to implement a 4×4 matrix multiplier using Multiply–Accumulate (MAC) units.

Hardware designed for processing complex Artificial Intelligence (AI) and Machine Learning (ML) workloads has gained significant popularity in recent years. One of the most fundamental operations in machine learning is matrix multiplication, which is widely used in neural networks, convolution operations, and many other ML algorithms.

The goal of this project is to design and implement a hardware-based matrix multiplication module that can efficiently perform these computations. By the end of this project, we aim to develop a 4×4 matrix multiplier architecture that can be integrated into larger processing systems such as Digital Signal Processors (DSPs), GPUs, and other hardware accelerators.

Project Overview

The matrix multiplier takes two input matrices:

Inputs

A 4 × 4 matrix of weights

A 4 × 4 matrix of activation values

Output

A 4 × 4 matrix representing the product of the input matrices

The multiplication follows the standard matrix multiplication rule:

𝑌
=
𝐴
×
𝑊
Y=A×W

Where:

A = Activation matrix

W = Weight matrix

Y = Output matrix

Each output element is computed as:

𝑦
𝑖
𝑗
=
∑
𝑘
=
1
4
𝑎
𝑖
𝑘
×
𝑤
𝑘
𝑗
y
ij
	​

=
k=1
∑
4
	​

a
ik
	​

×w
kj
	​


To efficiently compute this operation in hardware, the design uses an array of Multiply–Accumulate (MAC) units.

Architecture Inspiration

For the implementation of the matrix multiplier, we referenced an existing systolic array multiplier architecture. Systolic arrays are commonly used in hardware accelerators for AI because they allow efficient data reuse and high parallelism.

In this architecture:

Activation values propagate horizontally

Weight values propagate vertically

Partial sums accumulate through MAC units

This structure enables multiple multiplications and accumulations to occur simultaneously.

MAC Unit

A Multiply–Accumulate (MAC) unit is the fundamental building block of the matrix multiplier.

The MAC unit performs the following operation:

𝑀
𝐴
𝐶
=
(
𝑎
×
𝑤
)
+
partial sum
MAC=(a×w)+partial sum

Where:

a = activation value

w = weight value

partial sum = accumulated result from previous operations

This operation is essential for implementing matrix multiplication, digital filters, and neural network computations.

MAC Design Breakdown

The first stage of this project focuses on designing the MAC unit itself.

To implement the MAC operation, we break it into two basic arithmetic operations:

𝑀
𝐴
𝐶
=
(
𝐴
×
𝐵
)
+
𝐶
MAC=(A×B)+C

According to the BODMAS rule, the multiplication must be performed before the addition.

Step 1: Multiplication

Inputs:

A (8-bit value)

B (8-bit value)

Output:

16-bit product

This stage multiplies the activation value with the corresponding weight.

Step 2: Accumulation

The 16-bit multiplication result is added to the partial sum stored in an accumulator register.

This allows multiple multiplication results to be accumulated to produce the final matrix multiplication output.
