    using System;

    class ArithmeticCalculator
    {
       static void Main(string[] args)
     {
        char continueChoice;

        // While loop to repeat calculator sequence until user chooses 'N'
        while (true)
        {
            // Display menu interface
            Console.WriteLine("Press any following key to perform an arithmetic operation:");
            Console.WriteLine("1 - Addition");
            Console.WriteLine("2 - Subtraction");
            Console.WriteLine("3 - Multiplication");
            Console.WriteLine("4 - Division");

            // Get and validate operation choice
            int operation;
            while (!int.TryParse(Console.ReadLine(), out operation) || operation < 1 || operation > 4)
            {
                Console.WriteLine("Invalid choice! Please enter 1, 2, 3, or 4.");
            }

            // Get and validate numerical inputs
            double value1, value2;
            Console.Write("Enter Value 1: ");
            while (!double.TryParse(Console.ReadLine(), out value1))
            {
                Console.Write("Invalid input! Please enter a number for Value 1: ");
            }

            Console.Write("Enter Value 2: ");
            while (!double.TryParse(Console.ReadLine(), out value2))
            {
                Console.Write("Invalid input! Please enter a number for Value 2: ");
            }

            // Switch-case to route to selected operation
            switch (operation)
            {
                case 1:
                    double sum = Add(value1, value2);
                    Console.WriteLine($"{value1} + {value2} = {sum}");
                    break;
                case 2:
                    double difference = Subtract(value1, value2);
                    Console.WriteLine($"{value1} - {value2} = {difference}");
                    break;
                case 3:
                    double product = Multiply(value1, value2);
                    Console.WriteLine($"{value1} * {value2} = {product}");
                    break;
                case 4:
                    // Handle division by zero
                    if (value2 == 0)
                    {
                        Console.WriteLine("Error: Cannot divide by zero!");
                    }
                    else
                    {
                        double quotient = Divide(value1, value2);
                        Console.WriteLine($"{value1} / {value2} = {quotient}");
                    }
                    break;
            }

            // Prompt to continue or exit
            Console.Write("Do you want to continue again (Y/N)? ");
            continueChoice = char.ToUpper(Console.ReadKey().KeyChar);
            Console.WriteLine("\n");

            // Exit loop if user chooses 'N'
            if (continueChoice == 'N')
            {
                break;
            }
        }
    }

    // Dedicated method for Addition
    static double Add(double a, double b)
    {
        return a + b;
    }

    // Dedicated method for Subtraction
    static double Subtract(double a, double b)
    {
        return a - b;
    }

    // Dedicated method for Multiplication
    static double Multiply(double a, double b)
    {
        return a * b;
    }

    // Dedicated method for Division
    static double Divide(double a, double b)
    {
        return a / b;
    }
