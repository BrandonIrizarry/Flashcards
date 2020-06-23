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

One idea to (2) is use a function `Card` to set a metatable for each card-entry,  
so that `card.rank`, `card.question`, and `card.answer` work automatically as aliases for the
original numeric indices, without disturbing the number of lines within the data-file itself,
or else make it more verbose and unreadable:

```
Card {
	0,
	"What color is asparagus?"
	"Green."
}

local function Card (card)
	return setmetatable(card, {__index = function (card, key)
		if key == "rank" then
			return card[1]
		elseif key == "question" then
			return card[2]
		elseif key == "answer" then
			return card[3]
		end
	end})
end
```
