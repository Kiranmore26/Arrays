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
		int temp;
		int value[] = accept();
		System.out.println("Your Data is Sorted in Ascending Order: ");
		for (int i = 0; i < value.length; i++) 
		{
			for(int j=0+i;j<value.length;j++)
			{
				if(value[i]>value[j])
				{
					//swapping of numbers
					temp=value[i];
					value[i]=value[j];
					value[j]=temp;
				}
			}
			System.out.print(value[i]+" ");
		}
		System.out.println(" ");
		return value;
	}

	
	// Method to sort an array in descending order
	public int[] descending()
	{
		int temp;
		int value[] = ascending();  // Reusing the ascending() method
		System.out.println("Your Data is Sorted in Descending Order: ");
		for (int i = 0; i < value.length; i++) 
		{
			for(int j=0+i;j<value.length;j++)
			{
				if(value[i]<value[j])
				{
					//swapping of numbers
					temp=value[i];
					value[i]=value[j];
					value[j]=temp;
				}
			}
			System.out.print(value[i]+" ");
		}
		System.out.println(" ");
		return value;
	}

	
	// Method to find the largest element in the array
	public int[] largest() 
	{
		int value[] = descending();  // Reusing the descending() method
		int largest = value[0];
		for (int i = 0; i < value.length; i++) 
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
		for (int i = 0; i < value.length; i++)
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

