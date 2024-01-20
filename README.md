<div style="background-color:tomato;">import java.util.Scanner;</div>

public class perfectcalculator {
    public static void main(String args[]) {
        try {
            Scanner input = new Scanner(System.in);

            System.out.print("Enter first number: ");
            double num1 = input.nextDouble();

            System.out.print("Enter second number: ");
            double num2 = input.nextDouble();

            System.out.print("Enter a valid operator (+, -, *, /, %): ");
            char operator = input.next().charAt(0);

            ArithmeticCalculator calculator = new ArithmeticCalculator();
            calculator.performOperation(operator, num1, num2);

        } catch (Exception e) {
            System.out.println("Invalid input. Please enter numeric values.");
        }
    }
}

class ArithmeticCalculator {
    void performOperation(char operator, double num1, double num2) {
        double result;

        switch (operator) {
            case '+':
                result = num1 + num2;
                System.out.printf("Addition is: %.2f%n", result);
                break;
            case '-':
                result = num1 - num2;
                System.out.printf("Subtraction is: %.2f%n", result);
                break;
            case '*':
                result = num1 * num2;
                System.out.printf("Multiplication is: %.2f%n", result);
                break;
            case '/':
                if (num2 == 0) {
                    System.out.println("You can't divide any number by 0");
                } else {
                    result = num1 / num2;
                    System.out.printf("Division is: %.2f%n", result);
                }
                break;
            case '%':
                result = num1 % num2;
                System.out.printf("Modulus is: %.2f%n", result);
                break;
            default:
                System.out.println("Invalid operator. Please enter +, -, *, /, or %");
        }
    }
}
