# Repository-11
Create a class called Complex for performing arithmetic with complex numbers. Complex numbers have the form realPart + imaginaryPart * i where i is Write a program to test your class. Use floating-point variables to represent the private data of the class. Provide a constructor that enables an object of this class to be initialized when it’s declared. Provide a no-argument constructor with default values in case no initializers are provided. Provide public methods that perform the following operations: a) Add two Complex numbers: The real parts are added together and the imaginary parts are added together. b) Subtract two Complex numbers: The real part of the right operand is subtracted from the real part of the left operand, and the imaginary part of the right operand is subtracted from the imaginary part of the left operand. c) Print Complex numbers in the form (a, b), where a is the real part and b is the imaginary part.
import java.util.Scanner;

// Test Program
public class ComplexTest 
{
	 public static void main(String args[])
	 {
		 Scanner in=new Scanner(System.in);
		 double real1;
		 double imaginary1;
		 double real2;
		 double imaginary2;
		 
		 Complex complex1=new Complex();
		 Complex complex2=new Complex();
		 
		 System.out.printf("Enter 1st Real Number:");
		 real1=in.nextFloat();
		 complex1.setreal(real1);
		 
		 System.out.printf("Enter 1st Imaginary Number:");
		 imaginary1=in.nextFloat();
		 complex1.setimaginary(imaginary1);
		 
		 System.out.printf("The first Complex Number is :"+complex1.getreal()+"+"+complex1.getimaginary()+"i" );
		 
		 System.out.printf("\nEnter 2nd Real Number:");
		 real2=in.nextFloat();
		 complex2.setreal(real2);
		 System.out.printf("Enter 2nd Imaginary Number:");
		 imaginary2=in.nextFloat();
		 complex2.setimaginary(imaginary2);
		 System.out.printf("The Second Complex Number is :" +complex2.getreal()+"+"+complex2.getimaginary()+"i");
		 
		System.out.printf("\n%s%s","New complex Number after adding:",complex1.Add(complex2).toString());
		System.out.printf("\n%s%s","New complex Number after subtracting:",complex1.Subtract(complex2).toString());
		
	 }
}



public class Complex 
{
	private double real;
	private double imaginary;
	public Complex (double real, double imaginary)
	{
		this.real=real;
		this.imaginary=imaginary;		
	}
	public Complex()
	{
		real=0;
		imaginary=0;
	}
	public void setreal(double real)
	{
		this.real=real;
	}
	public double getreal()
	{
		return real;
	}
	public void setimaginary(double imaginary)
	{
		this.imaginary=imaginary;
	}
	public double getimaginary()
	{
		return imaginary;
	}
	public Complex Add(Complex addend)
	{
		double R=real+addend.real;
		double I=imaginary+addend.imaginary;
		return new Complex (R,I);
	}
	public Complex Subtract(Complex subtrahend)
	{
		double R=real-subtrahend.real;
		double I=imaginary-subtrahend.imaginary;
		return new Complex (R,I);
	}

	public String toString()
	 {
	    return String.format("%.2f%s%.2f%s",getreal(),"+",getimaginary(),"i");
	 }
	
}


