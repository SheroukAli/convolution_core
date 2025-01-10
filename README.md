# convolution_core
In this project, we build the convolution operator core. 

The core has the following components:  

 3 special memories: 

o Cyclic Queue for kernel matrix.   (256 byte)

o Input queue for Input matrix (cyclic fifo with modification) (1kB)

o Output queue for output result. (1kB) 

 Registers 

o M register to hold the number of rows in Kernel K (mxn) 

o N register to hold the number of columns in Kernel K (mxn) 

o S register to hold the stride length (the sliding window slide by how much) 

o L register to hold the number of rows of input Matrix(LxW) 

o W register to hold the number of rows of input Matrix(LxW) 

o Any other register you see relevant. 

 Multiplier : a 32-bit floating point multiplier (single precision, IEEE standard) 

 Accumulator: a 32-bit floating point accumulator  

 A controller: which has three modes of operation: 

o Loading data (kernel, or Input)

o Computing (which perform multiple and accumulate, it also controls the shift of 
the queues) 

o Output generation: which controls the generation of data out, valid and done 
signals. 
