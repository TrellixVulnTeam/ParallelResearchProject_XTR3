# PythonThreading


Repository for the PythonThreading research project for CS 470 at James Madison University

## Description

In our project, we attempt to compare the difference in runtime of parallel and serial computations between C and multiple Python implementations. The programs create an of size n containing random numbers, then performs many iterations of computations, and stores them in an array. Ultimately, the program will iterate n\*n times over the arrays, and prints the run time of the function. There is a script included that runs all programs with inputs of varying inputs.

## Compilation of C source files

To begin, start of with running the provided make file

```bash
make
gcc -g -O2 --std=c99 -fopenmp -Wall -o CBenchmark CBenchmark.c
gcc -g -O2 --std=c99 -Wall -o CBenchmark_Ser CBenchmark_Ser.c
```

It should have compiled the CBenchmark.c and CBenchmark_Ser.c files and created an executable for each

## Running the C files

Once you have the two executables in your directory, the files are ready to be ran

To run the serial C executable:

```bash
./CBenchmark_Ser <Number of Arugments>
```

to run the parallel C executable:

```bash
OMP_NUM_THREADS=<NUMBER_OF_THREADS> ./CBenchmark <Number of Arugments>
```

## Running Python3 with the Python files

To run the serial Python program:

```bash
python3 PyBenchmark_Ser.py <Number of Arugments>
```

To run the Multiprocess Python program:

```bash
python3 PyBenchmark.py <Number of Processes> <Number of Arugments>
```

To run the Multithread Python program:

```bash
python3 Py_Thread.py <Number of Threads> <Number of Arugments>
```

## Running PyPy3 with the Python files

To run pypy3, we have provided the absoulte path for it to work on the cluster

Serial Pypy example: 

```bash
pypy3.6-v7.3.3-linux64/bin/pypy3 PyBenchmark_Ser.py <Number of Arugments>
```

Multiprocesses Pypy program:

```bash
pypy3.6-v7.3.3-linux64/bin/pypy3 PyBenchmark.py <Number of Processes> <Number of Arugments>
```

## Running Cython with the Python files

To run cython with the provided provided, we have to use the absolute path. Note that we use have to use python not python3

Serial Cython example:

```bash
python Cython-0.28.1/Cy_ser_test.py <Number of Arguments>
```

Multiprocess Cython example:

```bash
python Cython-0.28.1/Cy_multi_test.py <Number of Processes> <Number of Arguments>
```


