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

## Boolean logic and loops.

### Loops
Loops work in the following way:
```
LOOP : Starts the loop
ENDLOOP: Ends the loop
```
Every line of code between this 2 lines of code will be played undefinetly until a BREAK line is executed, which would stop the loop.

### If Statements
If statements are a group of lines of code that executes code if a condition is true, the condition is made in Javascript.
```
IF("Condition") :Starts the IF
ENDIF: Ends the IF
//If the condition is true, the lines of code between the IF and END IF lines will be executed, if not, it will be skipped.
``` 
#### Operations
JS Operations are used for IFs to work, if they return a true condition, it will execute. For example IF("2+2==4") will be executed, but IF("2+2==5") would not execute the lines.

For example:
```
START
IF("2+3==5")
PRINT ("Hi")
ENDIF
END
```
The Output should be:
```
Hi
```

#### Key Logs
If conditions can also detect if the last key you pressed is the same as the one you stablished

Example:
```
START
PRINT("Press E!")
LOOP
IF("Keylog==E")
PRINT("Congrats!, you pressed E!")
ENDIF
ENDLOOP
IF
```
The output should be:
```
Press E!
```
If you press E,
```
Press E!
Congrats!, you pressed E!
```
WARNING: Note that keylogs work only IN LOOPS.

## System Variables
Asier System has Variables that lets your program get info from the System

There are several system variables:
```
!time-hour! : Returns the time in a HH-MM-SS Format
!time-date! : Returns the date in a DD-MM-YYYY Format
!battery! : Returns the battery percentage of the device
!mouse_x! : Returns the x position of the mouse
!mouse_y! : Returns the y position of the mouse
!clicked! : Returns a false/true if the mouse is clicked or not
!file("location of file")! : Returns the contents of a local file.
```
System Variables are displayed the same as normal variables.

```
PRINT(!mouse_x!)
```
## Internet
The following commands access the internet.

### Fetching 
To show a fetched content, use $url$

Example:
```
PRINT("$https://extensions.turbowarp.org/hello.txt$")
```
Returns:
```
Hello, world!
```
### Rotur
Asier System uses the account system of Rotur TW, created by mistium, an account system to access things like mailing, messaging, calling, and simple cloud storage. 

To learn more about Rotur, check out https://github.com/RoturTW

#### Rotur commands
Rotur commands are abvialable to interact with the RoturTW ecosystem
##### Authentication
The following rotur commands will help you authenticate to Rotur
```
AUTHTOROTUR : Opens the rotur auth pop-up
DISCONNECTROTUR: Disconnect from Rotur
```
##### Mail
Rotur also proportionates a e-mail environment
```
SENDMAIL("reciever's username","Header","Body") : Lets you send a mail to someone
```
##### Wallet
Rotur also has a virtual currency called Rotur Credits
```
SENDCREDITS("number of credits","username") : Sends a number of rotur credits to someone
```
##### Calling
Rotur proportionates a service to call other users.
```
CALL("username") : Starts rotur calling someone, the audio gets transmitted automatically
```
Note that you need a microphone for you to send audio to the reciever

#### Rotur Variables
Rotur variables work similar as system variables, but they access to your rotur information
```
@username@ : Returns the username of the user
@key("name of the key") : Lets you see a key of your account
@auth_key@ : Returns the Authentication key of your account. WARNING: DO NOT SHARE THIS AUTH KEY WITH ANYONE, ITS THE KEY TO YOUR ACCOUNT AND IF SOMEONE HAS IT THEY WILL HAVE ACCESS TO YOUR ACCOUNT
@transactions@ : Returns the transactions in a JSON format
@users_online@ : Returns the users online in an array
@badges@ : Returns your badges in a JSON format
@balance@ : Returns your balance
```
## AUDIO
This commands lets you play audio
```
PLAYMP3("url") : Plays an MP3 from the web
STOPSOUNDS : Stops all of the sounds
```
Thats all for now!
