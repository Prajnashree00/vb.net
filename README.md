# vb.net
**c# program to print a binary triangle<br>**
using System;

namespace ex1<br>
{<br>
    class BinaryTriangle<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.Write("\nEnter the number of lines: ");<br>
            number = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i <= number; i++)<br>
            {<br>
                for (int space = number - i; space > 0; space--)<br>
                {<br>
                    Console.Write(" ");<br>
                }<br>
                for (int j = 0; j < i; j++)<br>
                {<br>
                    Console.Write(digit + " ");<br>
                    digit = (digit == 1) ? 0 : 1;<br>
                }<br>
                Console.Write("\n");<br>

            }
        }

    }
}<br>

![image](https://user-images.githubusercontent.com/97970956/154621989-89ff8d1e-9761-4c52-bd61-e3805011b181.png)


**2.c# program to chech whether the entered number is amicable or not**
using System;

namespace ex2<br>
{
    class Program<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n--------AMICABLE NUMBERS-----------\n"); Console.Write("\nEnter the first number: ");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the second number: ");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i < num1; i++)<br>
            
            {<br>
                if (num1 % i == 0)<br>
                {<br>
                    sum1 +=i;<br>
                }<br>
            }<br>
            for (int i = 1; i < num2; i++)<br>
            {<br>
                if (num2 % i == 0)<br>
                {<br>
                    sum2 += i;<br>
                }<br>
            }<br>
            if (sum1 == num2 && sum2 == num1)<br>
            {
                Console.WriteLine("\nThe numbers {0} and {1} are amiciable.", num1, num2);<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("\nThe numbers {0} and {1} are not amiciable.", num1, num2);<br>
            }<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97970956/154622803-b55bb416-9476-4980-abd9-a66457a69091.png)

3.. **C# Program to Illustrate Multilevel Inheritance with Virtual Methods  (displaying student details). **
using System;<br>

namespace studentusing System;

namespace student<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br><br>
            Console.WriteLine("\n_________________PERSONAL DETAILS________________");<br>
            Console.WriteLine("Name              :" + name);<b<br>r>
            Console.WriteLine("Age              :" + age);<br>
            Console.WriteLine("Gender              :" + gender);<br><br>
        }<br>
    }<br>
        class CourseDetails:PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br><br>
        public CourseDetails(string name,int age,string gender,int regNo,string course,int semester):base(name,age,gender)<br>
        {<br>
            this.regNo = regNo;<br>
            this.course = course;<br>
            this.semester = semester;<br>

        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n_____________________COURSEDETAILS____________");<br>
            Console.WriteLine("Register Number        :" + regNo);<br>
            Console.WriteLine("course        :" + course);<br>
            Console.WriteLine("Semester        :" +semester);<br>

        }<br>
    }<br>
    class MarksDetails:CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)<br>

        {
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
            private void Calculate()<br>
            {<br>
                average = total / 5;<br>
                if (flagFail == 1 || average < 40)<br>
                    grade = "fail";<br>
                else if (average >= 70)<br>
                    grade = " destinction";<br>
                else if (average >= 60)<br>
                    grade = "first class";<br>
                else if (average >= 50)<br>
                    grade = "second class";<br>
                else<br>
                    grade = "pass class";<br>
            }<br>
            public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("_______________Marks details_______________");<br>
            Console.WriteLine("marks in 5 subejects");<br>
            for(int i=0;i<5;i++)<br>
                Console.WriteLine(marks[i]+   "");<br>
                 Console.WriteLine();<br>
            Console.WriteLine("total         :"+total);<br>
            Console.WriteLine("Average         :" + average);<br>
            Console.WriteLine("garde         :" + grade);<br>
          }<br>

         }<br>
    class Multilevel<br>
    {<br>
        public static void Main(string[] args)<br>
        {<br>
            MarksDetails student1 = new MarksDetails("prajna", 21, "female", 20120000, "MSC", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            student1.Display();<br>
        }<br>
    }<br>
    }<br>
        

{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        <br>
        {
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br>
            Console.WriteLine("\n_________________PERSONAL DETAILS________________");<br>
            Console.WriteLine("Name              :" + name);<br>
            Console.WriteLine("Age              :" + age);<br>
            Console.WriteLine("Gender              :" + gender);<br>
        }<br>
    }<br>
        class CourseDetails:PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name,int age,string gender,int regNo,string course,int semester):base(name,age,gender)<br>
        {<br>
            this.regNo = regNo;<br>
            this.course = course;<br>
            this.semester = semester;<br>

        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n_____________________COURSEDETAILS____________");<br>
            Console.WriteLine("Register Number        :" + regNo);<br>
            Console.WriteLine("course        :" + course);<br>
            Console.WriteLine("Semester        :" +semester);<br>

        }<br>
    }<br>
    class MarksDetails:CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)<br>

        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br><br>
                if (marks[i] < 35)
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
            private void Calculate()<br>
            {<br>
                average = total / 5;<br>
                if (flagFail == 1 || average < 40)<br>
                    grade = "fail";<br>
                else if (average >= 70)<br><br>
                    grade = " destinction";<br>
                else if (average >= 60)<br>
                    grade = "first class";<br>
                else if (average >= 50)<br>
                    grade = "second class";<br>
                else<br>
                    grade = "pass class";<br>
            }<br>
            public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("_______________Marks details_______________");<br>
            Console.WriteLine("marks in 5 subejects");<br>
            for(int i=0;i<5;i++)<br>
                Console.WriteLine(marks[i]+   "");<br>
                 Console.WriteLine();<br>
            Console.WriteLine("total         :"+total);<br>
            Console.WriteLine("Average         :" + average);<br>
            Console.WriteLine("garde         :" + grade);<br>
          }<br>

         }<br>
    class Multilevel<br>
    {
        public static void Main(string[] args)<br>
        {<br>
            MarksDetails student1 = new MarksDetails("prajna", 21, "female", 20120000, "MSC", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            student1.Display();<br>
        }<br>
    }<br>
    }<br>
    
  
 ![image](https://user-images.githubusercontent.com/97970956/154626838-d13cba68-9258-485a-91bd-30594d577644.png)
 

  
  

**4.C# Program to Create a Gray Code**

using System;<br>

namespace ex3<br>
{<br>
    class GrayCode<br>
    {<br>

        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);
        }
        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\nEnter the decimal number: ");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\nBinary equivalent of {0}: {1}", InputNum, Convert.ToString(InputNum, 2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\nGray Code equivalent of {0}: {1}", InputNum, Convert.ToString(GrayNum, 2));<br>
        }<br>
    }<br>
}<br>


![image](https://user-images.githubusercontent.com/97970956/154626602-e254a9f8-1849-46c5-8052-fd73d85d46e5.png)


**5. C# program to calculate volume of 2 boxes and find the resultant volume  after addition of 2 boxes by implementing operator overloading. 
**
using System;<br>

namespace ex5<br><br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = height;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override String ToString()<br>
        {<br>
            return "box with width " + width + ", height " + height + " and length " + length;<br>
        }<br>
    }<br>
    class OperatorOverloading<br>
    {<br>
        public static void Main()<br>
        {<br>
            Box box1 = new Box(10, 20, 30);<br>
            Box box2 = new Box(25, 32, 15);<br>
            Console.WriteLine("Volume of {0} is: {1}", box1, box1.Volume); Console.WriteLine("Volume of {0} is: {1}", box2, box2.Volume);<br>

        Console.WriteLine("Volume after adding boxes: {0}", box1 + box2);<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/154628073-261beb47-899e-4c98-b6b2-160d33bcc12c.png)


using System;

**6.. C# Program to Implement Principles of Delegates (converting input string to  uppercase first, last and entire string). **

namespace upppercase<br>

{<br>
    class delegates<br>
    {<br>
        delegate string UppercaseDelegates(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0] = char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);<br>
            return new string(buffer);<br><br>
        }<br>
        static string UppercaseAll(string input)<br>
        {<br>
        return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input, UppercaseDelegates del)<br>
        {<br>
            Console.WriteLine("Input String:{0}", input);<br>
            Console.WriteLine("Output String:{0}", del(input));<br>

         }<br>
     static void Main()<br>
        {<br>
            WriteOutput("tom", new UppercaseDelegates(UppercaseFirst));<br>
            WriteOutput("tom", new UppercaseDelegates(UppercaseLast));<br>
            WriteOutput("tom", new UppercaseDelegates(UppercaseAll));<br>
            Console.ReadLine();<br>
        }<br>
    }<<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/154628942-8b16e0de-0521-43f4-9cc4-ea30e324bf9f.png)


**7. C# Program to Generate Register Number automatically for 100 Students  using Static Constructor.**
using System;

namespace Register<br>
{<br>
    class RegisterNum<br>

    {<br>
        int regno;<br>
        static int startNum;<br>
        static RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
            regno = ++startNum;<br>
        }<br>
        public static void Main(string[] args)<br>
        {<br><br>
            for(int i=0;i<=100;i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("student{0}:{1}",i+1, Student.regno);<br>
            }<br>
        }<br>

        
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/154631352-e4fe7f0e-2029-4d5b-bd36-cf72c0fa4493.png)
![image](https://user-images.githubusercontent.com/97970956/154631406-49a9a180-7faf-42b5-8fdf-669439d9b8fa.png)




**8.C# Program to Find the Frequency of the Word ʺisʺ in a given Sentence. **

using System;

namespace freequency<br>
{<br>
    class freequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count = 0;<br>
            string inputString;<br>
            Console.WriteLine("--------------FREQUENCY OF WORD IS-----------");<br>
            Console.Write("\n Enter the input string");<br>
            inputString = Console.ReadLine();<br>
            char[] seperator = { ',', ' ', '.', '!', '\n' };<br>
            string testString = inputString.ToLower();<br>
            string[] outcomes = testString.Split(seperator);<br>
            foreach(string s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\n Number of 'is' in' " + inputString + "'is: " + count);<br>

        }<br>
    }<br>
}<br>



![image](https://user-images.githubusercontent.com/97970956/154631143-13e10557-c570-4c14-ac47-77fd99cc20d1.png)


**9.C# program that benchmarks 2D, jagged array allocation. **
using System;
using System.Diagnostics;<br>


namespace benchmarks<br>
{<br>
    class BenchmarkAllocation<br>

    {<br>
        const int Max=10000;<br>
        static void Main(string[] args)<br>
        {<br>
            var Arr2D = new int[1000, 100];<br>
            var ArrJagged = new int[100][];<br>
            for(int i=0;i<100;i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>

            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i <Max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>

                    for (int k = 0; k < 100; k++)<br>
                    
                    {<br>
                        Arr2D[j, k] = k;<br>
                        
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>
                var StopwatchJagged = Stopwatch.StartNew();<br>
            for (int i = 0; i < Max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>  
                {<br>
                for (int k = 0; k < 100; k++)<br>
                
                    {<br>
                        ArrJagged[j][k]=k;<br>
                    }<br>
                }<br>
            }<br>
            StopwatchJagged.Stop();<br>
            Console.WriteLine("\n Time taken for allocation incase of 2D array:");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds+"milliseconds");<br>
            Console.WriteLine("the time taken for allocation in case of Jagged array");<br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97970956/154632699-40ee54cf-6183-4f4e-ba8c-e1bd07e5270b.png)

**10.C# Program to Find the Sum of the Values on Diagonal of the Matrix. using System; **
using System;

namespace ex10
{
    class SumOfDiagonals<br>
    {
        static void Main(string[] args)<br>
        {<br>
            int MaxRow, MaxCol, Sum = 0;<br>
            int[,] Matrix;<br><br>
            Console.WriteLine("\n---------- SUM OF DIAGONAL OF A MATRIX ----------\n"); Console.Write("\nEnter the number of rows: ");<br>
            MaxRow = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the number of columns: ");<br>
            MaxCol = Convert.ToInt32(Console.ReadLine());<br>
            if (MaxRow != MaxCol)<br>
            {<br>
                Console.WriteLine("\nThe Dimensions entered are not of Square Matrix."); Console.WriteLine("\nExiting the Program..");<br>
                return;<br><br>
            }
            Matrix = new int[MaxRow, MaxCol];<br><br>
            for (int i = 0; i < MaxRow; i++)<br>
            {
                for (int j = 0; j < MaxCol; j++)<br>
                {
                    Console.Write("\nEnter the ({0},{1})th element of the matrix: ", (i + 1), (j + 1)); Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
                }<br>
            }<br>
            Console.WriteLine("\nThe entered Matrix is: ");<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write(" " + Matrix[i, j]);<br>
                    if (i == j)<br>
                    {<br>
                    Sum += Matrix[i, j];<br>
                    }<br>
                }<br>
                Console.WriteLine();<br>
            }
            Console.WriteLine("\nThe Sum of Diagonal is " + Sum);
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/154633626-af924c82-b262-4da9-877b-cca2aafb7735.png)


**11.C# Program to Create a File, Check the Existence of a File and Read the  Contents of the File.**
using System;
using System.IO;<br>


namespace create<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string filename;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n ----------------MENU------------------");<br>
                Console.WriteLine("\n 1.create a file");<br>
                Console.WriteLine("\n 2.existenece of the file");<br>
                Console.WriteLine("\n 3.Read the contents of the file ");<br>
                Console.WriteLine("\n 4.Exit");<br>
                Console.Write("\n enter your choice :");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\n Enter the name to create");<br>
                        filename = Console.ReadLine();<br>
                        Console.WriteLine("Write the contents to the file:\n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(filename))<br>
                        {
                            fileStr.WriteLine(r);<br>
                        }
                        Console.WriteLine("File is created.....");<br>
                        break;<br>
                    case 2:<br>
                        Console.Write("\n Enter the name to create");<br>
                        filename = Console.ReadLine();<br>
                        if (File.Exists(filename))<br>
                        {
                           <br> Console.WriteLine("file exists");<br>
                        }<br>
                        else
                        {
                            Console.WriteLine("file does not exists in the current directory ");<br>
                        }
                        break;<br>
                    case 3:<br>
                        Console.Write("\n Enter the file  name to read the contents:\n");<br>
                        filename = Console.ReadLine();<br>
                        if (File.Exists(filename))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(filename))<br>
                            {<br>
                                string s = " ";<br>
                                Console.WriteLine("here is thye content of the file:");<br>
                                while ((s = sr.ReadLine()) != null)<br>
                                {<br>
                                    Console.WriteLine(s);<br>


                                }<br>
                                Console.WriteLine(" ");<br>
                            }
                        }
                        else<br>
                        {
                            Console.WriteLine("File does not exists");<br>
                        }
                        break;<br>
                    case 4:<br>
                        Console.WriteLine(" \n exiting");<br>
                        return;<br>
                    default:<br>
                        Console.WriteLine("\n Invalid choice");<br>
                        break;<br>
                }<br>
            }
        }
    }  
 }
![image](https://user-images.githubusercontent.com/97970956/154636277-f73dfc6a-eef1-4c6f-aeed-29b1f9479a35.png)

   ![image](https://user-images.githubusercontent.com/97970956/154636121-1a69130c-22cc-43e0-82ff-2c7796243feb.png)

![image](https://user-images.githubusercontent.com/97970956/154636191-7d1e85da-545d-4e15-8ec1-6ff37b7e567b.png)


**12.C# Program to Perform File Comparison
using System;
using System.IO;


namespace comparision
{
    class FileRead
    {
        public static void Main()
        {
            string file1;
            string file2;
            Console.Write("enter the first fiole path");
            file1 = Console.ReadLine();
            Console.Write("enther the second file path");
            file2 = Console.ReadLine();
            if(!File.Exists(file1))
            {
                Console.WriteLine("First file does not exist");

            }
           else  if (!File.Exists(file2))
            {
                Console.WriteLine("second file does not exist");

            }
              else if (File.ReadAllText(file1)==File.ReadAllText(file2))
            {
                Console.WriteLine("Both files contains the same content");

            }
            else 
            {
                Console.WriteLine("contents of files are not same");

            }
        }
    }
}

        
![image](https://user-images.githubusercontent.com/97970956/154637057-788bdf1d-cfc8-4459-b8b8-3d62147728c1.png)

![image](https://user-images.githubusercontent.com/97970956/154637102-bf19bcb1-9925-408f-90d6-31159262c3c8.png)

![image](https://user-images.githubusercontent.com/97970956/154637167-0e165ecd-94cd-4912-b442-da41610bc49f.png)
![image](https://user-images.githubusercontent.com/97970956/154637496-766975d2-2ba8-4197-a47d-e95e3be54b70.png)
![image](https://user-images.githubusercontent.com/97970956/154637547-5d1deafb-ed4c-48ff-b158-9543d0f275c5.png)


**13.. C# Program to Implement IComparable Interface

using System;
namespace ex13
{
    class Fraction : IComparable
    {
        int z,n;
        public Fraction(int z, int n)
        {
            this.z = z;
            this.n = n;
        }
        public static Fraction operator +(Fraction a, Fraction b)
        {
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);
        }
        public static Fraction operator *(Fraction a, Fraction b)
        {
            return new Fraction(a.z * b.z, a.n * b.n);
        }
        public int CompareTo(object obj)
        {
            Fraction f = (Fraction)obj;
            if ((float) z / n < (float)f.z / f.n)
                    return -1;
            else if ((float)z / n > (float)f.z / f.n)
                return 1;
            else
                return 0;
        }

        public override string ToString()
        {
            return z + "/" + n;
        }
    }


    class ICompInterface
    {
        public static void Main()
        {
            Fraction[] a =
            {
                new Fraction(5,2),
                new Fraction(29,6),
                new Fraction(4,5),
                new Fraction(10,8),
                new Fraction(34,7),

            };
            Array.Sort(a);
            Console.WriteLine("Implementing the IComparabable interface in " + "Displaying Fraction:");
            foreach (Fraction f in a)
            {
                Console.WriteLine(f + "");
            }
            Console.WriteLine();
            Console.ReadLine();
        }
        
    }
}

![image](https://user-images.githubusercontent.com/97970956/154637892-c2511ee7-20b1-455d-ba6d-4ed7a2b10cf4.png)


**14.create a thred pool**
using System;
using System.Threading;

namespace Pool
{
    class ThreadPoolProg
    {
        public void ThreadFun1(object obj)
        {
            int loop = 0;
            for (loop = 0; loop <= 4; loop++)
            {
                Console.WriteLine("Thread 1 is executing");
            }

        }
        public void ThreadFun2(Object Obj)
        {
            int loop = 0;
            for (loop = 0; loop <= 4; loop++)
            {
                Console.WriteLine("Thread 1 is executing");

            }
        }
        public static  void Main()
        {
            ThreadPoolProg TP = new ThreadPoolProg();
            for (int i = 0; i <= 2; i++)
            {
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));
            }
            Console.ReadKey();
        }
    }
}

![image](https://user-images.githubusercontent.com/97970956/155658420-0b045807-fe6f-4384-84db-89f0f06e4c62.png)

**15.c# program to demostrate error handling using try catch and finally block**
using System;

namespace ex15
{
    class ExceptionHandling
    {
        static void Main(string[] args)
        {
            Age a = new Age();
            try
            {
                a.displayAge();
            }
            catch (AgeIsNegativeException e)
            {
                Console.WriteLine("AgeIsNegativeExpection:{0}", e.Message);

            }
            finally
            {
                Console.WriteLine("Exception of finally block is done");

            }
        }
    }
}
public class AgeIsNegativeException : Exception
{
    public AgeIsNegativeException(string Message) : base(Message)
    {

    }

}
public class Age
{
    int age = -5;
    public void displayAge()
    {
        if(age<0)
        {
            throw (new AgeIsNegativeException("Age cacanot be negative"));
        }
        else
        {
            Console.WriteLine("Age is:{0}", age);
        }
    }
}

![image](https://user-images.githubusercontent.com/97970956/155658714-f3552135-c0e6-48ec-a3c6-e694340ee510.png)


**16.c# program to generate the fibanaci series**
using System;

public class FibonacciExample
{
    public static void Main(string[] args)
    {
        int n1 = 0, n2 = 1, n3, i, number;
        Console.Write("Enter the number of elements: ");
        number = int.Parse(Console.ReadLine());
        Console.Write(n1 + " " + n2 + " "); //printing 0 and 1    
        for (i = 2; i < number; ++i) //loop starts from 2 because 0 and 1 are already printed    
        {
            n3 = n1 + n2;
            Console.Write(n3 + " ");
            n1 = n2;
            n2 = n3;
        }
    }
}

![image](https://user-images.githubusercontent.com/97970956/155659389-165cc0a5-c16f-4f11-ac9f-6974cd65985d.png)

**17.c# program to check the prime number is or not**
using System;
public class PrimeNumberExample
{
    public static void Main(string[] args)
    {
        int n, i, m = 0, flag = 0;
        Console.Write("Enter the Number to check Prime: ");
        n = int.Parse(Console.ReadLine());
        m = n / 2;
        for (i = 2; i <= m; i++)
        {
            if (n % i == 0)
            {
                Console.Write("Number is not Prime.");
                flag = 1;
                break;
            }
        }
        if (flag == 0)
            Console.Write("Number is Prime.");
    }
}
![image](https://user-images.githubusercontent.com/97970956/155659646-20e8dbcb-58f7-4545-8c1d-a05324309071.png)

**18.c# program to check whether palindrome or not**
using System;
public class PalindromeExample
{
    public static void Main(string[] args)
    {
        int n, r, sum = 0, temp;
        Console.Write("Enter the Number: ");
        n = int.Parse(Console.ReadLine());
        temp = n;
        while (n > 0)
        {
            r = n % 10;
            sum = (sum * 10) + r;
            n = n / 10;
        }
        if (temp == sum)
            Console.Write("Number is Palindrome.");
        else
            Console.Write("Number is not Palindrome");
    }
}

![image](https://user-images.githubusercontent.com/97970956/155661216-9090ce36-7519-42a5-acbe-cfeb02960950.png)

**19.write thye c# program to find the factorial of the number**
using System;
public class FactorialExample
{
    public static void Main(string[] args)
    {
        int i, fact = 1, number;
        Console.Write("Enter any Number: ");
        number = int.Parse(Console.ReadLine());
        for (i = 1; i <= number; i++)
        {
            fact = fact * i;
        }
        Console.Write("Factorial of " + number + " is: " + fact);
    }
}

![image](https://user-images.githubusercontent.com/97970956/155662482-9d25d469-717f-4d2b-9902-6da889925339.png)
**20.write a program to find the sum of digits**<br>
using System;  <br>
  public class SumExample <br> 
   {  <br>
     public static void Main(string[] args)  <br>
      {  <br>
       int  n,sum=0,m;  <br>       
       Console.Write("Enter a number: ");  <br>    
       n= int.Parse(Console.ReadLine()); <br>    
       while(n>0) <br>     
       { <br>     
        m=n%10;  <br>    
        sum=sum+m;<br>      
        n=n/10; <br>     
       }<br>      
       Console.Write("Sum is= "+sum);  <br>     
     }<br>
  }<br>
  
  ![image](https://user-images.githubusercontent.com/97970956/155663758-c0b65fc3-d94c-4fe6-beef-10a619359590.png)
  **21.reverse the number**<br>
  using System;<br>
public class ReverseExample<br>

{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, reverse = 0, rem;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n != 0)<br>
        {<br>
            rem = n % 10;<br>
            reverse = reverse * 10 + rem;<br>
            n /= 10;<br>
        }<br>
        Console.Write("Reversed Number: " + reverse);<br>
   <br> }<br>
}

![image](https://user-images.githubusercontent.com/97970956/155664224-a78ec3ab-f0d3-4421-a5eb-f6fd08866898.png)

**22.swap a number**<br>
using System;  <br>
  public class SwapExample  <br>
   {  <br>
     public static void Main(string[] args)  <br>
      {  <br>
       int  a=5, b=10; <br>           
       Console.WriteLine("Before swap a= "+a+" b= "+b);<br>    
       a=a*b; //a=50 (5*10)<br>      
       b=a/b; //b=5 (50/10)  <br>    
       a=a/b; //a=10 (50/5)  <br>  
       Console.Write("After swap a= "+a+" b= "+b); <br>      
     } <br> 
  }   <br>
  
  ![image](https://user-images.githubusercontent.com/97970956/155664725-9cea9143-7f34-43e3-af24-77d1664b33e7.png)





