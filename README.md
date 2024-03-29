# flipmatchcardgame
Flip-Match Card Game tests your memory and matching skills. Uncover cards to find matching pairs, earn points, and beat the clock. Can you conquer the deck and achieve a perfect score? Play now and test your skills


Flip-Match Card Game is a Java-based memory and matching game. The code implements a graphical user interface using Swing components and features card flipping, matching logic, scoring, and a timer. Players uncover cards to find matching pairs, earning points, and aiming to complete the game within a time limit. The code is well-structured, with separate classes for the game logic, event handling, and graphical elements. Enjoy a challenging and entertaining card matching experience! 


explanation of each part of the code, including the methods:

Package and Import Statements:
The code begins with package and import statements, which define the package and import the necessary classes and libraries for the game.

Class Definition:
The FlipMatchCardGame class is defined, which extends the JFrame class to create the game window.

Constant Variables:
The following constant variables are declared:

CARD_WIDTH and CARD_HEIGHT: The dimensions of the cards.
NUM_CARDS: The total number of cards in the game.
MAX_MATCHES: The maximum number of matches required to win the game.
MAX_TIME_SECONDS: The maximum time allowed for the game in seconds.
Instance Variables:
The following instance variables are declared:
cardImages: A list to store the card images.
cardStack: A stack to store the card images for shuffling.
cardButtons: A list to store the card buttons.
selectedButton: A reference to the currently selected button.
numMatches: The number of matches found.
timer: A timer object to track the elapsed time.
elapsedTime: The elapsed time in seconds.
timerLabel: A label to display the elapsed time.
scoreLabel: A label to display the score.
isMatching: A flag to indicate if cards are currently being matched.
Constructor:
The constructor of the FlipMatchCardGame class sets up the game window and initializes variables. Here's what it does:
Sets the title, size, and layout of the game window.
Creates panels for cards, header, and footer.
Initializes variables and lists.
Populates the cardImages list with pairs of card images.
Shuffles the cardImages list.
Creates JButton objects for each card and adds them to the cardsPanel.
Sets up the timerLabel and scoreLabel.
Adds the panels to the mainPanel and sets it as the content pane of the JFrame.
Sets the visibility of the JFrame.
Calls the resetGame() method to start a new game.
Sets the isMatching flag to false.
CardButtonListener:
The CardButtonListener class is implemented as an ActionListener to handle the logic when a card button is clicked. Here's what it does:
When a button is clicked, it retrieves the index of the clicked button from the cardButtons list.
It sets the icon of the button to the corresponding image from the cardImages list.
If no card is currently selected, it sets the clicked button as the selectedButton.
If a card is already selected, it compares the images of the selected card and the clicked card.
If the images match, it increments the numMatches counter and checks if the maximum number of matches is reached. If so, it stops the timer and shows the game-over message using the showGameOver() method. Otherwise, it resets the selectedButton and enables all buttons.
If the images do not match, it creates a delay using a Timer object. After the delay, it resets the icons of the selectedButton and the clicked button, enables all buttons, and resets the selectedButton. It also sets the isMatching flag to false.
Helper Methods:
setEnabledAllButtons(boolean enabled): This method sets the enabled state of all buttons. It takes a boolean parameter to determine the state.
showGameOver(): This method is called when the game is over. It displays a message box with the game-over message, the elapsed time, and the score. It provides an option to play again or exit the game.
updateScore(int amount): This method updates the score label by adding the specified amount to the current score. If the new score reaches or exceeds 100, it calls the showGameOver() method.
updateTimer(): This method is called by the timer to update the elapsed time. It increments the elapsedTime variable, updates the timer label, and checks if the maximum time is reached. If so, it stops the timer and calls the showGameOver() method.
resetGame(): This method resets the game to its initial state. It resets variables, shuffles the cardImages list, clears the icons of all buttons, and starts a new timer.
Main Method:
The main method instantiates the FlipMatchCardGame class and runs the game by invoking the constructor within the SwingUtilities.invokeLater() method.
That's a detailed explanation of the code structure and the purpose of each part and method within the Flip-Match Card Game implementation.





this project use in my data structure coure 
thats why i use stack structure 
In the Flip-Match Card Game code, a stack is used to store the card images for shuffling. Here's an explanation of how the stack is used:

Declaration: The stack is declared as an instance variable of the FlipMatchCardGame class. It is defined as follows:

java
Copy
private Stack<ImageIcon> cardStack;
Initialization: The stack is initialized in the constructor of the FlipMatchCardGame class. Here's the relevant code:

java
Copy
cardStack = new Stack<>();
Populating the Stack: After initializing the stack, the code populates it with card images in the constructor. Here's the relevant code:

java
Copy
for (int i = 0; i < NUM_CARDS / 2; i++) {
    cardStack.push(cardImages.get(i));
    cardStack.push(cardImages.get(i));
}
In this code, the cardImages list contains pairs of card images. The code uses a loop to iterate over half the number of cards (NUM_CARDS / 2). For each card image, it pushes it onto the stack twice. This results in having two identical card images on the stack for each card in the game.

Shuffling the Stack: After populating the stack, the code shuffles it to randomize the order of the card images. Here's the relevant code:

java
Copy
Collections.shuffle(cardStack);
The Collections.shuffle() method is used to randomly shuffle the elements in the stack. This ensures that the card images are not in a predictable order when they are later retrieved from the stack during gameplay.

Retrieving Card Images: During gameplay, when creating the card buttons, the code retrieves card images from the stack. Here's the relevant code within the constructor:

java
Copy
for (JButton button : cardButtons) {
    ImageIcon cardImage = cardStack.pop();
    button.setIcon(cardImage);
}
The code uses a for-each loop to iterate over each button in the cardButtons list. It uses the pop() method of the stack to retrieve and remove the topmost card image from the stack. The retrieved card image is then set as the icon of the current button.

By using a stack to store the card images, the code ensures that the images are shuffled and randomly distributed across the card buttons each time a new game is started. This adds an element of unpredictability and challenge to the gameplay experience.
