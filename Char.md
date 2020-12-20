using System;





namespace read_char_by_char

{

  class Program

  {

​    static void Main(string[] args)

​    {

​      Console.WriteLine("Morning");



​      string password = "", Cpassword = "",ID = "", Age = "", Profit = "";





​      Console.Write("Password: \n");

​      RdPassword(password);

​      Console.WriteLine("Confirm\n");

​      RdPassword2(Cpassword);

​      



​      if (password == Cpassword)

​      {

​        Console.WriteLine("\nThe Keys aren equals");

​      }

​      else

​      {

​        System.Console.WriteLine("The Keys aren't equals");

​      }



​      Console.Write("ID: ");

​      ReadID(ID);

​      Console.WriteLine();



​      Console.Write("Age ");

​      ReadAge(Age);

​      Console.WriteLine();



​      Console.Write("Ahorros: ");

​      ReadMoney(Profit);

​      Console.WriteLine();

​    }



​    static string RdPassword(string pstring)

​    {

​      Console.Write(pstring);



​      while (true)

​      {

​        string password = "";

​        ConsoleKey key;



​        do

​        {

​          var keyInfo = Console.ReadKey(intercept: true);

​          key = keyInfo.Key;



​          if (key == ConsoleKey.Backspace && password.Length > 0)

​          {

​            Console.Write("\b \b");

​            password = password.Remove(password.Length - 1);

​          }

​          else if (!char.IsControl(keyInfo.KeyChar))

​          {

​            Console.Write("*");

​            password += keyInfo.KeyChar;

​          }

​          

​          } while (key != ConsoleKey.Enter);

​        



​        if (password == "")

​          continue;





​        return password;

​        

​      }

​      

​    }

​    static string RdPassword2(string pstring)

​    {

​      Console.Write(pstring);



​      while (true)

​      {

​        string password = "";

​        ConsoleKey key;



​        do

​        {

​          var keyInfo = Console.ReadKey(intercept: true);

​          key = keyInfo.Key;



​          if (key == ConsoleKey.Backspace && password.Length > 0)

​          {

​            Console.Write("\b \b");

​            password = password.Remove(password.Length - 1);

​          }

​          else if (!char.IsControl(keyInfo.KeyChar))

​          {

​            Console.Write("*");

​            password += keyInfo.KeyChar;

​          }

​          

​          } while (key != ConsoleKey.Enter);

​        



​        if (password == "")

​          continue;





​        return password;

​        

​      }

​      

​    }



​    static string ReadID(string text)

​    {

​      Console.Write(text);

​      while (true)

​      {

​        string data = "";

​        ConsoleKey key;



​        do

​        {

​          var keyInfo = Console.ReadKey(intercept: true);

​          key = keyInfo.Key;



​          int value;

​          bool success = int.TryParse(keyInfo.KeyChar.ToString(), out value);



​          if (key == ConsoleKey.Backspace && data.Length > 0)

​          {

​            Console.Write("\b \b");

​            data = data.Remove(data.Length - 1);

​          }

​          else if (!char.IsControl(keyInfo.KeyChar) && success)

​          {

​            Console.Write(keyInfo.KeyChar);

​            data += keyInfo.KeyChar;

​          }



​        } while (key != ConsoleKey.Enter);



​        if (data == "")

​          continue;



​        return data;

​      }

​    }



​    static int ReadAge(string text)

​    {

​      Console.Write(text);

​      while (true)

​      {

​        string data = "";

​        ConsoleKey key;



​        do

​        {

​          var keyInfo = Console.ReadKey(intercept: true);

​          key = keyInfo.Key;



​          int value;

​          bool success = int.TryParse(keyInfo.KeyChar.ToString(), out value);



​          if (key == ConsoleKey.Backspace && data.Length > 0)

​          {

​            Console.Write("\b \b");

​            data = data.Remove(data.Length - 1);

​          }

​          else if (!char.IsControl(keyInfo.KeyChar) && success)

​          {

​            Console.Write(keyInfo.KeyChar);

​            data += keyInfo.KeyChar;

​          }

​        } while (key != ConsoleKey.Enter);



​        if (data == "")

​          continue;



​        return int.Parse(data);

​      }

​    }



​    static decimal ReadMoney(string text)

​    {

​      Console.Write(text);

​      while (true)

​      {

​        string data = "";

​        ConsoleKey key;

​        int c = 0;



​        do

​        {

​          var keyInfo = Console.ReadKey(intercept: true);

​          key = keyInfo.Key;



​          int value;

​          bool success = int.TryParse(keyInfo.KeyChar.ToString(), out value) || (keyInfo.KeyChar == '.' && c == 0);



​          if (keyInfo.KeyChar == '.')

​            c = 1;

​          else

​            c = 0;



​          if (key == ConsoleKey.Backspace && data.Length > 0)

​          {

​            Console.Write("\b \b");

​            data = data.Remove(data.Length - 1);

​          }

​          else if (!char.IsControl(keyInfo.KeyChar) && success)

​          {

​            Console.Write(keyInfo.KeyChar);

​            data += keyInfo.KeyChar;

​          }

​        } while (key != ConsoleKey.Enter);



​        if (data == "")

​          continue;



​        return decimal.Parse(data);

​      }

​    }





  }

}