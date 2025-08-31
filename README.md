# DSA


<img width="447" height="208" alt="image" src="https://github.com/user-attachments/assets/19f518b7-b90f-497d-9f8f-071c98b7dfdc" />

 
<img width="506" height="266" alt="image" src="https://github.com/user-attachments/assets/928ab661-2361-4eb2-962c-f20c8c016d5c" />

 
<img width="515" height="245" alt="image" src="https://github.com/user-attachments/assets/ecc1d0a1-6586-42ab-8696-0acf121418c8" />

<img width="519" height="283" alt="image" src="https://github.com/user-attachments/assets/bc464c1f-069f-4f4b-a466-1faf9cba8b94" />

<img width="518" height="268" alt="image" src="https://github.com/user-attachments/assets/e947ab76-e6fb-4987-b268-4ac6f2bf8019" />

<img width="526" height="244" alt="image" src="https://github.com/user-attachments/assets/c681bcf3-c269-4544-89f4-63bfff2593ae" />

<img width="506" height="248" alt="image" src="https://github.com/user-attachments/assets/93845748-143b-4327-a192-ac8c392bc578" />

<img width="521" height="290" alt="image" src="https://github.com/user-attachments/assets/2cc4baf4-992c-47c0-8c7c-00a69ab168af" />

<img width="518" height="283" alt="image" src="https://github.com/user-attachments/assets/0b0d0085-d6e7-43c1-9c8e-cdf1f1dced31" />





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

        for(int i = 0; i < n-1; i++)
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

Sorting Algo
---------
 1) Selection Sort (Unstable algo)
Finding the smallest element in array and place it in first element then look for another small value in remaining array and soon


using System;

class Program
{

    public void SelectionSort(int[] a, int n)
    {
        for(int i=0;i<n-1;i++)
        {
            int pos = i;
            for (int j=i+1; j<n; j++)
            {
                if (a[pos] > a[j])
                {
                    pos = j;
                    int temp = a[i];
                    a[i] = a[pos];
                    a[pos] = temp;
                }
            }
        }
    }

    public void Display(int[] a ,int n)
    {
        for(int i =0;i<n;i++)
        {
            Console.Write(a[i] + " ");
        }
        Console.WriteLine();
    }

    static void Main(string[] args)
    {
        Program p = new Program();
        int[] a = { 4, 2, 5, 6, 1,10,0,3 };
        Console.WriteLine("Orig Array");
        p.Display(a, a.Length);
        p.SelectionSort(a, a.Length);
        Console.WriteLine("sorted Array");
        p.Display(a, a.Length);
        Console.ReadKey();
    }
}

//insertion sort
---------------------

using System;

class Program
{

    public void InsertionSort(int[] a, int n)

    {
        for(int i=1;i<n;i++)
        {
            int cValue = a[i];
            int pos = i;
            while(pos>0 && a[pos-1]>cValue)
            {
                a[pos] = a[pos - 1];
                pos--;
                a[pos] = cValue;
            }
        }
    }

    public void Display(int[] a ,int n)
    {
        for(int i =0;i<n;i++)
        {
            Console.Write(a[i] + " ");
        }
        Console.WriteLine();
    }

    static void Main(string[] args)
    {
        Program p = new Program();
        int[] a = { 4, 2, 5, 6, 1,10,0,3 };
        Console.WriteLine("Orig Array");
        p.Display(a, a.Length);
        p.InsertionSort(a, a.Length);
        Console.WriteLine("sorted Array");

        p.Display(a, a.Length);
        Console.ReadKey();
    }
}


//Bubble Sort
---------------

using System;
using System.Runtime.CompilerServices;

class Program
{

    public void BubbleSort(int[] a, int n)

    {
        for(int i=n-1;i>=0;i--)
        {
            for(int j=0;j<i;j++)
            {
                if (a[j] > a[j+1])
                {
                    int temp = a[j];
                    a[j] = a[j + 1];
                    a[j + 1] = temp; 
                }
            }
          
        }
    }

    public void Display(int[] a ,int n)
    {
        for(int i =0;i<n;i++)
        {
            Console.Write(a[i] + " ");
        }
        Console.WriteLine();
    }

    static void Main(string[] args)
    {
        Program p = new Program();
        int[] a = { 4, 2, 5, 6, 1 };
        Console.WriteLine("Orig Array");
        p.Display(a, a.Length);
        p.BubbleSort(a, a.Length);
        Console.WriteLine("sorted Array");

        p.Display(a, a.Length);
        Console.ReadKey();
    }
}

// Merge Sort
--------------------
using System;
using System.Runtime.CompilerServices;

class Program
{

    public void MergeSortAlgo(int[] a, int left,int right)

    {
        if(left<right)
        { 
        int mid = (left + right) / 2;
        MergeSortAlgo(a, left, mid);
        MergeSortAlgo(a, mid + 1, right);
        MergeSort(a, left, mid, right);
        }
    }

    public void MergeSort(int[] a ,int left,int mid,int right)
    {
        int i =left, 
        j=mid+1,k;
         k = i;

        int[] b = new int[a.Length];

        while(i<=mid && j<=right)
        {
            if (a[i] < a[j])
            {
                b[k] = a[i];
                i++;
            }
            else
            {
                b[k] = a[j];
                j++;
            }
            k++;

        }
        while(i<=mid)
        {
            b[k] = a[i];
            i++;
            k++;
        }
        while(j<=right)
        {
            b[k] = a[j];
            j++;
            k++;
        }

        for(int x = left;x<right+1;x++)
        {
            a[x] = b[x];
        }



    }

    public void Display(int[] a, int n)
    {
        for (int i = 0; i < n; i++)
        {
            Console.Write(a[i] + " ");
        }
        Console.WriteLine();
    }

    static void Main(string[] args)
    {
        Program p = new Program();
        int[] a = { 4, 2, 5, 6, 1 };
        Console.WriteLine("Orig Array");
        p.Display(a, a.Length);
        p.MergeSortAlgo(a, 0, a.Length-1);
        Console.WriteLine("sorted Array");

        p.Display(a, a.Length);
        Console.ReadKey();
    }
}

 
//Quick Sort
-----------------


using System;

class Program
{
    public static void QuickSort(int[] arr, int low, int high)
    {
        if (low < high)
        {
            int pi = Partition(arr, low, high);

            // Recursively sort elements before and after partition
            QuickSort(arr, low, pi - 1);
            QuickSort(arr, pi + 1, high);
        }
    }

    private static int Partition(int[] arr, int low, int high)
    {
        int pivot = arr[low]; // 👈 pivot is the FIRST element
        int i = low + 1;
        int j = high;

        while (true)
        {
            // Move i forward until finding an element >= pivot
            while (i <= j && arr[i] <= pivot) i++;

            // Move j backward until finding an element <= pivot
            while (i <= j && arr[j] >= pivot) j--;

            if (i <= j)
            {
                Swap(arr, i, j);
            }
            else
            {
                break;
            }
        }

        // Place pivot in correct position
        Swap(arr, low, j);

        return j; // return pivot index
    }

    private static void Swap(int[] arr, int i, int j)
    {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    static void Main(string[] args)
    {
        int[] numbers = { 64, 25, 12, 22, 11, 90, 5 };

        Console.WriteLine("Original Array: " + string.Join(", ", numbers));

        QuickSort(numbers, 0, numbers.Length - 1);

        Console.WriteLine("Sorted Array: " + string.Join(", ", numbers));
    }
}















```
