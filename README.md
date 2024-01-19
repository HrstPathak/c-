// You are using C#
using System;
using System.Collections.Generic;
// using System.Object;
sealed class Logger{
    private static Logger instance;   //PRIVATE INSTANCE
    private static object lockObject=new object();
    private Logger(){}   //CONSTRUCTOR
    public static Logger Instance{
        get {
                lock(lockObject){
                        instance = new Logger();
                        return instance;
                }
            }
    }
    private List<string> logMessages;
    public void LogMessage(string str){
        logMessages.Add(str);
    }
    
    public void DisplayLogMessages(){
        Console.WriteLine("Log Message:");
        foreach(string s in logMessages){
            Console.WriteLine(s+" : ");
        }
    }
}

class Program{
    public static void Main(){
        int n=Convert.ToInt32(Console.ReadLine());
        Logger L=Logger.Instance;
        while(n!=0){
            string s=Console.ReadLine();
            L.LogMessage(s);
            
            n--;
        }
        
        L.DisplayLogMessages();
        
    }
}
