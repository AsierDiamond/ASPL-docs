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
SETFONT("dir1/dir2/font.asff") : Chooses a font downloaded in the system for the following text to load, if the font file isnt found, it will                                      switch to Shellfont.asff
```
