using System; using System. 10;

using System.Collections.Generic;

class tester

public int[] ReadNumbersFromFile(string filename)

if(file.Exists(filename))

StreamReader sr new Streamileader (filename);

string line = null;

line sr.teadToEn eadToEnd();

string[] word line.Split();

int[] numbers new int[word.Length]; for(int i=0;i<word.Length; i++)

if(int.TryParse(word[i], out internusber))

else

numbers[i] = number;

Console.WriteLine($"Invalid number found: (word[i])");

numbers[i];

return numbers;

else

return new int[0];

public double CalculateSum(int[] arr)

double sum=0

for(int i=0;i<arr.Length;i++)

sunt arr[i];

return sum;

public double CalculateAverage(int[] arr)

double Sum CalculataSum(arr);

return Sum/arr.Length;

public class Program

public static void Main()

string filename data.txt"; I Streamriter su new StreamWriter(filename); string txt Console.ReadLine(); sw.Close();

sw.WriteLine(txt);

testort new tester();

int[] arrt.Readiumbers FronFile(filename);

Console.WriteLine($"Sum: (t.CalculateSum(arr)}\nAverage: (t.CalculateAverage(arr))");
