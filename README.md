# Introduction
Conway's Game of Life is a cellular automaton, which simulates a world of cells.

The simulation takes place on a grid, composed of infinitely many rows and columns.

Rows and columns of the grid are numbered with integers.

Each cell on the grid can be in one of two states: alive or dead.

The collective state of all cells is referred to as a generation.

The simulation starts with an initial generation, and subsequent generations are calculated based on it.

In the next generation, a cell will be alive if and only if:

The cell is alive in the current generation and has exactly two or three live neighbors, or
The cell is dead in the current generation and has exactly three live neighbors.
Project Description
This project involves writing a program to simulate Conway's Game of Life.

The program reads the description of the initial generation from the input. Then, in a loop, it displays a portion of the grid (window) and reads and executes user commands.

The commands control the calculation of subsequent generations and specify the window of the grid displayed to the user.

The program is parameterized with two positive integers:

ROWS: The number of rows in the window.
COLUMNS: The number of columns in the window.
The values of these parameters are defined using symbolic constants, which can be defined with the compiler's -D option.

The default values in the code are ROWS = 22 and COLUMNS = 80.

The window's position on the grid is determined by the position of its top-left corner. If the top-left corner of the window is in row w and column k, the window covers cells with row numbers from w to w + ROWS - 1 and column numbers from k to k + COLUMNS - 1.

Initially, the top-left corner of the window is in row 1 and column 1.

# Input Data Format
The program reads the description of the initial generation, followed by a sequence of commands.

The description of the initial generation indicates the living cells and has the format of several rows starting with the '/' (slash) character.

In the last row of the initial generation description, there is only the '/' character.

In all other rows after the '/', there is an integer representing the row number of the grid. Following that, there is an ordered, non-empty sequence of integers representing the column numbers of the living cells in that row. Each of these numbers is preceded by a single space.

A row in the following format:

/w k1 .. kn
indicates that in row w of the grid, the cells in columns k1, ..., kn are alive.

The sequence of row numbers in the description of the initial generation, preceded by '/', is ordered in ascending order.

After the description of the initial generation, the program reads a sequence of one-line commands.

The program recognizes the following commands:

Terminate the program: A line with a single period '.'.
Calculate the Nth next generation: A line with a positive integer N. It calculates the Nth next generation, starting from the current generation. In particular, the command 1 calculates the next generation.
Calculate the next generation: An empty line. It is equivalent to the command 1.
Dump the current generation: A line with the number 0. It generates a complete description of the current generation in the same format as the initial generation description that was read by the program.
Output Format
Before reading each command, the program displays the contents of the window, starting from the top-left corner.

The contents of the window are presented as ROWS rows, each with length COLUMNS. After the last row, there is a row containing a sequence of COLUMNS '=' (equal sign) characters.

The character in each row of the window content indicates the state of the cell. A live cell is represented by the character '0' (zero), and a dead cell is represented by the '.' (dot) character.

# Examples
Below are examples of the program's output when compiled with the command:

gcc @opcje -DWIERSZE=22 -DKOLUMNY=80 zadanie3.c -o zadanie3
Input data files with the description of the initial generation and example commands are provided as .in files, and the expected output for each example is provided as .out files.

For the input data in the file przyklad1.in, the correct output is in przyklad1.out.
For the input data in the file przyklad2.in, the correct output is in przyklad2.out.
For the input data in the file przyklad3.in, the correct output is in przyklad3.out.
