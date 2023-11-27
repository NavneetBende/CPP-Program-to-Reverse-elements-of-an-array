# CPP-Program-to-Reverse-elements-of-an-array

Reverse elements of an Array in C++
Here, in this page we will discuss the program to reverse elements of an Array in C++ Programming language. We are given with an array and need to reverse that array. WE will discuss various approaches to reverse the array.

Reverse elements of an array in C++
Method Discussed :
Method 1: Printing array in reverse order.
Method 2: In-place reversing of the original array
Method 3: Recursive in-place reversing of the original array
Method 4 : Using inbuilt function
 
Method 1 (Simple Printing Array in Reverse):
Objective: Reverse array in C++

Run a loop in reverse order i.e, from index n-1 to index 0.
Print i-th element
 
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(1)
Method 1 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int arr[] = {10, 20, 30, 40, 50};
   int n = sizeof(arr)/sizeof(arr[0]);

   for(int i=n-1; i>=0; i--)
      cout<<arr[i]<<" ";
}
Output
50 40 30 20 10
Method 2 (In-Place Reversal):
Take two variables say i = 0 and j = n – 1.
Run a loop till i < j
swap(arr[i],  arr[j])
Increment i and decrement the j
Now, Print the array
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(1)
Reverse elements of an array in C++ Example 2 new
Method 2 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int arr[] = {10, 20, 30, 40, 50};
   int n = sizeof(arr)/sizeof(arr[0]);

   int start = 0, end = n-1;

    while(start < end){
        swap(arr[start++], arr[end--]);
    }

    for(int i=0; i<n; i++)
       cout << arr[i] << " ";
}
Output
50 40 30 20 10
While loop in C
Related Pages
Find Second Smallest Element in an Array

Calculate the sum of elements in an array

Sort first half in ascending order and second half in descending 

Sort the elements of an array

Finding the frequency of elements in an array

Method 3 (Recursive):
Take variables, start = 0 and end = len – 1
Function gets called as reverseRecursive(arr, 0, len-1);
In each recursive iteration swap arr[start] & arr[end]
Make further recursive calls as reverseRecursive(arr, start + 1, end – 1);
return when (start >= end)
Print the array
Time and Space Complexity :
Time – Complexity : O(n)
Space-Complexity : O(n), require stack to store the recursive calls.
Reverse elements of an array in C++
Method 3 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

void reverseRecursive(int arr[], int start, int end)
{
   if (start >= end)
      return;

   int temp = arr[start];
   arr[start] = arr[end];
   arr[end] = temp;

   // recursive call to swap arr[start+1] & arr[end-1]
   reverseRecursive(arr, start + 1, end - 1);
}

int main(){

  int arr[] = {10, 20, 30, 40, 50};
  int n = sizeof(arr)/sizeof(arr[0]);

  reverseRecursive(arr, 0, n-1);

  for(int i=0; i<n; i++)
    cout<<arr[i]<<" ";
}
Output
50 40 30 20 10
Method 4 :
In this method we will use inbuilt reverse function to reverse the array.

reverse() is a predefined function in header file algorithm. 
It reverses the order of the elements in the range [first, last) of any container.
Time and Space Complexity :
Time – Complexity : O(n)
Space-Complexity : O(1)
Reversing array in C++
Method 4 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int arr[] = {10, 20, 30, 40, 50};
   int n = sizeof(arr)/sizeof(arr[0]);

   reverse(arr, arr+n);

   for(int i=0; i<n; i++)
      cout<<arr[i]<<" ";
}
Output
50 40 30 20 10
