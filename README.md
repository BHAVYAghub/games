
Introduction of SUDOKU
This article is on the implementation of a Sudoku game in Java. This version includes an intuitive interface with the ability to use help and to check for errors. Turning on help will mark all possible fields for the selected number. After checking for errors, the program marks valid fields green and invalid fields red. The rules used in this implementation are as follows:
An integer may only appear once in ...
o... the same row.
o... the same column.
o... the same 3x3 region.
A game has only one solution.

Implementation
A valid game has in every row, every column, and every region the numbers 1 to 9. Additionally, there should only be one solution existing. To achieve this, all open fields are filled with the first valid value. Even after finding a solution, the search continues by putting the next valid value in an open field. If a second solution is found, then the search will be stopped and the method returns false. There will always be at least one solution.
SudokuPanel and Fields
SudokuPanel contains 9 sub panels each containing 9 fields. All sub panels and fields are placed in a GridLayout of 3x3. Each sub panel represents a region of a Sudoku game, and is primarily used for drawing a border visually separating each region. They also get the SudokuController added to them, which is in charge of processing user input by mouse.
ButtonPanel
ButtonPanel contains two panels with a titled border. The first panel contains three buttons. Button New for starting a new game, button Check for checking user input, and button Exit for exiting the application. The second panel contains 9 toggle buttons placed inside a button group. This way, they react like radio buttons. Clicking one of these toggle buttons will set the corresponding selected number in the Game class.
NOTE: WE CAN ALSO IMPLEMENT THE GUI OF THE GAME IN ANDROID.
Approach(Backtracking Algorithm)

We can observe that all 3 x 3 matrices, which are diagonally present are independent of other 3 x 3 adjacent matrices initially, as others are empty. [0 means not filled]
Like all other Backtracking problems, we can solve Sudoku by one by one assigning numbers to empty cells. Before assigning a number, we check whether it is safe to assign. We basically check that the same number is not present in the current row, current column and current 3X3 subgrid. After checking for safety, we assign the number, and recursively check whether this assignment leads to a solution or not. If the assignment doesn’t lead to a solution, then we try next number for the current empty cell. And if none of the number (1 to 9) leads to a solution, we return false.
APART FROM THIS THERE WILL ALSO BE A TIMER OF THE GAME WHICH WILL BE SOLELY BASED ON MULTITHREADING.
  Find row, col of an unassigned cell
  If there is none, return true
  For digits from 1 to 9
    a) If there is no conflict for digit at row, col
        assign digit to row, col and recursively try fill in rest of grid
    b) If recursion successful, return true
    c) Else, remove digit and try another
  If all digits have been tried and nothing worked, return false.












Introuduction : Minesweeper

we would make the classic game of "Minesweeper" which is often found pre-installed in most machines using windows.
To start off the project we decided upon the difficulty levels.
These levels would be namely-
1)  Beginner
2) Intermediate
3) Advanced
Defining these difficulty levels would be as such-
Beginner = 9*9 board with 10 mines or bombs
Intermediate= 16*16 board with 40 mines or bombs
Advanced=24*24 board with 99 mines

We can think of the board as a matrix with rows and columns respective to the difficulty level.

We expect our program to run in the following way-
1) The user will be prompted to first chose his/her difficulty level
2) The board will be initialized depending upon the users choice of difficulty
3) MINES will be placed randomly in the board by "  " 
4) Current status of the board will be shown (It will be just dashes first)
5)User is allowed to enter his input like "x y" where x is the row and y the column the user wishes to "mine" and it is checked if the input is valid or not.
6) if the row/column entered by the user is not equal to the row/column of a bomb, then the board will be updated depending upon the number of bombs in the vicinity of the users desired choice.
7) If suppose the user entered a row/column combination that is equal to the row/column combination of a mine, then the user loses.
8) ) If all the user entered a rows/columns combinations do not matches  to the row/column combination of a mine, then the user wins.
The user keeps on playing until he steps/clicks on a cell having a mine (in this case the user loses) or if he had clicked/stepped on all the safe cell (in this case the user wins).
In this  project ,
data structures (queues and arrays) will be used to perform basic functions like 
 storing randomly  generated mines' x and y coordinates in queues(ENQUEUE) using ENQUEUE function,
 retrieving these mines when the user lose the games by deleting elements  from the front of the queues using DEQUEUE function.

