## Module 1: The Backend Translation
Reminder of the Logic: We need to store a soda price ($1.50), get the user's money, and check if it's enough.

1. **Python (The Readable Speedster)**
Python is famous for stripping away punctuation. It doesn't use semicolons, and it uses blank spaces (indentation) to 
figure out what code belongs inside the if/else statement.

	**Python**
	# 1. Store the price
	
		soda_price = 1.50
	
	# 2 & 3. Ask for money and turn the answer into a decimal number
	
		user_money = float(input("Enter your money: "))
	
	# 4. The Decision
		if user_money >= soda_price:
	    	print("Enjoy your drink!")
	
		else:
	    	print("Inadequate funds.")
		



2. **Java (The Organized Industrial Blueprint)**
Java is very strict. You can't just create a variable; you have to tell Java exactly what type of data is going inside it
(we use double for decimal numbers). It also requires a lot of "setup code" just to get the program running.

	**Java**
		import java.util.Scanner;
		
		public class VendingMachine {
		    public static void main(String[] args) {
		        Scanner input = new Scanner(System.util.in);
		        
		        // 1. Store the price (Must declare it's a double)
		        double soda_price = 1.50;
		        
		        // 2 & 3. Ask for money and read the decimal input
		        System.out.print("Enter your money: ");
		        double user_money = input.nextDouble();
		        
		        // 4. The Decision (Uses curly brackets to hold the logic)
		        if (user_money >= soda_price) {
		            System.out.println("Enjoy your drink!");
		        } else {
		            System.out.println("Inadequate funds.");
		        }
		    }
		}




3. **C# (The Corporate Powerhouse)**
Look closely at C# below. You will notice it looks almost exactly like Java. Microsoft built C# to compete with Java, 
so they share the same strict rules, curly brackets, and semicolons.

	** C# **
		using System;
		
		class VendingMachine {
		    static void Main() {
		        // 1. Store the price
		        double soda_price = 1.50;
		        
		        // 2 & 3. Ask for money and convert the text answer into a decimal number
		        Console.Write("Enter your money: ");
		        double user_money = Convert.ToDouble(Console.ReadLine());
		        
		        // 4. The Decision
		        if (user_money >= soda_price) {
		            Console.WriteLine("Enjoy your drink!");
		        } else {
		            Console.WriteLine("Inadequate funds.");
		        }
		    }
		}




4. **PHP (The Web's Old Reliable)**
PHP was built specifically for the web. Because it's designed to live alongside HTML, all PHP code has to start 
with a special tag <?php. Another unique rule of PHP is that every single variable name must start with a dollar sign ($).

	** PHP **
	<?php
	// 1. Store the price (Notice the $ before the name)
		$soda_price = 1.50;
	
	// 2 & 3. Ask for money and read what the user types in the terminal
		echo "Enter your money: ";
		$user_money = (float)readline();
	
	// 4. The Decision (Uses standard parentheses and curly brackets)
		if ($user_money >= $soda_price) {
		    echo "Enjoy your drink!\n";
		} else {
		    echo "Inadequate funds.\n";
		}
		?>




5. **Ruby (The Elegant Reader)**
Ruby’s philosophy is to make coding beautiful and natural. Like Python, it drops semicolons and parentheses. 
It also drops the word print or echo and just uses puts (short for "put string on the screen"). It closes its decisions 
with a clean end statemen

	**Ruby**
	# 1. Store the price
		soda_price = 1.50
	
	# 2 & 3. Ask for money and look at the answer
		print "Enter your money: "
		user_money = gets.to_f # "gets" catches the input, "to_f" turns it into a decimal float
	
	# 4. The Decision
		if user_money >= soda_price
		  puts "Enjoy your drink!"
		else
		  puts "Inadequate funds."
		end




## The "Plain English" Lesson for Beginners

**Lesson 1: Data Types are just "Labeling the Moving Boxes"**
Computers need to know what kind of data they are holding so they can allocate space in their memory chip. 
In our plain English logic, we just said "Remember the price is $1.50."

**Python** and **Ruby** are laid-back. They look at 1.50 and say, "Cool, that's a decimal number. 
I'll handle it automatically behind the scenes."

**Java** and ** C# *** are strict. They demand to know the exact box type upfront. We use the keyword double 
(which stands for double-precision floating-point number) to tell the machine: "Hey, prepare for a precise decimal number."

**PHP** requires a middle-ground approach. It handles the box automatically, but forces you to use a $ symbol so it 
never mistakes a variable name for a standard text word.

**Lesson 2: Input is just "Listening to the World"**
A computer program is completely isolated until you open a window for data to flow in.

	**Python** uses **input()**

	**Java** uses **input.nextDouble()**

	**C#** uses **Console.ReadLine()**

	**PHP** uses **readline()**

	**Ruby** uses **gets**

Different words, same exact concept: The program pauses, opens its ears, waits for the user to hit the 'Enter' key, 
and catches whatever they typed.

## The If/Else Structure
Look at the shape of the code across all five languages. They all follow a rigid logical fork in the road:

		[ Is the money >= the price? ]
		             /          \
		          YES            NO
		          /                \
		   "Enjoy your drink!"   "Inadequate funds."
	   
   No matter how many curly brackets ({}), dollar signs ($), or end keywords the languages use, 
   the machine is doing the exact same logical evaluation. ---






