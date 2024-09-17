import java.util.Scanner;
public class RockPaperScissors {
   
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        String[] rps = {"Rock", "Paper", "Scissors"};
        
        String computerMove;

        String playerMove;
        boolean playAgain = true;

        while (playAgain) {
            int computerChoice = (int) (Math.random() * 3);
            computerMove = rps[computerChoice];

            System.out.println("Enter your move (Rock, Paper, Scissors). To exit the game, type \"exit\": ");
            playerMove = scanner.nextLine();

            if (playerMove.equalsIgnoreCase("exit")) {
                playAgain = false;
                break;
            }

            if (!playerMove.equalsIgnoreCase("Rock") && !playerMove.equalsIgnoreCase("Paper") && !playerMove.equalsIgnoreCase("Scissors")) {
                System.out.println("Invalid move, please try again.");
            } else {
                System.out.println("Computer move: " + computerMove);

                if (playerMove.equalsIgnoreCase(computerMove)) {
                    System.out.println("It's a tie!");
                } else if (playerMove.equalsIgnoreCase("Rock") && computerMove.equals("Scissors") ||
                           playerMove.equalsIgnoreCase("Paper") && computerMove.equals("Rock") ||
                           playerMove.equalsIgnoreCase("Scissors") && computerMove.equals("Paper")) {
                    System.out.println("You win!");
                } else {
                    System.out.println("You lose!");
                }
            }

            System.out.print("Do you want to play again? (yes/no): ");
            String response = scanner.nextLine();
            playAgain = response.equalsIgnoreCase("yes");
        }

        scanner.close();
        System.out.println("Thank you for playing! Goodbye.");
    }
}
