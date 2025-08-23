# DSA

<img width="502" height="211" alt="image" src="https://github.com/user-attachments/assets/f76e0533-7716-47e9-9288-ddbe78c8e7ee" />
<img width="533" height="285" alt="image" src="https://github.com/user-attachments/assets/3fec099c-f026-493b-b848-691072a32490" />
<img width="517" height="248" alt="image" src="https://github.com/user-attachments/assets/a66b21c7-b78d-4902-8a9d-04f554cb89d7" />


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






















```
