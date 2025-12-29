# ASPL Docs
The documentation of the Asier System Programming Language


## What is ASPL?

ASPL is the official programming language for the Asier System Web OS, the syntax is simple and easy to learn

## Helpful info:
All of the Commands must be in Uppercase, except the contents you want it to operate.
Example:


```
COMMAND("content") is valid
command("content") is NOT valid
```
Asier System uses a central-based coordinates system.


x0 y0 is the center of the canvas
## Essential Syntax

Asier System Requires a minimum of two lines to operate, the commands in this two lines are:
```
START : Tells the System to start the code
END : Tells the System to Stop the code
```
Every piece of code before START and after END will be ignored and considered a comment.
Example
```
START
END
//Smallest syntactically correct ASPL code (9 Bytes)
```
## Printing Text
Asier System prints text accordingly to .asff files (Asier System Font File)
Asier System's default asff font is Shellfont.asff (https://raw.githubusercontent.com/AsierDiamond/Asier-System/refs/heads/main/Shellfont.asff)
You can make or download an asff and set it up to be the font you want to use
There are different ways to render text:
```
PRINT("text") : Prints text.
SPECIALTEXT("text","x","y","colour (in hex)") : Prints text with more customizable parameters
SETFONT("dir1/dir2/font.asff") : Chooses a font downloaded in the system for the following text to load, if the font file isnt found, it will switch to Shellfont.asff
```
## Rendering commands
Asier System uses the HTML canvas to render everything thats seen in the screen. You can render shapes, icns and png images.
There are several commands to render elements:
```
SQUARE("x","y","width","height","colour (in hex)") : Renders a rectangle with a customized position, colour, and dimensions
LINE("x1,"y1","x2","y2","width","colour (in hex)") : Renders a line from one point to another, with a custom witdh and colour
TRI("x1","y1","x2","y2","x3","y3","colour (in hex)") : Renders a triangle with a customized position, colour, and dimensions
BGCOLOUR("colour (in hex)") : Changes the colour of the background.
PIXEL("x","y","colour (in hex)") : Renders a single pixel in a customizable position and colour
IMAGE("x","y","url of image","witdh","height") : Renders an image with a customized position, colour, and dimensions
ICN("icn code", "size", "x","y") : Renders an icn with a customizable x and y position. ICN  is a vector logo system created by Mistium.
CLEARCANVAS : Clears all of the elements in the canvas, including text, shapes, images, icns...
```
## Variables
There are many commands that implement variables to ASPL
```
CREATEVAR("Name") : Creates a variable with a custom name
SETVAR("Name","Value") : Sets a value to a variable
ADDVAR("Name","Number to sum") : Sums a number to the already existing variable, if the variable isnt a number, it will return a NaN (Not a number)
```
### Showing and Using Variables
To use a variable, you can use the %Variable Name% in any field of a command, it will be replaced with the variable indicated

For Example:
```
START
CREATEVAR("test")
SETVAR("test","10")
PRINT("The value of test is: %test%")
ADDVAR("test","1")
PRINT("The value of test is: %test%")
END
```
The output is:
```
The value of test is: 10
The value of test is: 11
```
