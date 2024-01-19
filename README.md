# StringStreamAge
1. Write a program using map() method to convert a list of Strings into uppercase. If the given List is: Stream names = Stream.of("aBc", "d", "ef");

import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class UppercaseConverter {
    public static void main(String[] args) {
        Stream<String> names = Stream.of("aBc", "d", "ef");

        List<String> uppercaseList = names
                .map(String::toUpperCase)
                .collect(Collectors.toList());

        System.out.println("Original List: " + Stream.of("aBc", "d", "ef").collect(Collectors.toList()));
        System.out.println("Uppercase List: " + uppercaseList);
    }
}

2. Write a program to check whether the Strings in the List are empty or not and print the list having non-empty strings. If the given List is: Liststrings = Arrays.asList("abc"," "bc", "efg", "abcd","", "jkl");

import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class NonEmptyStringsFilter {
    public static void main(String[] args) {
        List<String> strings = Arrays.asList("abc", " ", "bc", "efg", "abcd", "", "jkl");

        List<String> nonEmptyStrings = strings.stream()
                .filter(str -> str != null && !str.trim().isEmpty())
                .collect(Collectors.toList());

        System.out.println("Original List: " + strings);
        System.out.println("List with Non-Empty Strings: " + nonEmptyStrings);
    }
}

3. You are a teacher in school .In your class there are 10 students, you have decided to give special gifts to those students whose names start with "A" you are asked to separate those students with the help of a java program.
Requirement:
Use List interface to store the student name
Use a lambda expression and the Stream API to filter the students

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
import java.util.stream.Collectors;

public class StudentGifts {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Initialize a list to store student names
        List<String> studentNames = new ArrayList<>();

        // Input student names using Scanner
        for (int i = 0; i < 10; i++) {
            System.out.print("Enter student name: ");
            String name = scanner.nextLine();
            studentNames.add(name);
        }

        // Use Stream API and lambda expression to filter students whose names start with "A"
        List<String> studentsWithA = studentNames.stream()
                .filter(name -> name.startsWith("A"))
                .collect(Collectors.toList());

        // Display the students with names starting with "A"
        System.out.println("Students with names starting with 'A':");
        studentsWithA.forEach(System.out::println);

        // Close the scanner
        scanner.close();
    }
}

4.Rajesh has been given a task to create an app which takes the user's birthdate as input and calculates their age, you have to help him to build this app using the java.time.LocalDate class.
Input:
Enter your birthdate (yyyy-mm-dd): 1990-05-15
Output:
Your age is: 33 years, 4 months, and 13 days.

import java.time.LocalDate;
import java.time.Period;
import java.time.format.DateTimeFormatter;
import java.util.Scanner;

public class AgeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to enter their birthdate
        System.out.print("Enter your birthdate (yyyy-mm-dd): ");
        String birthdateInput = scanner.nextLine();

        // Parse the input into a LocalDate object
        LocalDate birthdate = LocalDate.parse(birthdateInput, DateTimeFormatter.ISO_DATE);

        // Calculate the age using Period.between
        Period age = Period.between(birthdate, LocalDate.now());

        // Display the age
        System.out.println("Your age is: " + age.getYears() + " years, " + age.getMonths() + " months, and " + age.getDays() + " days.");

        // Close the scanner
        scanner.close();
    }
}


