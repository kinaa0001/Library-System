package BookRentalSystem;

import java.util.InputMismatchException;
import java.util.Scanner;

public class Stock {
	
		String book [] = {"System Analysis and Design", "Android Application","Programming Concepts and Logic Formulation"};
		String author [] = {"Gary B. Shelly", "Corinne Hoisington", "Rosauro E. Manuel"};
		int copy [] = {2,3,4};	

		private Stock(){	 
			System.out.println("ELECTRONIC BOOK RENTAL SYSTEM");
			System.out.println("*****************************");
			for (int i = 0; i < 3; i++) {
				System.out.println(i + " " + book[i] + ", " + author[i]);
			}
			choose();
		}
		
		void choose() {
			
			Scanner s = new Scanner (System.in);
			boolean valid = false;
			System.out.println("*****************************");
			System.out.print("CHOOSE A NUMBER TO RENT YOUR BOOK: ");
			while (valid == false) {
				
				int choice = s.nextInt();
		
				try {
					if (copy[choice] > 0) {
						System.out.println("\nYou Rented " + book[choice] + ".");
						copy[choice] = 1;
					}
					else {
						System.out.println("No Copies Available");
					}
					System.out.print("\nRENT AGAIN? Y/N: ");
					char letter = s.next().charAt(0);
						if(letter == 'N' || letter == 'n') {
							valid = true;
						}
						else if (letter == 'Y' || letter == 'y'){
							Stock();
						}
						else {
							System.out.println("INVALID INPUT");
						}
				}
				catch (IndexOutOfBoundsException ex) 
				{
					System.out.println("INVALID INPUT CHOOSE A NUMBER TO RENT YOUR BOOK:   ");
				}
				catch(InputMismatchException ex)
			{ 
					System.out.println("INVALID INPUT");
			
				}
			}
			System.out.println("PROGRAM ENDS");
	
}
		}
		
				
