This is my own custom version of the classic game Pong. It was initially created with the help of a tutorial and then I modified the code to fit my own personal tastes (see below for more details).

PLAYING THE GAME
This is a two-player game where both players utilize a keyboard on the same computer to play against each other (or you can play against yourself).

Player 1 controls the left paddle.
w: moves the paddle up
d: moves the paddle down
a: (super) teleports the paddle to match the current y-axis of the ball
d: (super) the next collision with the paddle will reflect the ball 3 times as fast

Player 2 controls the left paddle.
up: moves the paddle up
down: moves the paddle down
right: (super) teleports the paddle to match the current y-axis of the ball
left: (super) the next collision with the paddle will reflect the ball 3 times as fast

The ball moves in a random direction at the start and each time it resets to the center. There is no startup screen; the game will begin as soon as it loads so be ready to go!

The ball starts off slow but will move faster and faster with each paddle collision or with each point scored.

On some random paddle collisions, the ball will split in 2! Only one will be the real ball. The other will be a fake.

Paddles will be stationary at the start of the game and after a teleport move. Once a paddle starts moving, it will keep moving in that direction until it changes direction or reaches the edge of the screen.

Each player only has 5 uses of a "super" move. This includes both the super-reflection and the teleport.

The first player to score 5 points wins!

SETUP
Open the project in your preferred Python IDE or text editor.
Run the main.py file to start the Pong game.
Just like I did with the original tutorial file, feel free to experiment and customize the game to make it your own!
Have fun and enjoy!

CREDIT

This game is based on the Pong With Python and Pygame tutorial created by YouTube user @SMDS_Studio and posted on freeCodeCamp.org's channel. You can find the tutorial here:

https://www.youtube.com/watch?v=tS8F7_X2qB0

The tutorial code is here:

https://github.com/SMDS-Studio/Building-a-New-creative-Pong-

SUMMARY OF CHANGES

-Code refactoring: There was a lot of copy-and-paste so initially I simply changed some of these into functions so as to avoid violating the DRY principle.

-Increased speed: To make the games move faster and prevent deadlocks, I set the speed to steadily increase rather than remaining constant.

-Fixed Supers (Gadgets): I didn't like the name "gadget" so I changed it to "supers" (as in super-powers) but more importantly I fixed them in place so you cannot select different gadgets at the start of the game. The purpose of this decision was to just get players into the action right away. This game is meant to be quick and easy to start and to finish. Since the 4-button control scheme wouldn't accommodate all of the gadgets/supers that were available in the original tutorial, I implemented the dummy ball as a random event.

-Super/Gadget Controls: The tutorial used left/a for one super and right/d for the other. In my setup, teleport is always whatever button is away from the center of the screen (a or right) while the super-smack reflection is always whatever key is towards the center of the screen (d or left). I kind of imagine this as teleporting being sort of like backpedaling because you aren't going to catch the ball while the super smack is like you are leaning in and really hitting that ball.

-Floating Paddles: In the original game, the paddles only moved while a key was pressed. However, I found that this created issues where one player could interrupt another player's movement by pressing keys. To fix this, the paddles "float" meaning they are always moving and pressing a key is only needed to change direction. This fixed the input interrupt problem and in my opinion it also makes the game more interesting/challenging.

-Font: The tutorial used calibri as the font for all text but this turned out to be problematic on my Debian Linux computer. I switched the font to arial which was not an issue since arial was included in the distro be default.

-Endgame: I raised the endgame points to 5 rather than 3 because my other changes already cause the game to move really fast. I also froze the x-axis movement of the ball when the win message was shown because sometimes the game would say that one player had won but a few seconds later changed it to say that the other player had won. I suspect the ball was still being "moved" even though it wasn't drawn and was scoring points in the background.
