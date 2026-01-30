# Age-exception-
// Custom Exception Class (Checked Exception)
class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}

public class ExceptionDemo {

    // Method that throws custom exception
    static void checkAge(int age) throws InvalidAgeException {
        if(age < 18) {
            throw new InvalidAgeException("Age must be 18 or above to register!");
        }
        System.out.println("Registration successful!");
    }

    public static void main(String[] args) {

        try {
            // Runtime Exception Example
            int a = 10;
            int b = 0;
            int result = a / b;   // ArithmeticException
            System.out.println(result);

        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero!");

        } finally {
            // Cleanup code
            System.out.println("Finally block executed (cleanup done)");
        }

        // Handling checked exception
        try {
            checkAge(15);
        } catch (InvalidAgeException e) {
            System.out.println("Custom Exception: " + e.getMessage());
        }

        // Logging exception (simple logging)
        try {
            String name = null;
            System.out.println(name.length()); // NullPointerException

        } catch (Exception e) {
            System.out.println("Logged Error: " + e);
        }
    }
}
