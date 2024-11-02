# BlackJack-games
## Blackjack Game Documentation

This Blackjack game is implemented in Java using the Swing library for the graphical user interface. The game simulates a simple blackjack game between a player and a dealer.

### Classes and Their Functions

#### 1. **Card Class**
- **Attributes**:
  - `value`: A `String` that represents the card value (e.g., "1", "2", ..., "10", "J", "Q", "K").
  - `type`: A `String` that represents the suit of the card (e.g., "C" for Clubs, "D" for Diamonds, "H" for Hearts, "S" for Spades).
- **Methods**:
  - `toString()`: Returns a string representation of the card (e.g., "10-H").
  - `getValue()`: Returns the numerical value of the card for scoring in Blackjack. Jacks, Queens, and Kings are worth 10 points, Aces can be 1 or 11, and other cards are worth their face value.
  - `isAce()`: Checks if the card is an Ace.
  - `getImagePath()`: Provides the path to the image file corresponding to the card.

#### 2. **BlackJack Class**
- **Attributes**:
  - `deck`: An `ArrayList` of `Card` objects representing the deck of cards.
  - `random`: A `Random` object for shuffling the deck.
  - `dealerHand` and `playerHand`: `ArrayList` of `Card` objects representing the dealer's and player's hands, respectively.
  - `hiddenCard`: A `Card` object representing the dealer's hidden card.
  - `dealerSum` and `playerSum`: Integers tracking the total points of the dealer's and player's hands.
  - `dealerAceCount` and `playerAceCount`: Integers tracking the number of Aces in the dealer's and player's hands.
- **GUI Components**:
  - `frame`: The main window of the application.
  - `gamePanel`: A `JPanel` that handles drawing the cards and game messages.
  - `buttonPanel`: A `JPanel` containing buttons for player actions.
  - `hitButton` and `stayButton`: Buttons allowing the player to take a card or hold their hand.
- **Methods**:
  - `startGame()`: Initializes the game by shuffling the deck and dealing cards.
  - `buildDeck()`: Generates a standard deck of 52 cards.
  - `shuffleDeck()`: Shuffles the cards in the deck.
  - `reducePlayerAce()` and `reduceDealerAce()`: Adjust the score when the player or dealer's total exceeds 21, converting Aces from 11 points to 1 point if beneficial.
  - `toString()`: Overrides the `Object.toString()` method to return a string representation of the game's state.
- **Game Logic**:
  - The game starts by dealing two cards to both the player and the dealer, with one of the dealer's cards remaining hidden.
  - The player can choose to "Hit" to take another card or "Stay" to hold their hand.
  - The game continues until the player chooses to stay or exceeds 21 points.
  - If the player stays, the dealer reveals their hidden card and may take additional cards according to Blackjack rules (typically hitting until reaching a score of 17 or higher).
  - The winner is determined based on whose score is closest to 21 without exceeding it.

### Graphical User Interface (GUI)

The GUI is built using Java Swing and custom painting on a JPanel. Cards are represented as images, and the game's status is displayed textually within the panel. Interaction is managed through buttons located at the bottom of the window.

### Possible Enhancements

- **Betting System**: Allow players to bet chips on each hand.
- **Restart Functionality**: Implement a button to restart the game without needing to relaunch the application.
- **Enhanced UI and Sounds**: Improve the visual design and add sound effects for actions like shuffling and dealing cards.

This documentation provides an overview of the game's implementation and functionality. The structured approach using OOP principles facilitates understanding and potential future enhancements.
