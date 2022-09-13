Sole Author: Umar Chaudhry

Intro:
This project, adventure.py, is a text input based game written in python code. The way the game works is that it runs alongside a json file
in the command line prompt, and this json file must contain a dictionary that has specific keys to run the game. Think of the json file
as the main game component containing the story and rules while adventure.py serves as a game engine to play that story and game mechanics.
The adventure.py program will function with any json file that meets later mentioned requirements, but a sample json file map1.json is 
included in the repository.

Example:

RUN THE FILE IN COMMAND PROMPT of Code Editor/Terminal --> "python adventure.py map1.json"

Example Output:
Your goal is to get your laptop and charger and meet your friends to work on MCS 260.  You are standing in UIC's Student Center East, near the revolving doors leading to the main quad.  
To the east is a hallway leading to the bookstore and the escalators.  To the south is the I-card office.  To the north is Panda Express.  The revolving doors to the west don't seem to 
be working right now.
> north (user input)
You are in Panda Express, surrounded by students eating lo mein.  The only exit is to the south.
> south (user input)
Your goal is to get your laptop and charger and meet your friends to work on MCS 260.  You are standing in UIC's Student Center East, near the revolving doors leading to the main quad.  To the east is a hallway leading to the bookstore and the escalators.  To the south is the I-card office.  To the north is Panda Express.  The revolving doors to the west don't seem to be working right now.
> east (user input)
This is the main hallway of SCE, with the escalator to the north, the bookstore to the south, the Halsted lobby to the east, and the quad lobby to the west.
>

Description of JSON file requirements:

As you may be able to tell, this game functions by there being multiple places one can go by inputing the direction of travel, and all of these places have similar actions that can either 
be done or not. For example, the "west" direction in the first "room" of the game was unreachable while the others were places the user was able to go to, and in some "rooms", there are
multiple directions of travel while others may only have one like in the Pandas Express location. These game mechanics of whether or not a location is reachable or how many directions of
travel there are, all of these aspects are decided by the json file keys. These json file keys are actually dictionaries themselves by each key being named after the location the player
is in, and the dictionaries contained in each of these keys have their own data, the keys are "description", "exits", "mustvisit", and "roomtype". The "description" key contains the text 
that is printed in the command prompt to describe the location the player is in. The "exits" key contains the directions of travel that are available to the player and the names of those 
locations that are available to go to. The "mustvisit" key contains a boolean of either True or False that describes whether or not the user must go to this location to win the game. The 
"roomtype" key contains text that tells whether or not the location the player is in triggers a win or lose situation by the key containing either a "normal", "win", or "lose" value.

Example of JSON file connection to game output:

Game output:
Your goal is to get your laptop and charger and meet your friends to work on MCS 260.  You are standing in UIC's Student Center East, near the revolving doors leading to the main quad.  
To the east is a hallway leading to the bookstore and the escalators.  To the south is the I-card office.  To the north is Panda Express.  The revolving doors to the west don't seem to 
be working right now.
> north (user input)

Connected JSON file key:
"start": {
    "description": "Your goal is to get your laptop and charger and meet your friends to work on MCS 260.  You are standing in UIC's Student Center East, near the revolving doors leading to the main quad.  To the east is a hallway leading to the bookstore and the escalators.  To the south is the I-card office.  To the north is Panda Express.  The revolving doors to the west don't seem to be working right now.",
    "exits": {
      "north": "panda",
      "south": "cardoffice",
      "east": "hallway"
    },
    "mustvisit": false,
    "roomtype": "normal"

