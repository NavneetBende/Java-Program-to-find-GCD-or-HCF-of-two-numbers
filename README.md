# Java-Program-to-find-GCD-or-HCF-of-two-numbers

HCF of two numbers in Java
 

Here, in this section we will discuss HCF of two numbers in java.
GCD(Greatest Common Divisor) or HCF(Highest Common Factor) of two numbers is the number which is the largest common factor of both numbers. It is also referred as Greatest Common Factor(GCF), Greatest Common Measure(GCM), Highest Common Divisor(HCD).

GCD in java
While loop in C
We will learn
Method 1: Linear Quest to find HCF
Method 2: Euclidean Algorithm: Repeated Subtraction
Method 3: Recursive Euclidean Algorithm: Repeated Subtraction
Method 4: Modulo Recursive Euclidean Algorithm: Repeated Subtraction
Method 5: Handling Negative Numbers in HCF
Method 1 : Linear Quest
Algorithm
Initialize HCF = 1
Run a loop in the iteration of (i) between [1, min(num1, num2)]
Note down the highest number that divides both num1 & num2
If i satisfies (num1 % i == 0 && num2 % i == 0) then new value of HCF is i
Print value of HCF
Method 1 : Java Code
Run
class Main
{
  public static void main (String[]args)
  {
    int num1 = 36, num2 = 60, hcf=0;

    for (int i = 1; i <= num1 || i <= num2; i++)
      {
     if (num1 % i == 0 && num2 % i == 0)
        hcf = i;
      }

    System.out.println("The HCF: "+ hcf);
  }
}
Output
HCF of 36 and 60 is 12
Method 2 : Repeated Subtraction
Algorithm
Run a while loop until num1 is not equals to num2
If num1>num2 then num1 = num1 – num2
Else num2 = num2 – num1
After the loop ends both num1 & num2 stores HCF
Method 2 : Java Code
Run
class Main
{
  public static void main (String[]args)
  {
    int num1 = 36, num2 = 60, hcf;

    while (num1 != num2)
    {
        if (num1 > num2)
            num1 -= num2;
        else
            num2 -= num1;
    }


    System.out.println("The HCF: "+ num1);
  }
}
Output
HCF of 36 and 60 is 12
Related Pages
Lowest Common Multiple (LCM)

Greatest Common Divisor

Binary to Decimal to conversion

Octal to Decimal conversion

Hexadecimal to Decimal conversion

Method 3 : Repeated Subtraction using Recursion
Algorithm
Checked whether any of the input is 0 then return sum of both numbers
If both input are equal return any of the two numbers
If num1 is greater than the num2 then Recursively call findHCF(num1 – num2, num2)
Else Recursively call findHCF(num1, num2-num1)
Method 3 : Java Code
Run
class Main
{
  public static void main (String[]args)
  {
    int num1 = 36, num2 = 60, hcf;

      hcf = getHCF (num1, num2);
      System.out.println ("The HCF: " + hcf);
  }

  static int getHCF (int num1, int num2)
  {
    // Handles the case when one of the number is 0 (num1) 
    // Check alert above in explanation
    if (num1 == 0)
      return num2;

    // Handles the case when one of the number is 0 (num2)
    // Check alert above in explanation
    if (num2 == 0)
      return num1;

    // base case
    if (num1 == num2)
      return num1;

    // num1 is greater
    if (num1 > num2)
      return getHCF (num1 - num2, num2);

    return getHCF (num1, num2 - num1);
  }
}
Output
HCF of 36 and 60 is 12
Method 4 : Repeated Subtraction with Modulo Operator using Recursion
Algorithm
If b is equals to 0 return a
Else recursively call the function for value b, a%b and return 
Method 4 : Java Code
Run
class Main
{
    public static void main (String[]args)
    {
        int num1 = 36, num2 = 60, hcf;

            hcf = getHCF (num1, num2);
            System.out.println ("The HCF: " + hcf);
    }

// This method improves complexity of repeated substraction
// By efficient use of modulo operator in euclidean algorithm
    static int getHCF (int a, int b)
    {
        return b == 0 ? a : getHCF (b, a % b);
    }
}
Output
HCF of 36 and 60 is 12
Method 5 : Handling Negative Numbers in HCF
Algorithm
If any of the number is negative then convert it to positive by multiplying it with -1 as according to the proper definition HCF of two numbers can never be negative.

If b is equals to 0 return a
Else recursively call the function for value b, a%b and return 
Method 5 : Java Code
Run
class Main
{
    public static void main (String[]args)
    {
        int num1 = -36, num2 = 60, hcf = 1;

        // if user enters negative number, we just changing it to positive
        // By definition HCF is highest positive number that divides both numbers
        // -144 & 32 : HCF = 16 (as highest num that divides both)
        // -144 & - 32 : HCF = 16 (as highest num that divides both)
            num1 = (num1 > 0) ? num1 : -num1;
            num2 = (num2 > 0) ? num2 : -num2;

            hcf = getHCF (num1, num2);
            System.out.println ("The HCF: " + hcf);
}

// This method improves complexity of repeated substraction
// By efficient use of modulo operator in euclidean algorithm
    static int getHCF (int a, int b)
    {
        return b == 0 ? a : getHCF (b, a % b);
    }
}
Output
HCF of -36 and 60 is 12
