# Arrays
package Arraysss;

import java.util.*;

public class Demo2 {
	
	// Method to accept an array from user input
	public int[] accept() 
	{
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter size of array:");
		int size = sc.nextInt();
		int[] num = new int[size];
		System.out.println("Enter your numbers:");
		for (int i = 0; i < size; i++)
		{
			System.out.print("Enter number at index " + i + ": ");
			num[i] = sc.nextInt();
		}
		return num;
	}

	
	// Method to sort an array in ascending order
	public int[] ascending()
	{
		int value[] = accept();
		Arrays.sort(value);
		System.out.println("Your Data is Sorted in Ascending Order: ");
		for (int i = 0; i < value.length; i++) 
		{
			System.out.print(value[i] + " ");
		}
		System.out.println(" ");
		return value;
	}

	
	// Method to sort an array in descending order
	public int[] descending()
	{
		int value[] = ascending();  // Reusing the ascending() method
		Arrays.sort(value);
		for (int i = 0; i < value.length / 2; i++)
		{
			// Swap elements to reverse the order
			int temp = value[i];
			value[i] = value[value.length - 1 - i];
			value[value.length - 1 - i] = temp;
		}
		System.out.println("Your Data is Sorted in Descending Order: ");
		for (int i = 0; i < value.length; i++) 
		{
			System.out.print(value[i] + " ");
		}
		System.out.println(" ");
		return value;
	}

	
	// Method to find the largest element in the array
	public int[] largest() 
	{
		int value[] = descending();  // Reusing the descending() method
		int largest = value[0];
		for (int i = 1; i < value.length; i++) 
		{
			if (value[i] > largest) 
			{
				largest = value[i];
			}
		}
		System.out.println("The Largest Element is: " + largest);
		return value;
	}

	
	// Method to find the smallest element in the array
	public void smallest() 
	{
		int value[] = largest();  // Reusing the largest() method
		int smallest = value[0];
		for (int i = 1; i < value.length; i++)
		{
			if (value[i] < smallest)
			{
				smallest = value[i];
			}
		}
		System.out.println("The Smallest Element is: " + smallest);
	}

	public static void main(String[] args)
	{
		Demo2 d = new Demo2();
		d.smallest();
	}
}
