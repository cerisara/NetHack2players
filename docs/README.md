This is a patch to NetHack-3.7 that enables two players to play
nethack collaboratively.
One player controls the main character, while the other player controls her/his pet.

There are several ways you can play with 2 players:

- **Mono-player**: you can play alone and control both the main character moves and then its pet move, sequentially.
- **Hot-seat**: you can play with a friend, both of you sitting in front of the same computer and keyboard.
- **Network**: you can play with a friend through the network as follows:
    - First, player A launches a shared session on her/his (linux) computer by running the "tmate" command (see [https://tmate.io/](https://tmate.io/))
    - Then, player A sends the R/W ssh or web link (given by tmate) to player B
    - Then, player A launches this version of nethack
    - Now, both players can play one after the other, respectively the main character and the pet.
    - As both players control the same session, it's possible to exchange roles at any time, or continue playing alone, etc.

*Disclaimer: this version is an unstable patch on an unstable version of Nethack, so the program may crash at anytime.*

## Pet control

Controlling the pet is very limited, on purpose: basically, you can only move the pet, or let the engine decides on the pet move.
You can not volontary pick objects, you can only see the map around the main character, and if the pet is too far away from the
player, it may not have any move allocated, and you'll have to wait for the main character to find her/his pet back.

This patch is ideal when you (as an experienced NetHack player) want to introduce NetHack to a friend: in that case, let her/him
play the main character, and you should play the pet, explaining her/him all the subtleties of NetHack while you play together.

Technically, as soon as its the pet turn to move, the top line will display the text "PET MOVE" and wait for a move character,
**followed by return**: you have to "enter" after your move on purpose, so that if the other player accidentally keeps on pressing
keys for the main character, you can delete them before pressing enter.
If your move is illegal, the pet will either not move or move as planned by the game engine.

