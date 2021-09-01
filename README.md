# Givens rotation solving method 

This repo contain parallel (using pthread library) implementation of Given's rotation method to solve linear system. https://algowiki-project.org/en/Givens_method. I tried to optimize this method by enhanced use of CPU cache. This was achieved by operating with matrix blocks that fit in the cache.

## Building:
- Launch CMake in directory with source file, example : ```cmake . .```
- Launch Make in directory with source file, example : ```make```

## Launching:
```./QR_solver Matrix_size Block_size Thread_quantity Print_size Formula_type (File_name)```
- ```Matrix_size``` - size of square matrix 
- ```Block_size``` - size of matrix's block (to best performance use 50-100)
- ```Thread_quantity``` - thread number, for best perfomance use CPU core numbers (excluding hyper threading).
- ```Print_size``` - Maximum of matrix's columns\rows to print.
- ```Formula_type``` - Formula to initialize matrix without file.
- ```File_name``` - Optional argument, needed to initialize matrix by data from file. Formula_type should be set to 0 iff using initialization by file.


## Formulas:
- 1: A_ij = Matrix_size - max(i,j) + 1
- 2: A_ij = max(i,j)
- 3: A_ij = |i - j|
- 3: A_ij = 1 / (i + j - 1)