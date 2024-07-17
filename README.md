import java.util.Scanner;

public class PersonTest {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            // Taking input from user for person details
            System.out.print("Enter name: ");
            String name = scanner.nextLine();

            // Check name length
            if (name.length() > 15) {
                throw new Exception("Name should be of max 15 characters");
            }

            System.out.print("Enter city: ");
            String city = scanner.nextLine();

            // Check valid city
            if (!(city.equalsIgnoreCase("pune") || city.equalsIgnoreCase("mumbai") || city.equalsIgnoreCase("chennai"))) {
                throw new Exception("Please enter city (pune, Mumbai, Chennai) only");
            }

            System.out.print("Enter age: ");
            int age = scanner.nextInt();
            scanner.nextLine();  // Consume newline

            System.out.print("Enter phone number: ");
            String phone = scanner.nextLine();

            // Check phone number length
            if (phone.length() != 10 || !phone.matches("\\d+")) {
                throw new Exception("Enter valid 10-digit number");
            }

            // Create Person object with correct input
            Person person = new Person(name, city, age, phone);

            // Display person details
            System.out.println("Person Details:");
            System.out.println("Name: " + person.getName());
            System.out.println("City: " + person.getCity());
            System.out.println("Age: " + person.getAge());
            System.out.println("Phone: " + person.getPhone());

        } catch (Exception e) {
            // Print exception message and terminate the program
            System.out.println(e.getMessage());
        } finally {
            scanner.close();
        }
    }
}
