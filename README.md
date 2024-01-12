using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Dictionary<string, List<string>> studentSubjects = new Dictionary<string, List<string>>();

        Console.WriteLine("Enter the names of students and their subjects.");
        Console.WriteLine("Use 'Quit' to stop adding students.");

        while (true)
        {
            Console.Write("Enter the name of a student: ");
            string studentName = Console.ReadLine().Trim();

            // Check if the user wants to quit
            if (string.Equals(studentName, "quit", StringComparison.OrdinalIgnoreCase))
                break;

            Console.WriteLine($"Enter the subjects for {studentName}, separated by commas only:");
            string subjectsInput = Console.ReadLine();

            // Split subjects by commas and create a List<string>
            List<string> subjects = new List<string>(subjectsInput.Split(','));

            // Add the student and their subjects to the dictionary
            studentSubjects[studentName] = subjects;
        }

        Console.WriteLine("\nEnter the name of the student to search for their subjects.");

        while (true)
        {
            Console.Write("Enter the student's name (type 'quit' to stop searching): ");
            string searchName = Console.ReadLine().Trim();

            // Check if the user wants to quit searching
            if (string.Equals(searchName, "quit", StringComparison.OrdinalIgnoreCase))
                break;

            // Search for the student and display their subjects
            if (studentSubjects.TryGetValue(searchName, out List<string> subjects))
            {
                Console.WriteLine($"Subjects for {searchName}: {string.Join(", ", subjects)}");
            }
            else
            {
                Console.WriteLine($"Student '{searchName}' not found.");
            }
        }

        Console.WriteLine("Program terminated.");
    }
}
