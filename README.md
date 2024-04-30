# Security-Java-Username-Project

This Java program, named UsernameChecker, prompts the user to enter a username and then checks its security based on specified criteria. Using the Scanner class for input, the program evaluates the username's security through the isSecureUsername method. The method verifies that the username is between 8 and 20 characters long, contains both letters and digits, and consists solely of alphanumeric characters (no special characters allowed). If the username meets these requirements, the program confirms that it is secure; otherwise, it declares the username not secure. This tool is designed to enforce strong username standards to enhance account security.


    import java.util.Scanner;

    public class UsernameChecker {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter your username: ");
        String username = input.nextLine();

        if (isSecureUsername(username)) {
            System.out.println("Your username is secure.");
        } else {
            System.out.println("Your username is not secure.");
        }
    }

    public static boolean isSecureUsername(String username) {
        if (username.length() < 8 || username.length() > 20) {
            return false;
        }

        if (!username.matches(".*[a-zA-Z].*")) {
            return false;
        }

        if (!username.matches(".*[0-9].*")) {
            return false;
        }

        if (!username.matches("^[a-zA-Z0-9]*$")) {
            return false;
        }

        return true;
    }
}
