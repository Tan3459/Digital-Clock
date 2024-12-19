# Digital Clock

This project implements a simple digital clock using Python and the Tkinter library. The digital clock displays the current time in hours, minutes, and seconds, as well as the date. The time is updated every second.

## Features

- **Real-time Clock**: Displays the current time in HH:MM:SS AM/PM format.
- **Date Display**: Shows the current date in MM/DD/YY format.
- **Customizable UI**: Configured with a black background, white text, and bold Calibri font.

## Requirements

- Python 3.x
- Tkinter (comes pre-installed with Python on most platforms)

## Installation

1. Clone or download this repository.
2. Ensure you have Python 3.x installed on your system.

## Usage

1. Open the terminal or command prompt.
2. Navigate to the directory containing the script.
3. Run the script using the command:

   ```bash
   python digitalclock.py
   ```

4. A window will appear displaying the digital clock.

## Code Explanation

### Imports

```python
import tkinter as tk
from time import strftime
```
- `tkinter`: Used to create the graphical user interface (GUI).
- `strftime`: Retrieves the current time and formats it as a string.

### Main Window

```python
root = tk.Tk()
root.title("DIGITAL CLOCK")
```
- Initializes the main application window with the title "DIGITAL CLOCK".

### Clock Update Function

```python
def time():
    string = strftime('%H:%M:%S %p \n %D')
    label.config(text=string)
    label.after(1000, time)
```
- Fetches the current time and date using `strftime`.
- Updates the `label` widget with the new time and date.
- Calls itself recursively every 1000 milliseconds (1 second) to refresh the clock.

### Label Configuration

```python
label = tk.Label(root, font=('calibri', 50, 'bold'), background='black', foreground='white')
label.pack(anchor='center')
```
- Configures the `label` widget to display the clock with:
  - **Font**: Calibri, size 50, bold.
  - **Background**: Black.
  - **Foreground**: White.
- Anchored to the center of the window.

### Event Loop

```python
time()
root.mainloop()
```
- Calls the `time` function to start the clock.
- Enters the Tkinter event loop to keep the application running.

## Customization

- **Font and Size**: Modify the `font` parameter in the `Label` widget.
- **Colors**: Change the `background` and `foreground` parameters.
- **Format**: Adjust the `strftime` format string in the `time` function.

## Example Output

The clock window will display:

```
12:34:56 PM
12/19/24
```
