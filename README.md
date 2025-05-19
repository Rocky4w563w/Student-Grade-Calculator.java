# Student-Grade-Calculator.java
import java.util.Scanner;

public class StudentGradeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input: Ask user for number of subjects
        System.out.print("Enter the number of subjects: ");
        int numSubjects = scanner.nextInt();

        int[] marks = new int[numSubjects];
        int totalMarks = 0;

        // Input: Take marks for each subject
        for (int i = 0; i < numSubjects; i++) {
            System.out.print("Enter marks obtained in subject " + (i + 1) + " (out of 100): ");
            marks[i] = scanner.nextInt();

            // Validate input
            if (marks[i] < 0 || marks[i] > 100) {
                System.out.println("Invalid marks entered. Please enter a value between 0 and 100.");
                i--; // redo this subject input
                continue;
            }

            totalMarks += marks[i];
        }

        // Calculate Average Percentage
        double average = (double) totalMarks / numSubjects;

        // Grade Calculation
        String grade;
        if (average >= 90) {
            grade = "A+";
        } else if (average >= 80) {
            grade = "A";
        } else if (average >= 70) {
            grade = "B";
        } else if (average >= 60) {
            grade = "C";
        } else if (average >= 50) {
            grade = "D";
        } else {
            grade = "F";
        }

        // Display Results
        System.out.println("\n--- Result ---");
        System.out.println("Total Marks: " + totalMarks + " out of " + (numSubjects * 100));
        System.out.printf("Average Percentage: %.2f%%\n", average);
        System.out.println("Grade: " + grade);

        scanner.close();
    }
}

Output:- Enter the number of subjects: 3
Enter marks obtained in subject 1 (out of 100): 85
Enter marks obtained in subject 2 (out of 100): 78
Enter marks obtained in subject 3 (out of 100): 92

--- Result ---
Total Marks: 255 out of 300
Average Percentage: 85.00%
Grade: A
