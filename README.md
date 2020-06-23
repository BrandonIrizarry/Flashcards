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
 - I can't shake that it could be a good idea to merely output the new data-file to stdout,  
and then optionally choose to commit, even if I have to get some shell-scripting involved.
