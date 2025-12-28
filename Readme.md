    using System;

    class ArithmeticCalculator
    {
    static void Main()
    {
        char c;
        while (true)
        {
            Console.WriteLine("1-Add\n2-Sub\n3-Mul\n4-Div");
            int op;
            while (!int.TryParse(Console.ReadLine(), out op) || op < 1 || op > 4)
                Console.WriteLine("1-4!");

            double v1, v2;
            Console.Write("V1: ");
            while (!double.TryParse(Console.ReadLine(), out v1))
                Console.Write("Num: ");
            Console.Write("V2: ");
            while (!double.TryParse(Console.ReadLine(), out v2))
                Console.Write("Num: ");

            switch (op)
            {
                case 1: Console.WriteLine($"{v1}+{v2}={Add(v1,v2)}"); break;
                case 2: Console.WriteLine($"{v1}-{v2}={Subtract(v1,v2)}"); break;
                case 3: Console.WriteLine($"{v1}*{v2}={Multiply(v1,v2)}"); break;
                case 4: Console.WriteLine(v2==0?"Err":$"{v1}/{v2}={Divide(v1,v2)}"); break;
            }

            Console.Write("Again(Y/N)? ");
            c = char.ToUpper(Console.ReadKey().KeyChar);
            Console.WriteLine();
            if (c == 'N') break;
        }
    }

    static double Add(double a, double b) => a + b;
    static double Subtract(double a, double b) => a - b;
    static double Multiply(double a, double b) => a * b;
    static double Divide(double a, double b) => a / b
    }
