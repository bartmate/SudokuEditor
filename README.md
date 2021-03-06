# SudokuEditor for Creating New Sudoku Puzzles

## Short Decription

This little Python based Sudoku Editor is mainly for creating Sudoku puzzles. It has two independent undo-redo list in it:
* One for the puzzle creation
* One for the solving process

The options are automatically handled as one puts numbers into the grid. Depending on the show-level set, not all of them are shown, though it can be set for each cell separately that the options are shown in them. Also, the system automatically show certain combinations:
* Naked Single
* Only-one digit in row, column or box
* Pairs, triples, quadruples, quintupples.

In case of valid thermometers the options are handled automatically, too. Pre-requisit: After drawing the thermo, it must be prepared with <Alt-t>. Preparation means that the program finds the thermometers (in case of invalid ones, some subset of the thermometer lines and bulbs) and translates them onto "less-than" relations between cells. These "less-than" relations are enforced automatically.

In its current form it is developed in Jupyter Notebook. To execute the application, you have to execute the cells one-by-one.

Beside traditional Sudoku, the editor supports the features below. All of them are UI features, meaning that there is no check or automatism during the solution.

| 1-cell Feature       | Remark      |
| -------------------  |-------------| 
| Filled circle           | Typically used for odd-cells. | 
| Empty circle           |  | 
| Filled square           | Typically used for even-cells.  | 
| Empty square           |  | 
| Cell with 4 arrows outwards | Typically used for indicating that the cell value is higher than its neighbors. | 
| Cell with 4 arrows inwards | Typically used for indicating that the cell value is lower than its neighbors. | 
| Thin circle | Typically used for summation arrows to hold the 1-digit sum. | 

| 2-cell Feature       | Remark      |
| -------------------  |-------------| 
| Filled Kropki Dot           | Typically used for indicating 1:2 ratio. | 
| Empty Kropki Dot           |  Typically used for indicating consequtive digits. | 
| Filled Kropki Square            |  | 
| Empty Kropki Square           |  | 
| "X" | Typically used for indicating that the sum of the two neighboring cells is 10. | 
| "V" | Typically used for indicating that the sum of the two neighboring cells is 5. | 
| "<" | Indicating relation between cells. | 
| ">" | Indicating relation between cells. | 
| Thin circle | Typically used for summation arrows to hold the 2-digit sum. | 

| 2-cell Line Segment       | Remark      |
| -------------------  |-------------| 
| Thermo               | Can be used for thermometers. | 
| Thin Line            | Can be used for summation arrow. | 
| Thin Line with Arrow at the Beginning |  Can be used for summation arrow. | 
| Thin Line with Arrow at the End       |  Can be used for summation arrow. | 

## Plans

I plan to add further elements for the puzzles, like support for:
* Killer Cages
* Out-of-grid clues (like sandwich clues)
* Out-of-grid diagonal arrows + diagonal sums
* Circle between two cells showing digits
* Circle among four cells showing digits
* Coloring (as part of puzzle, not as part of solution which is supported already)
* Coloring of 1-cell, 2-cell features
* One or two main diagonal line(s)

Further plans for solution-related functionalities:
* Supporting Knight constraint
* Supporting King constraint
* Supporting "Same-position-in-box" constraint
* Save/Load (including the two undo/redo lists)

## Short-term TODO-s

* Adding bottom left pencilmark (one digit) useful for puzzle creation to note a digit which is known because of the puzzle, but not known according to the current solution state
* Coloring (as part of puzzle, not as part of solution which is supported already)

## Controls

### Mouse

| Event         | Effect      |
| ------------- |-------------| 
| Click         | The clicked cell will be the active one (cell with red frame) | 
| Shift-click   | Add the clicked cell to the selection (yellow coloring) | 
| Ctrl-click    | Remove the clicked cell from the selection (yellow coloring)  | 


### General Keys

| Event                | Effect      |
| -------------------  |-------------| 
| Arrow keys           | Moving the active cell (cell with red frame) | 
| Shift - Arrow keys   | Adding cells to the selection (yellow coloring) | 
| Ctrl - Arrow keys    | Deleting cells from the selection (yellow coloring) | 
| s                    | Toggle - Show/hide options (center pencilmarks) in each cell | 
| Space                | Add/remove the active cell (cell with red frame) to/from the selection (yellow coloring) | 
| Shift-a              | Add all cells to the selection (yellow coloring) | 
| Ctrl-a               | Remove all cells from the selection (yellow coloring) | 
| q                    | Increasing Show-level by one |
| w                    | Decreasing Show-level by one |

### Puzzle Related Keys

| Event         | Effect      | Remark |
| ------------- |-------------|--------| 
| Alt - 1-9     | Adding a digit to the puzzle        | To reverse use Undo (Alt-u) |
| Alt-u         | Undoing the last puzzle-related step | |
| Alt-r         | Redoing the next puzzle-related step  | |
| Alt-s         | Rotating among Shapes | 1-cell shapes (no selection needed): None -> Filled circle -> Empty circle -> Filled square -> Empty square -> Min cell -> Max cell -> 1-digit circle -> None |
| Alt-s         | Rotating among Shapes | 2-cell shapes (2 cells need to be selected): None -> Filled Kropki Dot -> Empty Kropki Dot -> Filled Kropki Square -> Empty Kropki Square -> "X" -> "V" -> "<" -> ">" -> 2-digit circle ->None |
| Alt-l         | Rotating among Line Segments | (2 cells need to be selected): None -> Thermo -> Thin Segment -> Thin Segment with Arrow (beginning) -> Thin Segment with Arrow (end) -> None |
| Alt-t         | Preparing thermometers | A thermometer consists of one bulb and some continuous thermometer line segments. The thermometers can branch. |

### Solution Related Keys

| Event              | Effect      | Remark |
|--------------------|-------------|--------|
| 1-9                | Adding a digit into the active cell to the solution | To reverse use Undo (u) |
| Shift - 1-9        | Deleting the option in the selected cell(s)   | To reverse use Undo (u); Use only if the center pm is shown. |
| Ctrl - 1-9         | Adding/deleting a digit as top pencilmark in the selected cell(s) | |
| o                  | Show or hide the options (i.e. center pencilmarks) in the selected cells(s) | | 
| c                  | Color the selected cell(s) using the current color | Current color is shown in the top left corner | 
| Shift-c            | Set the current color to the next color option | | 
| Ctrl-c             | Set the current color to the previous color option| | 
| f                  | Counting the number of solutions from the current grid | Search up to the maximal number (8) or up to the maximal number of examined nodes (100). | 
| Shift-f            | Searching for the first solution from the current grid | Search up to the maximal number (8) or up to the maximal number of examined nodes (100). | 

