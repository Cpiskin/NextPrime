import java.util.Scanner;

public class NextPrime {

    // Method to check if a number is prime
    public static boolean isPrime(int num) {
        if (num < 2) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }

    // Method to find the next prime number greater than n
    public static int nextPrime(int n) {
        while (true) {
            n++;
            if (isPrime(n)) {
                return n;
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter five integers (0 < n ≤ 500,000,000):");

        for (int i = 0; i < 5; i++) {
            int num = scanner.nextInt();
            if (num > 0 && num <= 500000000) {
                int result = nextPrime(num);
                System.out.println("Next prime greater than " + num + " is: " + result);
            } else {
                System.out.println("Input out of range. Please enter a valid integer.");
            }
        }

        scanner.close();
    }
}
