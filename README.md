# DSA


<img width="447" height="208" alt="image" src="https://github.com/user-attachments/assets/19f518b7-b90f-497d-9f8f-071c98b7dfdc" />
 O(n)
 
<img width="506" height="266" alt="image" src="https://github.com/user-attachments/assets/928ab661-2361-4eb2-962c-f20c8c016d5c" />
 O(logn)
 
<img width="515" height="245" alt="image" src="https://github.com/user-attachments/assets/ecc1d0a1-6586-42ab-8696-0acf121418c8" />
 O(logn)


```
Linear Search / Sequence Search
----------
Key point: array, length, key need to be search

using System;
using System.Reflection.Metadata.Ecma335;


class Program
{
   public static void Main()
    {
        int[] a = { 5, 20, 40, 4, 24 };
        int key = 24;
        int n = a.Length;
        int result = LinearSearch(a, n, key);
        Console.WriteLine(result);

    }

    public static int LinearSearch(int[] arr , int n , int key)
    {
         for(int i=0;i<n;i++)
        {
            if (arr[i] ==key)
            {
                 return i;
            }
        }
        return -1;
    }

}

Binary Search
---------------

Array Need to be in Sorted Order

find the middle of an element where  L=0 and R= n-1 M = (L+R)/2

using System;
using System.Reflection.Metadata.Ecma335;


class Program
{
   public static void Main()
    {
        int[] a = { 4,5,8,20,24,30 };
        int key = 5;
        int n = a.Length;
        int result = BinarySearch(a, n, key);
        Console.WriteLine(result);

    }

    public static int BinarySearch(int[] arr , int n , int key)
    {
        int L = 0;
        int R = n - 1;

        for(int i = L; i < n-1; i++)
        {
            int m = (L + R) / 2;

            if (key == arr[m])
                return m;

            else if (key < arr[m])
                R = m - 1;

            else
                L = m + 1;
        }

        return -1;
    }


}

Binary Search using Recursion
--------------------------------
// See https://aka.ms/new-console-template for more information
using System;
using System.Reflection.Metadata.Ecma335;


class Program
{
   public static void Main()
    {
        int[] a = { 4,5,8,20,24,30 };
        int key = 5;
        int n = a.Length;
        int L = 0;
        int R = n - 1;
        int result = BinarySearch(a, key, L,R);
        Console.WriteLine(result);

    }

    public static int BinarySearch(int[] arr , int key , int L,int R)
    {
            if (L > R)
                 return -1;
       
            int m = (L + R) / 2;
            if (key == arr[m])
                return m;
            if (key < arr[m])
              return  BinarySearch(arr, key, L, m - 1);

            else
              return  BinarySearch(arr, key, m + 1, R);       
    }
}




















```
