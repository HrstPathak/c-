// You are using C#
using System;
using System.IO;

class tester{
    string filename="sample.txt";
    public void WriteToFile(string str){
            if(!File.Exists(filename)){
                File.WriteAllText(filename,string.Empty);
            }
           StreamWriter sw=new StreamWriter(filename);
           sw.WriteLine(str);
           sw.Close();
           Console.WriteLine("Content successfully written to the file.");
           Console.WriteLine("");
    }
    public void ReadFromFile(){
            StreamReader sr=new StreamReader(filename);
            string text=sr.ReadLine();
            Console.WriteLine($"File contents:{text}");
            Console.WriteLine("");
        
    }
    
}


class Program{
    public static void Main(){
        try{
        int ch=0;
        tester t = new tester();
        while(ch!=3){
            ch=Convert.ToInt32(Console.ReadLine());
            switch(ch){
                case 1:
                    t.ReadFromFile();
                    break;
                case 2:
                string str=Console.ReadLine();
                    t.WriteToFile(str);
                    break;
                case 3:
                    Console.WriteLine("Exiting the program. Goodbye!");
                    Console.WriteLine("");
                    break;
                default:
                    Console.WriteLine("Invalid option. Please select a valid option.");
                    Console.WriteLine("");
                    break;
            }
        }}catch(Exception ex){
            Console.WriteLine(ex.Message);
        }
    }
}
