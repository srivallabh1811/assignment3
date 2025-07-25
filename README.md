# assignment 3
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("Choose a shape (Circle(c) / Rectangle(r)) or type 'exit' to quit:");
            String choice = scanner.nextLine().trim().toLowerCase();

            if (choice.equals("exit")) {
                System.out.println("Exiting program.");
                break;
            }

            Shape shape = null;

            if (choice.equals("c")) {
                System.out.print("Enter the radius of the circle: ");
                double radius = scanner.nextDouble();
                scanner.nextLine(); // Consume newline
                shape = new Circle(radius);
            } else if (choice.equals("r")) {
                System.out.print("Enter the width of the rectangle: ");
                double width = scanner.nextDouble();
                System.out.print("Enter the height of the rectangle: ");
                double height = scanner.nextDouble();
                scanner.nextLine(); // Consume newline
                shape = new Rectangle(width, height);
            } else {
                System.out.println("Invalid shape choice. Please try again.");
                continue;
            }

            System.out.println("Shape: " + shape.getName());
            System.out.println("Area: " + shape.area());
            System.out.println("Perimeter: " + shape.perimeter());
        }

        scanner.close();
    }
}
