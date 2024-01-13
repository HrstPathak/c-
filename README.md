using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Dictionary<string, List<string>> studentSubjects = new Dictionary<string, List<string>>();

        while (true)
        {
            Console.WriteLine("Enter the name of a student:");
            string studentName = Console.ReadLine();

            if (studentName.Equals("quit", StringComparison.OrdinalIgnoreCase))
                break;

            Console.WriteLine("Enter the subjects for the student, separated by commas only:");
            string subjectsInput = Console.ReadLine();
            List<string> subjects = new List<string>(subjectsInput.Split(','));

            studentSubjects[studentName] = subjects;
        }

        Console.WriteLine("Enter the name of the student to search for their subjects:");
        string searchName = Console.ReadLine();

        if (studentSubjects.TryGetValue(searchName, out List<string> foundSubjects))
        {
            Console.WriteLine("Subjects:");
            foreach (var subject in foundSubjects)
            {
                Console.WriteLine(subject);
            }
        }
        else
        {
            Console.WriteLine("Student not found.");
        }
    }
}
