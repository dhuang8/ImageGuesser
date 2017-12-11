# ImageGuesser
## How to compile
compile using the command in the folder
javac -cp "./;./json.jar" ImageGuesser.java
run using the command
java -cp "./;./json.jar" ImageGuesser

When the program starts, follow the instructions.

## external libraries
### json.jar
parses JSON format strings from google search api

## text files
### apikey.txt
contains the google search api key
### highscores.txt
contains scores and times for past players delimited by "?" and "&"
### wordlist.txt
word list delimited by ":"

## Classes
### ImageGuesser
contains the main method that begins the program
### Window
an abstract class that determines the current state of the game and the UI elements to display
### StartWindow
extends Window and begins the game. Displays instructions and requests a player name. Switches to GameWindow on submit
### GameWindow
extends Window and plays the game. Shuffles the word list, keeps score and timer. After 10 pictures, moves to EndWindow
### EndWindow
extends Window. Displays your score and the top high and scores sorts scores. See Score for more information.
#### sort
This sort can be used with any Object that implements Comparable. The sort is an in-place insertion sort with a modified recursive binary search I wrote myself that returns the first elements greater than the search element.
### Score
implements Comparable so they can be used for sorting. A player is greater than another if the score is higher. If both are the same, a player is greater if the time is lower. If both are the same, a player is greater if the name is greater than the other, usually alphabetical order.
### ErrorWindow
extends Window. All other windows will shift to this one if they encounter an error with try/catch
