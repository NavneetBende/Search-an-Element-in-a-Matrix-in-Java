Search an element in a matrix in Java
Here, in this page we will discuss the program to print the spiral traversal of the matrix in Java programming language. We’re given a n x n matrix and the value of the element in the matrix that needs to be found.
If the searched element is present in the matrix, we must find its position.
Otherwise, “Not Found” must be printed.
Every row and column in the specified matrix is sorted in ascending order.

Search an element in a matrix in Java
Method discussed :
Method 1 : Using Brute force.
Method 2 : Using DFS
Method 1 :
Run a nested for loop that iterates over the matrix
Compares the current value to the searched value.
If it is, print its location and set the value of flag to 1 before exiting the loop.
If flag becomes 1, the outer loop will be broken as well.
If flag==0 after exiting the nested loop, then print “Not Found.”
Method 1 : Code in Java
Run
import java.io.*;
import java.util.*;
 
class Main {
    public static void main(String[] args)
    {
        int a[][] = {{0,1,12,3}, {4,5,6,7}, {8,9,10,11}};;
        
        int size = 4;
        int search = 6;
        int flag=0;

        for(int i=0; i<size; i++){

            for(int j=0; j<size; j++){
                if(a[i][j]==search){
                    System.out.println("Element is found at ("+ i+", "+ j +") position");
                    flag=1;
                    break;
                }
            }

            if(flag==1)
            break;
        }

        if(flag==0)
            System.out.println("Not found");
    }
}
Output
Element is found at (1, 2) position
Method 2 :
Run a loop  that will terminate when i>n
Now, If the current element is greater than x then decrease the count of j. Exclude the current column.
And If the current element is less than x then increase the count of i. Exclude the current row.
If the element is equal, then print the position, set flag = 1 and break the loop.
After coming out from the loop, if flag==0 then print “Not Found”
Method 2 : Code in Java
Run
import java.io.*;
import java.util.*;
 
class Main {
    public static void main(String[] args)
    {
        int a[][] = {{0,1,12,3}, {4,5,6,7}, {8,9,10,11}};;
        
        int x = 6;
        int flag=0;

        int i=0, j=3;
  
        while (i < 3 && j >= 0)
        {
            if (a[i][j] == x)
            {
                System.out.println("Element is found at ("+ i+", "+ j +") position");
                flag=1;
                break;
            }
            
            if (a[i][j] > x)
                j--;
            else
                i++;
        }

        if(flag==0)
            System.out.println("Not found");
    }
}
Output
Element is found at (1, 2) position
