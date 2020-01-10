## What is this about?
This page is intended to show the basics of user scripts in the [_SWCombine_](https://www.swcombine.com) online game .

## Reference
The official rules for NPC scripting are located [here](https://www.swcombine.com/rules/?Scripts).

## Where can I use this?
To use a script, you first have to own a *_Custom Type NPC_*. Regular NPCs and droids can't have user scripts attached to it for now.

To get a custom NPC, follow the rules [here](https://www.swcombine.com/rules/?NPCs#Custom_NPCs).
Once you have a custom NPC, you will be able to edit its script via the game's inventory.

## Simple NPC tutorial
A really basic NPC, intended to only speak to the users will have two major functions called in its script:
- `say`: to make the NPC speak
- `add-reponse`: to make the user speak

As a reminder, what I will call *the user* in this documentation refers to the player that is interacting with the NPC. It is not restricted to the owner of the NPC.

Let's start with a basic example:

```
(defun start
  (say "Hello, my name is Dankan, I work for Abraari To.")
  (add-response "Hello there!")
)
```
See? Nothing big and you have your first custom NPC to play with! Now let's break this script down.

```
(defun start
[...]
)
```
This defines the start of a function, called `start`. This is a mandatory function in any NPC script. Technically speaking, when you interact with a NPC is SWC, the game blindly calls the `start` function assigned to it, so if you don't define it in your script it will cause an error.


```
  (say "Hello, my name is Dankan, I work for Abraari To.")
```
The first thing this script does is make the NPC talk and greet the user with some basic information. For now it's just plain text with nothing fancy but we'll find some fun things to do later on.

```
  (add-response "Hello there!")
```
Now the script adds some interaction! With this, the user has an action available to him/her, the same way you can select a line of dialog in any game with user choices. If you omit to add any `add-response` call, the script will add a default clause for the user to be able to finish the interaction. But with this line, the user will greet back the NPC and the interaction will be finished.
