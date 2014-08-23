rubiks-solver
=============

Rubik's cube solver in javascript


This is an implementation of Thistlewaite's algorithm in javascript:
(http://en.wikipedia.org/wiki/Optimal_solutions_for_Rubik's_Cube#Thistlethwaite.27s_algorithm)

The Rubik's cube has 20 cubicles, the cubicles are fixed positions on the cube where cubies reside
Each cubie is named after the cubicle it belongs in. A cubicle is named by the faces it has.
The faces are labeled as: {U: up, D: down, R: right, L: left, F: front, B: back}

To solve a cube you pass it a string of the current state of the cube that looks like:
UF UR UB UL DF DR DB DL FR FL BR BL UFR URB UBL ULF DRF DFL DLB DBR (<-- is an already solved cube)

The first 12 pairs correspond to the cubicle of the Rubik's cube
For a scrambled cube you put the cubie that is in the cubicle in the order presented above.
An example of a scramble cube is:
BR DF UR LB BD FU FL DL RD FR LU BU UBL FDR FRU BUR ULF LDF RDB DLB

The state of the Rubik's cube is the position of the cubies at each of the 20 non-center locations

We number the cubies in the following order:
 
	                  -------------------
	                  |     |     |     |
	                  |     |     |     |
	                  |     |     |     |
	                  -------------------
	                  |     |     |     |
	                  |  11 |  B  |  10 |
	                  |     |     |     |
	                  -------------------
	                  |     |     |     |
	                  |     |     |     |
	                  |     |     |     |
	=======================================================
	|     |     |     |     |     |     |     |     |     |
	|     |     |     |  14 |  2  |  13 |     |     |     |
	|     |     |     |     |     |     |     |     |     |
	-------------------------------------------------------
	|     |     |     |     |     |     |     |     |     |
	|     |  L  |     |  3  |  U  |  1  |     |  R  |     |
	|     |     |     |     |     |     |     |     |     |
	-------------------------------------------------------
	|     |     |     |     |     |     |     |     |     |
	|     |     |     |  15 |  0  |  12 |     |     |     |
	|     |     |     |     |     |     |     |     |     |
	=======================================================
	                  |     |     |     |
	                  |     |     |     |
	                  |     |     |     |
	                  -------------------
	                  |     |     |     |
	                  |  9  |  F  |  8  |
	                  |     |     |     |
	                  -------------------
	                  |     |     |     |
	                  |     |     |     |
	                  |     |     |     |
	                  ===================
	                  |     |     |     |
	                  |  17 |  4  |  16 |
	                  |     |     |     |
	                  -------------------
	                  |     |     |     |
	                  |  7  |  D  |  5  |
	                  |     |     |     |
	                  -------------------
	                  |     |     |     |
	                  |  18 |  6  |  19 |
	                  |     |     |     |
	                  -------------------