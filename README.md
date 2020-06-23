# Flashcards
Barebones flashcard program in Lua.

Run 

`./flashcards <name of deck>`

Decks are to be found in a subdirectory called "cards". The name of a deck corresponds to the
subject represented by the questions in that deck. For example, "cards/forth.lua" corresponds
to deck with questions related to the Forth programming language.

Decks are Lua programs unto themselves, that hold a single table called `data`, which holds
a field called `day` (which is effectively the session number), and a series of card-objects
accessible as `data`'s sequential part.

Ideas:
 - Shuffle cards while in play, while maintaining the same order within the file itself.
 - Refactor some of the variables in `flashcards`, possibly adding fields within a given card object indicating rank (r), question (q),  
 and answer (a).
