#include <stdio.h>

double sum_of_series(int n) {
    double sum = 0.0;
    long long fact = 1; // Use long long to avoid overflow for larger factorials

    for (int i = 1; i <= n; i++) {
        // Update factorial iteratively (fact = 1! -> 2! -> ... -> i!)
        fact *= i;
        // Add the current term to the sum. Use 1.0 / fact to force floating-point division.
        sum += 1.0 / fact;
    }

    return sum;
}

int main() {
    int n;

    // Prompt user for input
    printf("Enter the number of terms (n): ");
    
    // Read the input from the user
    if (scanf("%d", &n) != 1 || n <= 0) {
        printf("Invalid input. Please enter a positive integer.\n");
        return 1;
    }

    // Calculate the sum
    double total_sum = sum_of_series(n);

    // Print the result
    printf("The sum of the series 1/1! + ... + 1/%d! is: %lf\n", n, total_sum);

    return 0;
}
# turbo
