# BASIC Computer Games

## Animal

Unlike other computer games in which the computer picks a number or a letter and you must guess what it is, in this game *you* thing of an animal and the *computer* asks you questions and tries to guess the name of your animal.
If the computer guesses incorrectly, it will ask you for a question that differentiates the animal it guessed from the one you were thinkg of. In this way the computer "learns" new animals.
Questions to differentiate new animals should be input without a question mark.

THis version of the game does not have a SAVE feature. If your system allows, you may modify the program to save array A$, then reload the array when you want to play the game again. This way you can save what the computer learns over a series of games.

At any time if you reply "LIST" to the question "ARE YOU THINKING OF AN ANIMAL," the computer will tell you all the animals it kowns so far.

The program starts originally by knowing only FISH and BIRD. As you build up a file of animals you should use broad, general questions first and then narrow down to more specific ones with later animals. For example, if an elephant was to be you first animal, the computer would ask for a question to distinguish an elephant from a bird. Naturelly there are hundres of possibilities, however, if you plan to build a large file of animals a good question would be  "IS IT A MAMMAL."

This program can be easily modified to deal with categories of things other than animals by simply modifying the initial data in Line 530 and the dialogue references to animals in lines 10, 40, 50, 130, 230, 240, and 600. In an educational environment, this would be a valuable program to teach the distinguishing characteristics of many classes of objects — rock formations, geography, marine life, cell strutures, etc.

Originally developed by Arthur Luehrmann at Darthmouth College, Animal was subsequently shortened and modified by Nathan Teichholtz at DEC and Steve North at Creative Computing.
