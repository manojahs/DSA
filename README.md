# DSA

<img width="502" height="211" alt="image" src="https://github.com/user-attachments/assets/f76e0533-7716-47e9-9288-ddbe78c8e7ee" />

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
        int ni = 0;
         for(int i=0;i<n;i++)
        {
            if (arr[i] ==key)
            {
                 ni=i;
            }
            else
            {
                return ni =-1;
            }

        }
        return ni;
    }

}

Binary Search
---------------

Array Need to be in Sorted Order






















```
