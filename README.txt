#### Group Member:
Henry Dihardjo
Ian Antonius Suwandi

#### Class :
CPSC4610 (Artificial Inteligent)

#### Game:
Reversi

#### How to run:

The code can be run from the command line (for windows) or terminal (for mac).
First , user have to go to the directory where the file is saved.
Then , user can run this following line :

        python3 reversiMiniMax.py

(This requires python 3 to run the program)

Then user has to choose the level of difficulty for the game after this following
instruction is printed : 

        Choose your desired level of difficulty (Easy/Medium/Hard) : 

(the input is not case sensitive , but has to be filled with exact word)
(Example : it will accept "eaSY" but will not accept "Esay")

Next , user has to choose which color they want to play the beads after this 
following line :

        Choose your color (black or white) :

(the input is not case sensitive , but has to be filled with exact word)

Finally , user can enjoy the game fighting against the AI .
The program will show the updated board every time user or AI make a move.

Initial board:
|_|_|_|_|_|_|_|_|       
|_|_|_|_|_|_|_|_|
|_|_|_|_|_|_|_|_|
|_|_|_|b|w|_|_|_|
|_|_|_|w|b|_|_|_|
|_|_|_|_|_|_|_|_|
|_|_|_|_|_|_|_|_|
|_|_|_|_|_|_|_|_|

updated board after several move:
|_|_|_|_|_|_|_|_|
|_|_|_|_|_|_|_|_|
|_|_|_|_|b|b|b|_|
|_|_|_|b|w|_|_|_|
|_|_|_|w|b|_|_|_|
|_|_|_|_|_|_|_|_|
|_|_|_|_|_|_|_|_|
|_|_|_|_|_|_|_|_|

(black beads is displayed as 'b' and white beads is displayed as 'w' in the board)

all available move will be provided for user in the list of array of [row,column]
example:

Available Spots:
[ 2 , 5 ]
[ 2 , 7 ]
[ 3 , 4 ]
[ 4 , 3 ]
[ 5 , 6 ]
[ 6 , 5 ]

(row and column is in range of 1 to 8 )

To make a move , user have to provide input of integer of the row and column they
want to choose from provided available spots after the following line:

        row:
        <user input>
        column:
        <user input>

(<user input> is in range of 1 to 8 )

user can enjoy the game with the AI bot until the game is finished.

Finished condition if the board satisfy at least one of the following condition:
    - No more black bead in the board
    - No more white bead in the board
    - No more empty space in the board

In the end of the game , The system will print out the result in number of beads 
each color have . Example : 

    Game has Ended
    White Score(AI):  51
    Black Score (Player):  13



#### Algorithm : 

    The algorithm used to create the AI bot is using Minimax with alpha beta pruning.
    The algorithm is designed to maximize the score of the game by placing the beads 
    that will result the highest score . Some spots has a higher value than other spot,
    and some has negative value because it can lead to condition later in the game. 
    We modified the minimax algorithm to alpha pruning to reduce the computation cost as 
    looking ahead to scan the entire tree is not cheap. With pruning, it will cut off any 
    moves that are obviously disadvantage to the AI. The function of alpha-beta pruning will 
    return a score which will then translated into move coordinates. The actual bead placement
    will take in another function called bestMove which will call the alphaBeta function to 
    maximize or minimize the score and each moves will be compared to one another. The move
    with the most point will be initiated.  

    Some additional filter is also added to the function depending on the level of 
    difficulty chosen :

    Different level of difficulty will have different depth of the Minimax algorithm.
    The harder the difficulty will result on a deeper depth.

    "Medium" and "Hard" level will contain function to eliminate the bad spots that can lead
    to bad circumtances in the later game .

    Only a "Hard" level have the ability to do "Priority move" that will result to better 
    circumtances in the later game.
    

#### Demo (Youtube link):
	https://youtu.be/kdnOEfhUJ88
