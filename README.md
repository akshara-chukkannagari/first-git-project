first-git-project
=================

public class GuessGame {

	public static void main(String[] args) {
		int maxNumber = 1024,
			numberOfGuesses = 0,
			guess = 0;

		// get a random integer between 1 and maxNumber
		int number = (int)(Math.random() * maxNumber + 1);	// 1 <= number <= maxNumber

		// compute maximum number of guesses the user should need
		int maxGuesses = (int)(Math.log(maxNumber) / Math.log(2));

		// just some output to introduce the rules of the game
		System.out.println("Guess my number");
		System.out.println("---------------\n");
		System.out.println("I am thinking of an integer number between 1 and " + maxNumber + ".");
		System.out.println("Try and guess this number!\n");

		// get input from user until he guesses the right number
		do {
			numberOfGuesses = numberOfGuesses + 1;
			guess = Keyboard.readInt(numberOfGuesses + ". guess:");

			// give the user a hint whether his guess is less or greater than the number
			if (number < guess)
				System.out.println("My number is less than your guess. Try again...");
			else if (number > guess)
				System.out.println("My number is greater than your guess. Try again...");

		} while (guess != number);

		// ok, the user found out the correct number
		System.out.println("\nCongratulations! I really thought of the number " + number + ".");

		// rate the performance
		System.out.print("It took you " + numberOfGuesses + " guesses. ");
		if (numberOfGuesses < maxGuesses)
			System.out.println("Good performance.");
		else if (numberOfGuesses == maxGuesses)
			System.out.println("Fair performance.");
		else
			System.out.println("Poor performance.");
	}

}
