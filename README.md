# Flip-Match Card Game

Flip-Match Card Game is a Java-based memory and matching game. It tests your memory and matching skills as you uncover cards to find matching pairs, earn points, and beat the clock. Can you conquer the deck and achieve a perfect score? Play now and test your skills!

## Overview

Flip-Match Card Game is a Java program that implements a graphical user interface (GUI) using Swing components. The game features card flipping, matching logic, scoring, and a timer. The objective of the game is to uncover cards and find matching pairs. Each time a pair is matched, the player earns points. The game is timed, adding an extra challenge to complete the game within a specific time limit.

## Code Structure

The code is well-structured and follows object-oriented principles. Here's an explanation of each part of the code, including the methods:

### Package and Import Statements

The code begins with package and import statements, which define the package and import the necessary classes and libraries for the game.

### Class Definition

The `FlipMatchCardGame` class is defined, which extends the `JFrame` class to create the game window.

### Constant Variables

The code declares several constant variables that define the dimensions of the cards, the total number of cards in the game, the maximum number of matches required to win, and the maximum time allowed for the game.

### Instance Variables

The code declares several instance variables to store card images, card buttons, the currently selected button, the number of matches found, the timer, the elapsed time, and various GUI components such as labels. These variables are used throughout the code to manage the game state and update the GUI.

### Constructor

The constructor of the `FlipMatchCardGame` class sets up the game window and initializes variables. It performs the following tasks:
- Sets the title, size, and layout of the game window.
- Creates panels for cards, header, and footer.
- Initializes variables and lists.
- Populates the `cardImages` list with pairs of card images.
- Shuffles the `cardImages` list.
- Creates `JButton` objects for each card and adds them to the `cardsPanel`.
- Sets up the timer label and score label.
- Adds the panels to the main panel and sets it as the content pane of the `JFrame`.
- Sets the visibility of the `JFrame`.
- Calls the `resetGame()` method to start a new game.
- Sets the `isMatching` flag to `false`.

### CardButtonListener

The `CardButtonListener` class is implemented as an `ActionListener` to handle the logic when a card button is clicked. It performs the following tasks:
- Retrieves the index of the clicked button from the `cardButtons` list.
- Sets the icon of the button to the corresponding image from the `cardImages` list.
- If no card is currently selected, it sets the clicked button as the `selectedButton`.
- If a card is already selected, it compares the images of the selected card and the clicked card.
  - If the images match, it increments the `numMatches` counter and checks if the maximum number of matches is reached.
    - If the maximum number of matches is reached, it stops the timer and shows the game-over message using the `showGameOver()` method.
    - Otherwise, it resets the `selectedButton` and enables all buttons.
  - If the images do not match, it creates a delay using a `Timer` object.
    - After the delay, it resets the icons of the `selectedButton` and the clicked button, enables all buttons, resets the `selectedButton`, and sets the `isMatching` flag to `false`.

### Helper Methods

The code includes several helper methods to perform specific tasks:
- `setEnabledAllButtons(boolean enabled)`: This method sets the enabled state of all buttons. It takes a boolean parameter to determine the state.
- `showGameOver()`: This method is called when the game is over. It displays a message box with the game-over message, the elapsed time, and the score. It provides an option to play again or exit the game.
- `updateScore(int amount)`: This method updates the score label by adding the specified amount to the current score. If the new score reaches or exceeds 100, it calls the `showGameOver()` method.
- `updateTimer()`: This method is called by the timer to update the elapsed time. It increments the `elapsedTime` variable, updates the timer label, and checks if the maximum time is reached. If so, it stops the timer and calls the `showGameOver()` method.
- `resetGame()`: This method resets the game to its initial state. It resets variables, shuffles the `cardImages` list, clears the icons of all buttons, and starts a new timer.

### Main Method

The main method instantiates the `FlipMatchCardGame` class and runs the game by invoking the constructor within the `SwingUtilities.invokeLater()` method.

## How to Play

1. Run the Java program to start the game.
2. The game window will appear, displaying a grid of face-down cards.
3. Click on a card to flip it and reveal the image.
4. Click on another card to flip it and reveal its image.
5. If the images on the two cards match, they will remain face-up, and you earn points.
6. If the images on the two cards do not match, they will flip back face-down after a short delay.
7. Continue flipping cards and finding matching pairs until all pairs are found.
8. The game is timed, so try to find all the pairs before the time runs out.
9. If you find all the pairs before the time runs out, you win the game.
10. If the time runs out before you find all the pairs, you lose the game.
11. The game will display a message box showing your score and elapsed time.
12. You can choose to play again or exit the game.

Enjoy playing the Flip-Match Card Game and have fun testing your memory skills!
