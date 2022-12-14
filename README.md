# Sudoku Solver - How does it work?

## There are a few steps...

	*	Check if the board is valid, so no repeat numbers in rows, columns or squares
 	* 	If valid, it iterates through the board looking for an empty slot
 	* 	Chooses a number to put in the slot based on the rules of Sudoku
 	* 	If it finds a number that satifies the rules it will insert it and search for another slot
 	* 	This repeats until the board is completed or found to be unsolvable

## How does it backtrack?
	* 	If it runs into a slot which has no acceptable numbers it will return to an ambiguous slot (could have more than one acceptable number)
 	* 	It will then try another number in this ambiguous slot and work its way back to the point of failure
 	* 	If the same issue occurs then it will return either to the same ambiguous slot or another that it found
		before and repeat the previous step
	*	If this happens again but there are no ambiguous slots left then the solver will determine that the board is unsolvable

## How does determine a sudoku has been solved?
	*	When the solver fills in the last slot succesfully it will still make a call to look through the remainder of the board
	*	This will be the only time the solver iterates through both for loops, which sets a global boolean filled to true
	*	This tells the solver not to backtrack values in the board.

## Other information

Some hard sudokus may take more than 30 seconds to solve but they will be either solved or determined unsolvable correctly. 
The sudokus in question are 1, 5, 10, 11 and 14.#   S u d o k u - S o l v e r  
 