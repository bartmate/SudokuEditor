# SudokuEditor for Creating New Sudoku Puzzles

## Short Decription

This little Python based Sudoku Editor is mainly for creating Sudoku puzzles. It has two independent undo-redo list in it:
* One for the puzzle creation
* One for the solving process

In its current form it is developed in Jupyter Notebook. To execute the application, you have to execute the cells one-by-one.

Beside traditional Sudoku, the editor supports the features below. All of them are UI features, meaning that there is no check or automatism during the solution.

| Feature                | Remark      |
| -------------------  |-------------| 
| Filled circle           | Typically used for odd-cells. | 
| Empty circle           |  | 
| Filled square           | Typically used for even-cells.  | 
| Empty square           |  | 
| Cell with 4 arrows outwards | Typically used for indicating that the cell value is higher than its neighbors. | 
| Cell with 4 arrows inwards | Typically used for indicating that the cell value is lower than its neighbors. | 

## Plans

I plan to add further elements like support for:
* Thermometers
* Killer Cages
* Summing arrows
* Kropki dots
* Out-of-grid clues (like sandwich clues)
* etc...

Further plans for solution-related functionalities:
* Highlighting naked singles
* Highlighting doubles, triples, ...
* Highlighting when there is only one place for a digit in box/row/column
* Highlighting when digits in a row/column in a box can cause that digit can be deleted in the other boxes in the same row/column.
* Checking if the sudoku is solvable from the current position
 * If there are more solutions: how many.
* Save/Load (including the two undo/redo lists)

## Short-term TODO-s

* Adding two-cell shapes (like kropki dots / relational signs)
* Adding lines for thermo-s

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
| Alt-s         | Rotating among shapes | 1-cell shapes (no selection needed): None -> Filled circle -> Empty circle -> Filled square -> Empty square -> Min cell -> Max cell -> None |

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

