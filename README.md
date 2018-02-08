# calculatorProject
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Calculator
{   
    public class Standard
    {
        public double x;
        public double y;
        public double z;
        public double c;
        public double v;

        public void calcStandard(double x, double y, double z, double c, double v)
        {
            

                       
            
                int wybor = 0;
                Console.Write("\n1) Addition (+)\n2) Subtraction (-)\n3) Multiply (x)\n4) Division (/)  : ");
                wybor = Convert.ToInt32(Console.ReadLine());
            

            switch (wybor)
            {
                case 1:
                    Console.Write("\nx=");
                    x = Convert.ToDouble(Console.ReadLine());

                    Console.Write("\ny=");
                    y = Convert.ToDouble(Console.ReadLine());

                    double add = x + y;
                    Console.WriteLine("\nResult: {0} + {1} = {2}", x, y, add);
                    break;

                case 2:
                    Console.Write("\nx=");
                    x = Convert.ToDouble(Console.ReadLine());

                    Console.Write("\ny=");

                    z = Convert.ToDouble(Console.ReadLine());

                    double sub = x - z;
                    Console.WriteLine("\nResult: {0} - {1} = {2}", x, z, sub);
                    break;

                case 3:
                    Console.Write("\nx=");
                    x = Convert.ToDouble(Console.ReadLine());
                    Console.Write("\ny=");

                    c = Convert.ToDouble(Console.ReadLine());

                    double multi = x * c;
                    Console.WriteLine("\nResult: {0} x {1} = {2}", x, c, multi);
                    break;

                case 4:
                    Console.Write("\nx=");
                    x = Convert.ToDouble(Console.ReadLine());
                    Console.Write("\ny=");

                    v = Convert.ToDouble(Console.ReadLine());

                    double divi = x / v;
                    Console.WriteLine("\nResult: {0} / {1} = {2}", x, v, divi);
                    break;

                default:
                    Console.WriteLine("\nOperation unknown...");
                    break;
            }
        }
    }

    public class Scientific : Standard
    {
        

        public void calcScience()
        {
            int wybor = 0;
            Console.Write("\n1) Power\n2) Square root\n3) Modulo\n4) Standard options  : ");
            wybor = Convert.ToInt32(Console.ReadLine());

            switch (wybor)
            {
                case 1:
                    Console.Write("\nx=");
                    x = Convert.ToDouble(Console.ReadLine());

                    Console.Write("\nThe degree of power: ");
                    y = Convert.ToDouble(Console.ReadLine());

                    
                    double number = x;

                    for (int i = 1; i < y; i++)
                    {
                        number *= x;
                    }
                    Console.WriteLine("\n\nResult: " + number);

                    break;

                case 2:
                    Console.Write("\nx=");
                    x = Convert.ToDouble(Console.ReadLine());

                    Console.WriteLine("\nResult: " + Math.Sqrt(x));
                    break;

                case 3:
                    Console.Write("\nx=");
                    x = Convert.ToDouble(Console.ReadLine());

                    Console.Write("\ny=");
                    c = Convert.ToDouble(Console.ReadLine());

                    double modulo = x % c;
                    Console.WriteLine("\nResult: {0} % {1} = {2}", x, c, modulo);
                    break;

                case 4:

                    calcStandard(1, 2, 3, 4, 5);
                    break;

                default:
                    Console.WriteLine("\nOperation unknown...");
                    break;
            }
        }

    }

    public class Binary : Scientific
    {
        public int bin;

        public void compTranslation(int bin)
        {
            Console.Write("\nx=");

            bin = Convert.ToInt32(Console.ReadLine());
            string binary = Convert.ToString(bin, 2);
            Console.WriteLine("Binary representation of {0} is {1}", bin, binary);

            Console.Write("\nDo you want to make another operation?\n1)Yes      2)No\n");

            int x = Convert.ToInt32(Console.ReadLine());
            if (x == 1)
            {
                Console.Write("Choose calculator type\n1)Standard\n2)Scientific\n3)Binary  : ");
                int type = Convert.ToInt32(Console.ReadLine());
                if (type == 1)
                {
                    calcStandard(1, 2, 3, 4, 5);
                }
                else if (type == 2)
                {
                    calcScience();
                }
                else if (type == 3)
                {
                    compTranslation(0);
                }
                else
                    return;
            }
            else
                return;
        }
    }


    class Program
    {
        static void Main(string[] args)
        {

                Console.Write("Choose calculator type\n1)Standard\n2)Scientific\n3)Binary  : ");
                int type = Convert.ToInt32(Console.ReadLine());

            if (type == 1)
            {
                Standard dzialanie = new Standard();
                dzialanie.calcStandard(1, 2, 3, 4, 5);
            }

            else if (type == 2)
            {
                Scientific przelicz = new Scientific();
                przelicz.calcScience();
            }

            else if (type == 3)
            {
                Binary binary = new Binary();
                binary.compTranslation(1);
            }

            else
            {
                Console.WriteLine("Unspecified option. Please restart the application.");
            }


            Console.ReadKey();
        }

    }

}
