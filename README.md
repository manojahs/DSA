# DSA
```
Linear Search
----------

// See https://aka.ms/new-console-template for more information
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

```
}

