# SudokuEditor for Creating New Sudoku Puzzles

## Short Decription

This little Python based Sudoku Editor is mainly for creating Sudoku puzzles. It has two independent undo-redo list in it:
* One for the puzzle creation
* One for the solving process

Currently it supports only traditional Sudoku-s. But I plan to add further elements like support for:
* Thermometers
* Killer Cages
* Coloring
* Summing arrows
* Odd-even signs
* Kropki dots
* Min-max cells
* etc...

In it current form it is developed in Jupyter Notebook. To execute the application, you have to execute the cells one-by-one.

## Controls

### Mouse

| Event         | Effect      |
| ------------- |-------------| 
| Click         | The clicked cell will be the active one (cell with red frame) | 
| Shift-click   | Add the clicked cell to the selection (yellow coloring) | 
| Control-click | Remove the clicked cell from the selection (yellow coloring)  | 


### General Keys

| Event                | Effect      |
| -------------------  |-------------| 
| Arrow keys           | Moving the active cell (cell with red frame) | 
| Shift - Arrow keys   | Adding cells to the selection (yellow coloring) | 
| Control - Arrow keys | Deleting cells from the selection (yellow coloring) | 
| s                    | Toggle - Show/hide options (center pencilmarks) in each cell | 
| Space                | Add/remove the active cell (cell with red frame) to/from the selection (yellow coloring) | 
| Shift - a            | Add all cell to the selection (yellow coloring) | 
| Control - a          | Remove all cells from the selection (yellow coloring) | 

### Puzzle Related Keys

| Event         | Effect      | Remark |
| ------------- |-------------|--------| 
| Alt - 1-9     | Adding a digit to the puzzle        | To reverse use Undo (Alt-u) |
| Alt - u       | Undoing the last puzzle-related step | |
| Control-click | Redoing the next puzzle-related step  | |

### Solution Related Keys

| Event         | Effect      | Remark |
| ------------- |-------------|--------|
| 1-9           | Adding a digit into the active cell to the solution | To reverse use Undo (u) |
| Shift - 1-9   | Deleting the option in the active cell   | To reverse use Undo (u); Use only if the center pm is shown. |
| Control - 1-9 | Adding/deleting a digit as top pencilmark | |
| c             | Show or hide the options (i.e. center pencilmarks) in the selected cells(s) | | 

