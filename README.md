Difference between Blindfold Sunfish and Sunfish
=======

This is a modification of the original Sunfish chess engine that can be found <a href='https://github.com/thomasahle/sunfish'>here</a>.

Blindfold doesn't print the board, and I made it a bit easier to play for practicing blindfold chess. You only see the algebraic notation. 
Text to speech only works for OS X since I couldn't get pyttsx to work yet. Also changing it to espeak for linux will work on lines 392/394. 


Sunfish
=======
Sunfish is a simple, but strong chess engine, written in Python, mostly for teaching purposes. Without tables and its simple interface, it takes up just 111 lines of code! Yet it plays at rating 1800-1900 at Lichess. It’s simple open source chess engine under the GPL written by Thomas Dybdahl Ahle in Python for didactic purposes, inspired by Harm Geert Muller's Micro- Max. Sunfish supports the Chess Engine Communication protocol to play with a graphical interface like XBoard or PyChess. 
 The program uses Unicode glyphs to display the pieces within the terminal,making it look a little more chess- like than GNU chess. Moves are inputted by specifying the starting and ending co-ordinates,so the aggressive opening which moves the king's pawn to e4 would be inputted e2e4.Note that this can be slightly longer than the more common algebraic notation(in which the previous move would be written e4),but makes it much easier for computation. In this engine Lower case letters represent black pieces (p,r,n,b,k,q), and upper case letters represent white pieces (P,R,N,B,K,Q).Black-White-Empty matrix(BWE) is solely a listing of strings which represent each square on the board. This matrix is compared with an internally stored matrix within the Chess Engine.This suggests the Chess Engine can understand : 
 
i)where the piece moved from 
 
ii)where it moved to and construct a chess command from it. Moving pawn piece A2 to A4 at the beginning of the game would require command ‘a2a4’.         

The clarity of the Sunfish code provides a great platform for experimenting, be it with evaluation functions, search extensions or anything. Fork it today and see what you can do!

Screenshot
==========

    My move: g8f6
                      
                       
       r n b q k b . r 
       p p p p p p p p 
       . . . . . n . . 
       . . . . . . . . 
       . . . . P . . . 
       . . . . . . . . 
       P P P P . P P P 
       R N B Q K B N R 
                       
                        
    Your move: 


Run it!
=======
Sunfish is self contained in the `sunfish.py` file from the repository. I recommend running it with `pypy` for optimal performance.

It is also possible to run Sunfish as an [XBoard](http://www.gnu.org/software/xboard/)/CECP engine in [PyChess](http://pychess.org), [Arena](http://www.playwitharena.com) or your chess interface of choice. Just add the command `pypy -u xboard.py`. Ruxy Sylwyka has [a note on making it all work on Windows](http://www.talkchess.com/forum/viewtopic.php?topic_view=threads&p=560462).

![Arena Screenshot](http://s29.postimg.org/89gnk99d3/Clipboard01.png)

Features
===========
1. Build around the simple, but deadly efficient MTD-bi search algorithm.
2. Filled with classic as well as modern 'chess engine tricks' for simpler and faster code.
3. Easily adaptive evaluation function through Piece Square Tables.
4. Uses standard Python collections and data structures for clarity and efficiency.

Limitations
===========
Sunfish supports castling, en passant, and promotion. It doesn't however do minor promotion or draws of any kind. All input must be done in simple 'two coordinate' notation, as shown in the screenshot.

On the technical side there are a lot of features that could be interesting to add to Sunfish. For performance, the most important might be a piecelist to save the enumeration of all board squares at every move generation. Other performance optimizations could include dedicated check detection, zobrist hashing and a mutable board representation - perhaps based on bitboards.

The evaluation in Sunfish is not very sophisticated. E.g. we don't distinguish between midgame and endgame. Not much selective deepening is done, no threat detection and the like. Finally Sunfish might benefit from a more advanced move ordering, including such things as killer move and SEE.

Why Sunfish?
============
The name Sunfish actually refers to the [Pygmy Sunfish](http://en.wikipedia.org/wiki/Pygmy_sunfish), which is among the very few fish to start with the letters 'Py'. The use of a fish is in the spirit of great engines such as Stockfish, Zappa and Rybka.

In terms of Heritage, Sunfish borrows much more from [Micro-Max by Geert Muller](http://home.hccnet.nl/h.g.muller/max-src2.html) and [PyChess](http://pychess.org).

![Sunfish logo](https://raw.github.com/thomasahle/sunfish/master/logo/sunfish_large.png)
