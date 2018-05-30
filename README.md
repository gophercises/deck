# Exercise #9: Deck of Cards

[![exercise status: released](https://img.shields.io/badge/exercise%20status-released-green.svg?style=for-the-badge)](https://gophercises.com/exercises/deck)

## Exercise details

In this exercise we are going to create a package that can be used to build decks of cards. You can learn a lot simply coding this on your own, but I am going to specifically include the following topics:

1. Sorting (using the [sort](https://golang.org/pkg/sort/) package)
2. Shuffling with permutations (using the [math/rand](https://golang.org/pkg/math/rand/) package)
3. `go generate` with [stringer](https://godoc.org/golang.org/x/tools/cmd/stringer)
4. Functional options (for practice)

Along the way we will also learn a little bit about constants, iota, and other aspects of using Go.

*NOTE: We will be using this package in the next two Gophercises exercises, so if you opt to write it on your own you may want to work on at least the next exercise before watching the videos. That will help you udnerstand how this package will be used and allow you to design a much better API.*

To start, create a package named `deck`, and in it create a type named `Card` that will be exported, and is used to represent a playing card. Try not to add any game-specific logic to the `Card` type and instead focus on attributes that are true of a card regardless of the game you are playing. For instance, an "ace of hearts" could be represented as a card with a numeric value of 1, and a suit of hearts, but we want to avoid giving it a specific score value as that can change from game to game.

After creating the `Card` type and any helper methods you deem useful, add a `New` function to the deck package that can be used to generate a deck of cards (represented as `[]Card` should be fine - I don't believe we will need a custom `Deck` type). I will be writing my code to generate the cards in the default order a deck of cards comes in (shown below), but you can do this however you see fit.

*NOTE: A brand new deck of cards is typically sorted by suit, so that the 13 cards in the deck are all spades, the next 13 diamonds, the next 13 clubs, and the last 13 hearts. Some decks have Jokers, but I'm going to leave those out for now. Inside each suit the cards are sorted in the order A,1,2,3,...,10,J,Q,K.*

Once you have your `New` function working, add some options to be used when creating a deck of cards. I'll be using functional options for these, but you can experiment with other approaches if you want. I suggest implementing the following options:

- An option to sort the cards with a user-defined comparison function. The `sort` package in the standard library can be used here, and expects a `less(i, j int) bool` function.
- A default comparison function that can be used with the sorting option.
- An option to shuffle the cards.
- An option to add an arbitrary number of jokers to the deck.
- An option to filter out specific cards. Many card games are played without 2s and 3s, while others might filter out other cards. We can provide a generic way to handle this as an option.
- An option to construct a single deck composed of multiple decks. This is used often enough in games like blackjack that having an option to build a deck of cards with say 3 standard decks can be useful.


## Bonus

Once you have your package created, try to comment the code if you haven't already and look at how to run a local godoc server. You should take some time to learn a little about how you can document your code to make it easier for future developers to use.
