/* David Hernandez
 * 12/18/2021
 * Description: Program prompts user to input a binary number, then converts it to a decimal value.
 * If a invalid binary number is inputed, a prompt to input a valid binary number is displayed.
 * Let's user know if the number is divisible by 3, or 5, or both.
 * Displays the decimal number with numbers reversed, and returns the sum of the numbers making up the decimal value.
 * Program continues until a 0 is inputed.
 */

import java.util.Scanner;

public class BinToDecimal
{

	public static void main(String[] args) 
	{
		//scanner object used for input
		Scanner kbd = new Scanner(System.in);
		
		//long to store binary number
		long binary = 0;
	
		
		//prompt for user input of a binary number
		System.out.print("Please enter a binary number (leading zeros are OK), 0 to Quit: ");
		
		//input
		binary = kbd.nextLong();
		
		
		//run while binary input doesn't equal 0
		while(binary != 0)
		{
			
			//while method isBinary returns false, prompt user to input a valid binary number
			while(!isBinary(binary))
			{
				
				//display that input was not a valid binary number
				System.out.println("Sorry, your number is not a binary number.\nPlease enter a binary number (leading zeros are OK)");
					
				//new input
				binary = kbd.nextLong();
				
			}
			
			
			//display input and its conversion to decimal
			System.out.printf("The decimal value of your binary number %d is: %d", binary, binaryToDecimal(binary));
				
			//display message before invoking method 
			System.out.print("\nInvoking divCheck: Divisible by 3, 5, both, or neither? ");
				
			//invoking method, method binaryToDecimal returns long, divCheck takes and returns int so typecast was required
			divCheck((int)binaryToDecimal(binary));
				
				
			System.out.print("\nYour decimal value backwards is: ");
					
			System.out.printf("\nThe sum of the digits of your decimal number is: %d\n", backpedalAndSum((int)binaryToDecimal(binary)));
				
			//prompt for user input of a binary number
			System.out.print("Please enter a binary number (leading zeros are OK), 0 to Quit: ");
				
			//input
			binary = kbd.nextLong();
				
				
			
		}
		
		
		//close scanner
		kbd.close();
		
		
	}//end main
	
	//METHODS BELOW
	
	//method used to identify if method is binary
	public static boolean isBinary(long num)
	{
		//flag will remain true if the input is a binary number
		boolean flag = true;
		
		//long remainder (used long since method argument is a long)
		long remainder = 0;
		
		
		//stripping one number at a time
		//while loop, divides number by 10 until the number is greater than 0 and while flag is still true
		while(flag && num >0)
		{
			//remainder is the num modulo 10
			remainder = num % 10;
			
			//if the remainder is greater than 1, then the inputed number is not a valid binary number
			if(remainder > 1)
			{
				//flag is set to false
				flag = false;
			}
			
			//num is equal to num divided by 10
			num /= 10;
		}
	
		
		//returns boolean 
		return flag;
		
	}//end method
	
	//function convert binary to decimal
	public static long binaryToDecimal(long n)
	{
	
		//result to store binary number converted to decimal
		long result = 0;
		
		long last_digit = 0;
		
		//initialize base
		int base = 1;
		
		//while loop, runs while n is greater than 0
		while (n > 0)
		{
			//last_digit is n modulo 10
			last_digit = n % 10;
			
			//divide by 10 to strip thte last digit
			n = n/10;
			
			//result = result + last_digit * base
			result += last_digit * base;
			
			//update power of 2
			base = base * 2;
			
		}
		
		//return result
		return result;
		
	}//end method
	
	//identifies if decimal number is divisible by 3,5 or neither
	public static void divCheck(int decimalNum)
	{
				
		//prompt if value is divisible by 3 and 5
		if(decimalNum % 3 == 0 && decimalNum % 5 == 0)
		{
			System.out.print("Divisable by 3 and 5!");
			
		}
		//else, value isnt divisible by both 3 and 5, then display if number is divisible by only 3
		else if(decimalNum % 3 == 0)
		{
			System.out.print("divisable by 3!");
		}
		//else, since value isnt divisible by 3 and 5, or only by 3, check if divisible by only 5
		else if(decimalNum % 5 == 0)
		{
			System.out.print("Divisable by 5!");
		}
		//if no other parameter is met, displau that value is not displayed by either 3 or 5
		else
		{
			System.out.print("Not divisable by 3 or 5!");
		}
		
}//end method
	
	//method prints the converted decimal value in reverse and also returns the addition of all the numbers in the decimal value
	public static int backpedalAndSum(int decimalNum)
	{
		
		//remainder to store stripped digit
		int remainder = 0;
		//addition to hold the addition of numbers
		int addition = 0;
		
		//while loop, runs while decimalNum is greater than 0
		while(decimalNum > 0)
		{
			//remainder equals decimalNum modulo 10
			remainder = decimalNum % 10;
			//print remainder number with spacing
			System.out.printf("%d ", remainder);
			
			//addition = addition plus remainder
			addition += remainder;
			
			//decimalNum = decimalNum / remainder;
			decimalNum /= 10;	
		}
		
		//return addition 
		return addition;
	}
	
}//end method



