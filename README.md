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
            }<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/154621989-89ff8d1e-9761-4c52-bd61-e3805011b181.png)
**2.c# program to chech whether the entered number is amicable or not**<br>
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

3.. **C# Program to Illustrate Multilevel Inheritance with Virtual Methods  (displaying student details). **<br>
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

**4.C# Program to Create a Gray Code**<br>
using System;<br>
namespace ex3<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
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
**<br>
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

**6.. C# Program to Implement Principles of Delegates (converting input string to  uppercase first, last and entire string). **<br>
using System;<br>
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

**7. C# Program to Generate Register Number automatically for 100 Students  using Static Constructor.**<br>
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

**8.C# Program to Find the Frequency of the Word ʺisʺ in a given Sentence. **<br>
using System;<br>
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


**9.C# program that benchmarks 2D, jagged array allocation. **<br>
using System;<br>
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

**10.C# Program to Find the Sum of the Values on Diagonal of the Matrix. using System; **<br>
using System;<br>
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


**11.C# Program to Create a File, Check the Existence of a File and Read the  Contents of the File.**<br>
using System;<br>
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

**12.C# Program to Perform File Comparison**<br>
using System;<br>
using System.IO;<br>
namespace comparision<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string file1;<br>
            string file2;<br>
            Console.Write("enter the first fiole path");<br>
            file1 = Console.ReadLine();<br>
            Console.Write("enther the second file path");<br>
            file2 = Console.ReadLine();<br>
            if(!File.Exists(file1))<br>
            {<br>
                Console.WriteLine("First file does not exist");<br>
            }<br>
           else  if (!File.Exists(file2))<br>
            {<br>
                Console.WriteLine("second file does not exist");<br>
            }<br>
              else if (File.ReadAllText(file1)==File.ReadAllText(file2))<br>
            {<br>
                Console.WriteLine("Both files contains the same content");<br>
            }<br>
            else <br>
            {<br>
                Console.WriteLine("contents of files are not same");<br>
            }<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97970956/154637057-788bdf1d-cfc8-4459-b8b8-3d62147728c1.png)
![image](https://user-images.githubusercontent.com/97970956/154637102-bf19bcb1-9925-408f-90d6-31159262c3c8.png)
![image](https://user-images.githubusercontent.com/97970956/154637167-0e165ecd-94cd-4912-b442-da41610bc49f.png)
![image](https://user-images.githubusercontent.com/97970956/154637496-766975d2-2ba8-4197-a47d-e95e3be54b70.png)
![image](https://user-images.githubusercontent.com/97970956/154637547-5d1deafb-ed4c-48ff-b158-9543d0f275c5.png)

**13.. C# Program to Implement IComparable Interface<br>
using System;<br>
namespace ex13<br>
{<br>
    class Fraction : IComparable<br>
    {<br>
        int z,n;<br>
        public Fraction(int z, int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator *(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float) z / n < (float)f.z / f.n)<br>
                    return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
            public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br>
    {<br>
        public static void Main()<br>
        {<br>
            Fraction[] a =<br>
            {<br>
                new Fraction(5,2),<br>
                new Fraction(29,6),<br>
                new Fraction(4,5),<br>
                new Fraction(10,8),<br>
                new Fraction(34,7),<br>
                };<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the IComparabable interface in " + "Displaying Fraction:");<br>
            foreach (Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + "");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();
        }<br>     
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97970956/154637892-c2511ee7-20b1-455d-ba6d-4ed7a2b10cf4.png)

**14.create a thred pool**<br>
using System;<br>
using System.Threading;<br>
namespace Pool<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread 1 is executing");<br>
            }<br>
         }<br>
        public void ThreadFun2(Object Obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread 1 is executing");<br>
            }<br>
        }<br>
        public static  void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for (int i = 0; i <= 2; i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/155658420-0b045807-fe6f-4384-84db-89f0f06e4c62.png)

**15.c# program to demostrate error handling using try catch and finally block**<br>
using System;<br>
namespace ex15<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeExpection:{0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Exception of finally block is done");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string Message) : base(Message)<br>
    {<br>
    }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if(age<0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cacanot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is:{0}", age);<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/155658714-f3552135-c0e6-48ec-a3c6-e694340ee510.png)

**16.c# program to generate the fibanaci series**<br>
using System;<br>
public class FibonacciExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n1 = 0, n2 = 1, n3, i, number;<br>
        Console.Write("Enter the number of elements: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        Console.Write(n1 + " " + n2 + " "); //printing 0 and 1  <br>  
        for (i = 2; i < number; ++i) //loop starts from 2 because 0 and 1 are already printed <br>   
        {<br>
            n3 = n1 + n2;<br>
            Console.Write(n3 + " ");<br>
            n1 = n2;<br>
            n2 = n3;<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/155659389-165cc0a5-c16f-4f11-ac9f-6974cd65985d.png)

**17.c# program to check the prime number is or not**<br>
using System;<br>
public class PrimeNumberExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i, m = 0, flag = 0;<br>
        Console.Write("Enter the Number to check Prime: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        m = n / 2;<br>
        for (i = 2; i <= m; i++)<br>
        {<br>
            if (n % i == 0)<br>
            {<br>
                Console.Write("Number is not Prime.");<br>
                flag = 1;<br>
                break;<br>
            }<br>
        }<br>
        if (flag == 0)<br>
            Console.Write("Number is Prime.");<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97970956/155659646-20e8dbcb-58f7-4545-8c1d-a05324309071.png)

**18.c# program to check whether palindrome or not**<br>
using System;<br>
public class PalindromeExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = (sum * 10) + r;<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Number is Palindrome.");<br>
        else<br>
            Console.Write("Number is not Palindrome");<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/155661216-9090ce36-7519-42a5-acbe-cfeb02960950.png)

**19.write thye c# program to find the factorial of the number**<br>
using System;<br>
public class FactorialExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int i, fact = 1, number;<br>
        Console.Write("Enter any Number: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= number; i++)<br>
        {<br>
            fact = fact * i;<br>
        }<br>
        Console.Write("Factorial of " + number + " is: " + fact);<br>
    }<br>
}<br>

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

**Exapmle**
**23.write a c# program to print the number triangle**<br>
using System;<br>

namespace eg31<br>
{<br>
    public class printExample<br>
    {<br>
        public static void Main(string[] args)<br>
        {<br>
            int i, j, k, l, n;<br>
            Console.Write("Enther the range");<br>
            n = int.Parse(Console.ReadLine());<br>
            for (i = 1; i <= n; i++)<br>
            {<br>
                for (j = 1; j <= n - i; j++)<br>
                {<br>
                    Console.Write(" ");<br>
                }<br>
                for (k = 1; k <= i; k++)<br>
                {<br>
                    Console.Write(k);<br>
                }<br>
                for (l = i-1; l >= 1; l--)<br>
                {<br>
                    Console.Write(l);<br><br>
                }<br>
                Console.Write("\n");<br>
            }<br>
        }<br>
    }<br>
}<br>

**Output**
![image](https://user-images.githubusercontent.com/97970956/156508841-3bb08fcb-12a2-4112-a1f9-121a2ae834ce.png)


**24.write a program to find decimal to binary **<br>
using System;<br>
public class ConversionExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br><br>
        int n, i;<br>
        int[] a = new int[10];<br>
        Console.Write("Enter the number to convert: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        for (i = 0; n > 0; i++)<br>
        {<br>
            a[i] = n % 2;<br>
            n = n / 2;<br>
        }<br>
        Console.Write("Binary of the given number= ");<br>
        for (i = i - 1; i >= 0; i--)<br>
        {<br><br>
            Console.Write(a[i]);
        }<br>
    }<br>
}<br><br>
![image](https://user-images.githubusercontent.com/97970956/156509186-4e77d469-3928-49bb-9646-fb050cac6c00.png)

**25 write a c# program to number in a character**<br>
using System;<br>
public class ConversionExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, sum = 0, r;<br>
        Console.Write("Enter the Number= ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br><br>
            sum = sum * 10 + r;
            n = n / 10;<br>
        }<br>
        n = sum;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            switch (r)<br>
            {<br>
                case 1:<br>
                    Console.Write("one ");<br>
                    break;<br>
                case 2:<br><br>
                    Console.Write("two ");<br>
                    break;<br><br>
                case 3:<br>
                    Console.Write("three ");<br>
                    break;<br>
                case 4:<br><br>
                    Console.Write("four ");<br>
                    break;<br>
                case 5:<br>
                    Console.Write("five ");<br>
                    break;<br>
                case 6:<br>
                    Console.Write("six ");<br>
                    break;<br>
                case 7:<br>
                    Console.Write("seven ");<br>
                    break;<br>
                case 8:<br>
                    Console.Write("eight ");<br>
                    break;<br>
                case 9:<br>
                    Console.Write("nine ");<br>
                    break;<br>
                case 0:<br>
                    Console.Write("zero ");
                    break;<br>
                default:<br>
                    Console.Write("tttt ");<br>
                    break;<br>
            }//end of switch   <br>   
            n = n / 10;<br>
        }//end of while loop    <br>   
    }<br>
}<br>

**output**
![image](https://user-images.githubusercontent.com/97970956/156509435-038f821e-f6c7-46e1-8d90-0a8a28db6204.png)

**26.Write a c# program to alphabet Triangle**<br>
using System;<br>
public class PrintExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        char ch = 'A';<br>
        int i, j, k, m;<br>
        for (i = 1; i <= 5; i++)<br>
        {<br>
            for (j = 5; j >= i; j--)<br>
                Console.Write(" ");<br>
            for (k = 1; k <= i; k++)<br>
                Console.Write(ch++);<br>
            ch--;<br>
            for (m = 1; m < i; m++)<br>
                Console.Write(--ch);<br>
            Console.Write("\n");<br>
            ch = 'A';<br>
        }<br>
    }<br>
}<br>

**Output**
![image](https://user-images.githubusercontent.com/97970956/156509743-e582aff4-aa52-4398-97e9-d744ae8a3172.png)

**27.write a program to a fibonaci traiangle**<br>
using System;<br>
public class PrintExample<br>
{<br>
    public static void Main(String[] args)<br>
    {<br>
        int a = 0, b = 1, i, c, n, j;<br>
        Console.Write("Enter the limit");<br>
        n = int.Parse(Console.ReadLine());<br><br>
        for (i = 1; i <= n; i++)<br>
        {<br>
            a = 0;<br>
            b = 1;<br>
            Console.Write(b + "\t");<br>
            for (j = 1; j < i; j++)<br>
            {<br>
                c = a + b;<br>
                Console.Write(c + "\t");<br>
                a = b;<br>
                b = c;<br>
            }<br>
            Console.Write("\n");<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97970956/156514236-cfda944e-fd4c-4f5b-b419-6ebac979f0b6.png)


**WINDOWS APPLICATION<br>
1. CONVERT DIGITS INTO WORD**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace ex2<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void button1_Click(object sender, EventArgs e)<br>
        {
            lbl_words.Text = NumtoWord(long.Parse(txt_num.Text));<br>
        }
        public string NumtoWord(long number)<br>
        {<br>
            string word = "";
            if (number == 0)
            {<br>
                return "Zero";<br>
            }<br>
            if (number < 0)<br>
            {<br>
                return "Minus" + Math.Abs(number);<br>
            }<br>
            if (number / 10000000 > 0)<br>
            {<br>
                word += NumtoWord(number / 10000000) + "Corer"; number %= 10000000;<br>
            }<br>

        if (number / 100000 > 0)<br>
            {<br>
                word += NumtoWord(number / 100000) + "Lacs";<br>
                number %= 100000;<br>
            }<br>
            if (number / 1000 > 0)<br>
            {<br>
                word += NumtoWord(number / 1000) + "Thousand";<br>
                number %= 1000;<br>
            }<br>
            if (number / 100 > 0)<br>
            {<br>
                word += NumtoWord(number / 100) + "Hundred";<br>
                number %= 100;<br>
            }<br>
            if (number > 0)<br>
            {<br>
                string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine","ten" ,"Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Nineteen" };<br>
                string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety" };<br>
                if (number < 20)<br>
                {<br>
                    word += units[number];<br>
                }<br>
                else<br>
                {<br>
                    word += Tens[number / 10];<br>
                    if (number % 10 > 0)<br>
                    {<br>
                        word += units[number % 10];<br>
                    }<br>
                }<br>
            }<br>
            return word;
        }<br>
    }<br>
}<br>

            

OUTPUT:


![image](https://user-images.githubusercontent.com/97940767/157811354-31ba1c0e-df5d-4955-9027-d3f228c69fa9.png)<br>
![image](https://user-images.githubusercontent.com/97940767/157811446-b77dd21d-7724-4ed1-a02b-2f06beef44c1.png)

**3.. C# Program to Perform Reversal, Padding and Trimming Operations on  string.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace lab4<br>
{<br>
    public partial class Form1 : Form<br>
    {
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString, revstr = "";<br>
            int Length;<br>
            inputString = txtInput.Text;<br>
            Length = inputString.Length - 1;<br>
            while (Length >= 0)<br>
            {<br>
                revstr = revstr + inputString[Length];<br>
                Length--;<br>
            }<br>
            MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>
        }<br>
private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
        }<br>
private void button3_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            inputString = inputString.PadLeft(10, '*');<br>
            inputString = inputString.PadRight(15, '*');<br>
            MessageBox.Show("String After Padding : " + inputString, "Result");<br>
        }<br>
    }<br>
}<br>


![image](https://user-images.githubusercontent.com/97970956/157820065-79e67d7d-46c8-461a-a607-7fdd031f5550.png)
![image](https://user-images.githubusercontent.com/97970956/157820232-0b687e42-9e6c-496c-853a-bc38c3eb344c.png)
![image](https://user-images.githubusercontent.com/97970956/157820318-dfcd95ad-00c0-4d1d-8ded-10c3ac9028f6.png)
![image](https://user-images.githubusercontent.com/97970956/157820384-0620f8ab-7e11-4bd8-9c44-da7a8ec3b629.png)

**26.c#program to create a progress bar control**
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading;<br>
using System.Windows.Forms;<br>
namespace lab5<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br><br>
        }<br>
private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            backgroundWorker1.WorkerReportsProgress = true;<br>
            backgroundWorker1.RunWorkerAsync();<br>
        }<br>
private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)<br>
        {<br>
            for(int i=1 ; i<=100;i++)<br>
            {<br>
                Thread.Sleep(50);<br>
                backgroundWorker1.ReportProgress(i);<br>
            }<br>
        }<br>
  private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)<br>
        {<br>
            progressBar1.Value = e.ProgressPercentage;<br>
            this.Text = "progress:" +<br>
                e.ProgressPercentage.ToString() + "%";<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/158744269-2ad9d518-8913-4469-adcf-46718cfcebed.png)

**27.Develop a winform application to create flat clock.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace lab6<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            timer1.Start();<br>
        }<br>
<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            System.Timers.Timer timer = new System.Timers.Timer();<br>
            timer.Interval = 1000;<br>
            timer.Elapsed += Timer_Elapsed;<br>
            timer.Start();<br>
        }<br>
        private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
        {<br>
            circularProgressBar1.Invoke((MethodInvoker)delegate<br>
            {<br>
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss"); circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM  }); <br>
            });<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/158755816-99f96cc5-2ea7-4637-ae81-f14e532c7351.png)
![image](https://user-images.githubusercontent.com/97970956/158755895-177a86d3-d664-4be4-8df4-32ffb939e1e7.png)


**28 C# program perform a number guessing game**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace lab9<br>
{<br>
    public partial class Form1 : Form<br>
    {// Intialising component  <br>
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        Button button1;<br>
        TextBox textBox1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;<br>

        public Form1()
        {
            InitializeComponent();
           
            {
                value = r.Next(100);
                this.Controls.Clear();
                this.BackColor = Color.SkyBlue;
                this.AutoSize = true;
                this.Padding = new Padding(16);
                Label label = new Label();
                label.Text = "Pick a number between 1 and 100"; label.Bounds = new Rectangle(10, 20, 340, 40); label.Font = new Font("Arial", 16);
                textBox1 = new TextBox();
                textBox1.Bounds = new Rectangle(20, 50, 120, 80); textBox1.Font = new Font("Arial", 24);

                button1 = new Button();
                button1.Text = " Check Your Guess ";
                button1.Bounds = new Rectangle(160, 50, 120, 40);

                button1.BackColor = Color.LightGray;
                button1.Click += new EventHandler(button1_Click);
                Label label2 = new Label();
                label2.Text = "Low Guess";
                label2.Bounds = new Rectangle(20, 150, 160, 40); label2.Font = new Font("Arial", 18);
                richTextBox1 = new RichTextBox();
                richTextBox1.Bounds = new Rectangle(20, 190, 160, 300); richTextBox1.Font = new Font("Arial", 16);
                Label label3 = new Label();
                label3.Text = "High Guess";
                label3.Bounds = new Rectangle(180, 150, 160, 40); label3.Font = new Font("Arial", 18);
                richTextBox2 = new RichTextBox();
                richTextBox2.Bounds = new Rectangle(180, 190, 160, 300); richTextBox2.Font = new Font("Arial", 16);
                label4 = new Label();
                label4.Bounds = new Rectangle(20, 100, 340, 40); label4.Font = new Font("Arial", 16);
                this.Controls.Add(label);
                this.Controls.Add(textBox1);
                this.Controls.Add(button1);
                this.Controls.Add(label4);
                this.Controls.Add(label2);
                this.Controls.Add(label3);
                this.Controls.Add(richTextBox1);
                this.Controls.Add(richTextBox2);
            }
        }

            private void button1_Click(object sender, EventArgs e)
            {
                // Coding of game  
                if (textBox1.Text == "")
                {
                    return;
                }
                guessnum = Convert.ToInt32(textBox1.Text); textBox1.Text = String.Empty;
                if (win >= 0)
                { 

                if (guessnum == value)
                    {
                        MessageBox.Show("You have guessed the number! \n The number was " + value); InitializeComponent();
                    }
                    else if (guessnum < value)
                    {
                        richTextBox1.Text += guessnum + "\n";
                        label4.Text = "wrong Guess and number of guesses left are " + (10 - guess);
                    }
                    else if (guessnum > value)
                    {
                        richTextBox2.Text += guessnum + "\n";
                        label4.Text = "wrong Guess and number of guesses left are " + (10 - guess);
                    }
                    guess++;
                    win--;
                }
                if (guess == 11)
                {
                    label4.Text = "You loose,Correct Guess is " + value;
                }
            }
           
        private void Form1_Load(object sender, EventArgs e)
        {

        }
    }
}

![image](https://user-images.githubusercontent.com/97970956/158955013-3f0d877d-981b-408a-a579-03851b05e772.png)
![image](https://user-images.githubusercontent.com/97970956/158954902-582ad59d-5a4b-4006-8d19-2dd743c99f42.png)
![image](https://user-images.githubusercontent.com/97970956/158955189-449a3f42-4c33-4201-98bd-8b8b8724a697.png)

**29. Develop an application to create a notepad.** <br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace lab21<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>

        }<br>
        private string fileName;<br>
        private RichTextBox txtContent;<br>
        private ToolBar toolBar;<br>
        internal Form1()<br>
        {<br>
            fileName = null;<br>
            initializeComponents();<br>
        }<br>
        void initializeComponents()<br>
        {<br>
            this.Text = "My notepad";<br>
            this.MinimumSize = new Size(600, 450);<br>
            this.FormClosing += new FormClosingEventHandler(NotepadClosing); this.MaximizeBox = true;<br>
            toolBar = new ToolBar();<br>
            toolBar.Font = new Font("Arial", 16);<br>
            toolBar.Padding = new Padding(4);<br>
            toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
            ToolBarButton toolBarButton1 = new ToolBarButton();<br>
            ToolBarButton toolBarButton2 = new ToolBarButton();<br>
            ToolBarButton toolBarButton3 = new ToolBarButton();<br> 
            toolBarButton1.Text = "New";<br>
            toolBarButton2.Text = "Open";<br>
            toolBarButton3.Text = "Save";<br>
            toolBar.Buttons.Add(toolBarButton1);<br>
            toolBar.Buttons.Add(toolBarButton2);<br>
            toolBar.Buttons.Add(toolBarButton3);<br><br>
            txtContent = new RichTextBox();<br>
            txtContent.Size = this.ClientSize;<br>
            txtContent.Height -= toolBar.Height;<br>
            txtContent.Top = toolBar.Height;<br>
            txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right | AnchorStyles.Top | AnchorStyles.Bottom;<br>
            txtContent.Font = new Font("Arial", 16);<br>
            txtContent.AcceptsTab = true;<br>
            txtContent.Padding = new Padding(8);<br>
            this.Controls.Add(toolBar);<br>
            this.Controls.Add(txtContent);<br>
        }<br>
        private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br>
        {<br>
            saveFile();<br>
            switch (toolBar.Buttons.IndexOf(e.Button))<br>
            {<br>
                case 0:<br>
                    this.Text += "My notepad";<br>
                    txtContent.Text = string.Empty;<br>
                    fileName = null;<br>
                    break;<br>
                case 1:<br>
                    OpenFileDialog openDlg = new OpenFileDialog();<br>
                    if (DialogResult.OK == openDlg.ShowDialog())
                    {<br>
                        fileName = openDlg.FileName;<br>
                        txtContent.LoadFile(fileName); <br>
                     <br>   this.Text = "My notepad " + fileName;<br>
                    }<br>
                    break;<br>
            }<br>
        }
        void saveFile()<br>
        {<br>
            if (fileName == null)<br>
            {<br>
                SaveFileDialog saveDlg = new SaveFileDialog();<br>
                if (DialogResult.OK == saveDlg.ShowDialog())<br>
                {<br>
                    fileName = saveDlg.FileName;<br>
                    this.Text += " " + fileName;<br>
                }<br>
            }<br>
            else<br>
            {
                txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br>
            }<br>
        }<br>
        private void NotepadClosing(Object sender, FormClosingEventArgs e)<br>
        {<br>
            saveFile();<br>
           
        }<br>
      
        /*static void Main(String[] args)<br>
        {<br>
            Application.Run(new NotepadForm());<br>
        }*/<br>
    }<br>

}<br>


![image](https://user-images.githubusercontent.com/97970956/160995813-173a2a45-f8f9-4398-a0b0-b6749e2a57ae.png)

**30.23. C# Program to Perform Reversal, Padding and Trimming Operations on  string. **
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using System.Drawing.Drawing2D;


namespace lab23
{
    public partial class Form1 : Form
    {
        private Node root;
        public Form1()
        {
            InitializeComponent();
            this.root = null;
            test();  
        }
        void test()
        {
            textBox1.Text = "5";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "3";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "2";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "1";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "4";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "7";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "6";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "8";
            btnAdd_Click(btnAdd, null);
        }

        private void btnAdd_Click(object sender, EventArgs e)
        {
            int value = int.Parse(textBox1.Text); if (root == null)
                root = new Node(value);
            else
            {
                if (root.Add(value) == false)
                    MessageBox.Show("The value already exists!");
            }
            drawTree();

        }

        private void btnRemove_Click(object sender, EventArgs e)
        {
            int value = int.Parse(textBox1.Text); if (root != null)
            {
                bool status = root.Remove(value, root, ref root); if (status == false)
                {
                    MessageBox.Show("the value does not exists");
                }
            }
                      drawTree();

        }

        private void btnSearch_Click(object sender, EventArgs e)
        {
            string msg;
            int value = int.Parse(textBox1.Text); 
            if (root == null)
            {
                msg = "Tree is empty";
            }
            else
            {
                if (root.Exists(value))
                {
                    msg = "Value found";
                }
                else
                {
                    msg = "Value not found";
                }
            }
            MessageBox.Show(msg);

        }

        private void btnCreate_Click(object sender, EventArgs e)
        {
            root = null;
            pictureBox1.Image = null;

        }
        void drawTree()
        {
            if (root != null)
                pictureBox1.Image = root.Draw();
            else
                pictureBox1.Image = null;
            this.Update();
        }
       /* static void Main()
        {
            Application.Run(new Form());
        }*/
    }
    class Node
    {
        internal Node left { get; set; }
        internal Node right { get; set; }
        internal int value;
        internal int center = 12;
        private static Bitmap nodeBg = new Bitmap(30, 25); 
        private static Font font = new Font("Arial", 14);
        internal Node(int value)
        {
            this.value = value;
        }
        internal bool Add(int value)
        {
            Node node = new Node(value);
            if (value < this.value)
            {
                if (this.left == null)
                {
                    this.left = node;
                    return true;
                }
                else
                    return this.left.Add(value);
            }
            else if (value > this.value)
            {
                if (this.right == null)

             {
                    this.right = node;
                    return true;
                }
 else
                    return this.right.Add(value);
            }
            return false;
        }
        internal bool Remove(int value, Node parent, ref Node root)
        {
            if (value < this.value)
            {
                if (left != null)
                {
                    return left.Remove(value, this, ref root);
                }
            }
            else if (value > this.value)
            {
                if (right != null)
                {
                    return right.Remove(value, this, ref root);
                }
            }
            else if (value == this.value)
            {
                bool isLeft = (this == parent.left);
                if (left == null && right == null)
                {
                    if (root == this)
                        root = null;
                    else
                    if (isLeft) parent.left = null; else parent.right = null;
                }
                else if (right == null)
                {
                    if (isLeft) parent.left = left; else parent.right = left; if (root == this)
                        root = left;
                }
                else
                {
                    if (right.left == null)
                    {
                        right.left = left;
                        if (isLeft) parent.left = right;
                        else

                    parent.right = right;
                        if (root == this)
                            root = right;
                    }
                    else
                    {
                        Node node = right;
                        while (node.left.left != null)
                            node = node.left;
                        Console.WriteLine("Node: " + node.value);
                        this.value = node.left.value;
                        Console.WriteLine("here");
                        node.left = null;
                    }
                }
                return true;
            }
            return false;
        }
        public Image Draw()
        {
            Size lSize = new Size(nodeBg.Width / 2, 0);
            Size rSize = new Size(nodeBg.Width / 2, 0);
            Image lNodeImg = null;
            Image rNodeImg = null;
            int lCenter = 0, rCenter = 0;

            if (this.left != null)
            {
                lNodeImg = left.Draw();
                lSize = lNodeImg.Size;
                this.center = lSize.Width;
                lCenter = left.center;
            }
            if (this.right != null)
            {
                rNodeImg = right.Draw();
                rSize = rNodeImg.Size;
                rCenter = right.center;
            }
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height; 
            if (maxHeight > 0) maxHeight += 35;

        Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height + maxHeight);
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);
            Graphics g = Graphics.FromImage(result);
            g.SmoothingMode = SmoothingMode.HighQuality;
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize));
            g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);
            string str = "" + value;
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7, nodeBg.Height / 2f - 12);
            Pen pen = new Pen(Brushes.Black, 1.2f);
            float x1 = center;
            float y1 = nodeBg.Height;
            float y2 = nodeBg.Height + 35;
            float x2 = lCenter;
            var h = Math.Abs(y2 - y1);
            var w = Math.Abs(x2 - x1);
            if (lNodeImg != null)
            {
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35); var points1 = new List<PointF>
            {
                 new PointF(x1, y1),
                 new PointF(x1 - w/6, y1 + h/3.5f),
                 new PointF(x2 + w/6, y2 - h/3.5f),
                 new PointF(x2, y2),
            };
                g.DrawCurve(pen, points1.ToArray(), 0.5f);
            }
            if (rNodeImg != null)
            {
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35); x2 = rCenter + lSize.Width;
                w = Math.Abs(x2 - x1);
                var points = new List<PointF>
            {
                new PointF(x1, y1),
                 new PointF(x1 + w/6, y1 + h/3.5f),
                new PointF(x2 - w/6, y2 - h/3.5f),
                    new PointF(x2, y2)
 };

            g.DrawCurve(pen, points.ToArray(), 0.5f);
            }
            return result;
        }
        public bool Exists(int value)
        {
            bool res = value == this.value;
            if (!res && left != null)
                res = left.Exists(value);
            if (!res && right != null)
                res = right.Exists(value);
            return res;
        }
    }
} 

    








