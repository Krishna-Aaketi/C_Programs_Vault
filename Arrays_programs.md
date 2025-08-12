### 01.find maximum value and minimum Value
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 01. Write a c  program to find maximum value and minimum    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int i=0,n=0,max,min;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  max=min=arr[0];
  for(i=0; i<n; i++)
  {
    if(max<=arr[i])
    {
      max=arr[i];
    }
    else if(min >= arr[i])
    {
      min=arr[i];
    }
  }
  printf("Maximum value=%d Minimum value=%d\n",max,min);
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :10 50 30 20 5
Maximum value=50 Minimum value=5
```
### 02. print substring in given array 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 02. Write a C program to print substring in given array     *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i,j,l=0,k=0,n;
  int arr[100],a[1000];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<n; i++)
  {
    j=i;
    while(j<(n-1))
    {
      a[k]=(arr[i] *10) + arr[j+1];
      printf("%d ",a[k]);
      j++;
      k++;
    }
  }
  printf("\n");

  for(i=0; i<n; i++)
  {
    j=i;
    while(j<(n-j))
    {
      a[k]=(a[l] *10) + arr[j+2];
      printf("%d ",a[k]);
      j++;
      k++;
      l++;
    }
    l++;
  }
  printf("\n");
  for(i=0; i<n-3; i++)
  {
    printf("%d ", arr[i]*1000 + arr[i+1]*100 + arr[i+2]*10 + arr[i+3]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 6
Enter Elements :1 2 3 4 5 6
12 13 14 15 16 23 24 25 26 34 35 36 45 46 56
123 124 125 126 134 135 136 145 146 156 234 235 236 245 246 256 345 346 356 456
1234 2345 3456
```
### 03. Reverse an Array in place
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 03. Write a C program to Reverse an Array in place          *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i=0,n=0,temp;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<=(n-i); i++)
  {
    temp=arr[i];
    arr[i]=arr[n-i-1];
    arr[n-i-1]=temp;
  }
  for(i=0;i<n; i++)
  {
    printf("%d ",arr[i]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :10 20 30 40 50
50 40 30 20 10
```
### 04. Remove duplicate elements in array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 04. Write a c program to remove duplicate elements in array *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>
#include<stdlib.h>

int main(void)
{
  int i=0,j=0,n=5,temp,a[100];
  int *arr;
  printf("Enter Number of elements: ");
  scanf("%d",&n);
  arr=malloc(sizeof(int)*n);
  if(arr==NULL)
  {
    printf("malloc is failed\n");
    return 0;
  }
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<n; i++)
  {
    for(j=1;j<n-i;j++)
    {
      if(arr[j-1]>=arr[j])
      {
        temp=arr[j];
        arr[j]=arr[j-1];
        arr[j-1]=temp;
      }
    }
  }
  a[0]=arr[0];
  j=1;
  for(i=0; i<n-1; i++)
  {
    if(arr[i] !=arr[i+1])
    {
      a[j]=arr[i+1];
      j++;
    }
  }
  for(i=0;i<j;i++)
  {
    printf("%d ",a[i]);
  }
  printf("\n");
  free(arr);
  return 0;
}
```
### Output 
```c
Enter Number of elements: 5
Enter Elements :1 2 3 2 1
1 2 3
```
### 05. Find second large number in array 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 05. Write a c program to find second large number in array  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int i=0,n=0,max,temp;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  max=temp=arr[0];
  for(i=0; i<n; i++)
  {
    if(arr[i] > max)
    {
      temp=max;
      max=arr[i];
    }
    else if(arr[i] > temp)
    {
      temp=arr[i];
    }
  }
  printf("Second large number=%d\n",temp);
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :1 3 6 9 2
Second large number=6
```
### 06. One left rotation in given array 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 06. Write a c program to one left rotation in given array   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int i=0,n=0,temp;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  temp=arr[0];
  for(i=0; i<n-1; i++)
  {
    arr[i]=arr[i+1];
  }
  arr[i]=temp;
  for(i=0;i<n; i++)
  {
    printf("%d ",arr[i]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :1 2 3 4 5
2 3 4 5 1
```
###  09.Right rotation with kth position in given array 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 09. Write a c program to right rotation with kth position in given array  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i=0,n=0,k=0,j=0,l=0;
  int arr[100],a[50];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  printf("Enter kth position:");
  scanf("%d",&k);
  if(n<k)
  {
    printf("K value is greaterthen n value\n");
    return 0;
  }
  i=0;
  while(i<k)
  {
    a[i]=arr[n-k+i];
    i++;
  }
  for(i=n-1; i >= k; i--)
  {
    arr[i]=arr[i-k];
  }
  i=0;
  while(i < k)
  {
    arr[i]=a[i];
    i++;
  }
  for(i=0;i<n; i++)
  {
    printf("%d ",arr[i]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :1 2 3 4 5
Enter kth position:3
3 4 5 1 2
```
### 10. Merge sorted array in given two array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 10. Write a c program to merge sorted array in given two array    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int i=0,n,m,j=0,temp;
  int arr1[200],arr2[100];
  printf("Enter Number of elements first Array(<100): ");
  scanf("%d",&n);
  if(n<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr1[i]);
  }
  printf("Enter Number of elements Second Array(<100): ");
  scanf("%d",&m);
  if(m<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0; i<m; i++)
  {
    scanf("%d",&arr2[i]);
  }
  for(i = n ; i < n+m ; i++)
  {
    arr1[i]=arr2[j];
    j++;
  }
  for(i=0 ; i < n+m; i++)
  {
    for(j=1; j <(n+m-i); j++)
    {
      if(arr1[j]<arr1[j-1])
      {
        temp=arr1[j];
        arr1[j]=arr1[j-1];
        arr1[j-1]=temp;
      }
    }
  }
  for(i = 0 ; i < n+m ; i++)
  {
    printf("%d ",arr1[i]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements first Array(<100): 5
Enter Elements :10 20 30 40 50
Enter Number of elements Second Array(<100): 5
Enter Elements :60 70 80 90 100
10 20 30 40 50 60 70 80 90 100
```
### 11.Check given array is sorted or not
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 11. Write a c program to Check given array is sorted or not       *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i=0,n,flag=0;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  if(n<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i = 0 ; i < n-1 ; i++)
  {
    if(arr[i]<=arr[i+1])
    {
      continue;
    }
    else
    {
      flag=1;
      break;
    }
  }
  if(flag)
  {
    printf("Given Array is not Sorted array\n");
  }
  else
  {
    printf("Given Array is Sorted array\n");
  }
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :1 2 3  4 5
Given Array is Sorted array
```
### 12. Even number is one side odd numbers is one side in array  
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 12. write a c program to even number is one side odd numbers is one side in array *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
#if 1
#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int arr[5];
  int num,i=0,j=0,k=0;
  int *ptr1,*ptr2;
  printf("Enter number of elements\n");
  scanf("%d",&num);
  printf("Enter elements\n");
  for(i=0;i<num;i++)
  {
   scanf("%d",&arr[i]);
  }
  ptr1=malloc(sizeof(int)*50);
  ptr2=malloc(sizeof(int)*50);
  i=0;
  while(i<5)
  {
    if(arr[i]%2==0)
    {
      ptr1[j]=arr[i];
      i++;
      j++;
    }
    else
    {
      ptr2[k]=arr[i];
      i++;
      k++;
    }
  }
  for(i=0;i<j;i++)
  {
    arr[i]=ptr1[i];
  }
  for(i=0;i<k;i++)
  {
    arr[j]=ptr2[i];
    j++;
  }
  for(i=0;i<5;i++)
  {
    printf("%d ",arr[i]);
  }
  printf("\n");
  free(ptr1);
  free(ptr2);
  return 0;
}
#endif
```
### Output
```c
Enter number of elements
5
Enter elements
10 13 15 16 17
10 16 13 15 17
```
### 13. Print largest element index in array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 13.write a c  program to print largest element index in array *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int i=0,j=0,n=0,temp;
  int arr[100];
  printf("Enter Number of elements: ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  temp=arr[0];
  j=i;
  for(i=0; i<n; i++)
  {
     if(temp<=arr[i])
     {
       temp=arr[i];
       j=i;
     }
  }
  printf("Index=%d\n",j);
  return 0;
}
```
### Output
```c
Enter Number of elements: 5
Enter Elements :10 40 50 20 15
Index=2
```
### 14. Odd occurring number when all other numbers occur an even number of times
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 14. write a c program to find the odd occurring number when all other numbers occur an even number of times *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int findOdd(int arr[], int n);

int main(void)
{
    int arr[100],odd,n,i;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    printf("Enter array elements: ");
    for (i = 0; i < n; i++)
    {
      scanf("%d", &arr[i]);
    }
    odd = findOdd(arr, n);
    printf("Odd occurring number is: %d\n", odd);
    return 0;
}

int findOdd(int arr[], int n)
{
  int res = 0,i;
  for (i = 0; i < n; i++)
  {
    res ^= arr[i];
  }
  return res;
}
```
### Output
```c
Enter number of elements: 5
Enter array elements: 2 3 2 3 3
Odd occurring number is: 3
```
### 15. Remove space in given string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 15. write a c program to remove space in given string   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int findOddOccurrence(int arr[], int size);
int main(void)
{
    //int arr[] = {4, 2, 4, 2, 7, 5, 5};
    //int size = sizeof(arr) / sizeof(arr[0]);
    int num,odd,arr[100],i;
    printf("Enter Number Elements\n");
    scanf("%d",&num);
    printf("Enter Elements\n");
    for(i=0;i<num;i++)
    {
      scanf("%d",&arr[i]);
    }
    odd = findOddOccurrence(arr, num);
    printf("The odd occurring number is: %d\n", odd);

    return 0;
}

int findOddOccurrence(int arr[], int size)
{
    int result = 0,i;
    for (i = 0; i < size; i++)
    {
        result ^= arr[i];
    }
    return result;
}
```
### Output
```c
Enter Number Elements
5
Enter Elements
10 11 11 12 13
The odd occurring number is: 11
```
### 16.Print unique array in given array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 16. write a c program to print unique array in given array  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int i=0,j=1,n=0,temp;
  int arr[100],a[50];
  printf("Enter Number of elements: ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<n; i++)
  {
    for(j=1;j<n-i;j++)
    {
      if(arr[j]<arr[j-1])
      {
        temp=arr[j];
        arr[j]=arr[j-1];
        arr[j-1]=temp;
      }
    }
  }
  a[0]=arr[0];
  for(i=0;i<n-1; i++)
  {
    if(arr[i]==arr[i+1])
    {
      continue;
    }
    else
    {
      a[j]=arr[i+1];
      j++;
    }
  }
  for(i=0;i<j;i++)
  {
    printf("%d ",a[i]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements: 6
Enter Elements :10 20 30 40 30 20
10 20 30 40
```
### 17. Rotate an array by 2 towards left
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 17. write a program to rotate an array by 2 towards left  *
 *  I/p:{1,2,3,4,5}                                          *
 *  o/p:{4,5,1,2,3}                                          *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>
int main(void)
{
    int arr[] = {1, 2, 3, 4, 5},n,d,i;
    n = sizeof(arr)/sizeof(arr[0]);
    d = 2; // number of positions to rotate
    rotateLeft(arr, n, d);
    printf("Rotated Array: ");
    for (i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");
    return 0;
}

void rotateLeft(int arr[], int n, int d)
{
    int temp[d],i;
    // Step 1: Copy first 'd' elements
    for (i = 0; i < d; i++)
        temp[i] = arr[i];
    // Step 2: Shift the rest of the elements to the left
    for (i = 0; i < n - d; i++)
        arr[i] = arr[i + d];
    // Step 3: Copy 'd' elements to the end
    for (i = 0; i < d; i++)
        arr[n - d + i] = temp[i];
    return 0;
}
```
### Output
```c
 I/p:{1,2,3,4,5}
 o/p:{4,5,1,2,3}

```
### 18. Count number of even and odd number in array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 18. Write a c program to Count number of even and odd number in array *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i=0,n,odd=0,even=0;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  if(n<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i = 0 ; i < n ; i++)
  {
    if(arr[i]%2 || arr[i]==1)
    {
      odd++;
    }
    else
    {
      even++;
    }
  }
  printf("Number of Even =%d and Odd =%d\n",even,odd);
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :10 13 15 16 18
Number of Even =3 and Odd =2
```
### 19.Find duplicate elements in given array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 19. Write a c program to find duplicate elements in given array   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i=0,n,j,temp=0;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  if(n<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i = 0 ; i < n ; i++)
  {
    for(j=i+1; j<n; j++)
    {
      if(arr[i]==arr[j] && temp != arr[i])
      {
        temp=arr[i];
        printf("%d ",arr[i]);
      }
    }
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :10 20 30 20 10
10 20
```
### 20. Print right to left Leads in Array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 20. Write a c program to print right to left Leads in Array *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>

int main(void)
{
  int i=0,n=0,temp;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  if(n<=0)
  {
    printf("Enter Positive Number\n");
    return 0;
  }
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  temp=arr[n-1];
  printf("%d ",temp);
  for(i=n-1; i >=0; i--)
  {
    if(temp<arr[i])
    {
      temp=arr[i];
      printf("%d ",temp);
    }
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 6
Enter Elements :1 3 5 6 -1 -5
-5 -1 6
```
### 21. Print Common elements in given arrays 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 21. Write a c program to print Common elements in given arrays    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i=0,n,m,j=0,temp,k=0,z,flag=1;
  int arr1[100],arr2[100],pri[100];
  printf("Enter Number of elements first Array(<100): ");
  scanf("%d",&n);
  if(n<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr1[i]);
  }
  printf("Enter Number of elements Second Array(<100): ");
  scanf("%d",&m);
  if(m<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0; i<m; i++)
  {
    scanf("%d",&arr2[i]);
  }
  printf("Common Elements are:");
  for(i = 0 ; i < n ; i++)
  {
    for(j=0; j<m; j++)
    {
      if(arr1[i]==arr2[j])
      {
        temp=1;
        flag=0;
        for(z=0; z<k; z++)
        {
          if(pri[z]==arr1[i])
          {
            temp=0;
          }
        }
        if(temp)
        {
          printf("%d ",arr1[i]);
          pri[k++]=arr1[i];
        }
      }
    }
  }
  printf("\n");
  if(flag)
  {
    printf("NO Common elments\n");
  }
  return 0;
}
```
###
```c
Enter Number of elements first Array(<100): 5
Enter Elements :1 2 3 4 5
Enter Number of elements Second Array(<100): 5
Enter Elements :1 -2 3 -4 -5
Common Elements are:1 3
```
### 22. Find Missing 1 to n between Number in Array 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 22. Write a c program to Find Missing 1 to n between Number in Array    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i=0,n,temp=0;
  int arr[100];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  if(n<=0)
  {
    printf("Enter Positive Values\n");
    return 1;
  }
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  temp;
  for(i = 0 ; i < n ; i++)
  {
    if(temp==arr[i])
    {
      temp++;
    }
    else
    {
      printf("The Missing Number is %d ",temp);
      temp++;
      --i;
    }
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter Number of elements(<100): 6
Enter Elements :1 3 5 7 9 10
The Missing Number is:2 4 6 8
```
### 23.Count number of Occurrence of each element 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 23. Write a c program to count number of Occurrence of each element   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int arr[100],a[100]={0};
  int i=0,j=0,count=0,n;
  printf("Enter number of elements(<99): ");
  scanf("%d", &n);
  printf("Enter array elements: ");
  for (i = 0; i < n; i++)
  {
    scanf("%d", &arr[i]);
  }
  for( i = 0; i < n; i++)
  {
    if(a[i]==1)
    {
      continue;
    }
    count=1;
    for(j=i+1;j<n;j++)
    {
      if(arr[i]==arr[j])
      {
        count++;
        a[j]=1;
      }
    }
    printf("%d is %d times occurred\n",arr[i],count);
  }
  return 0;
}
```
### Output
```c
Enter number of elements(<99): 5
Enter array elements: 1 2 3 2 1
1 is 2 times occurred
2 is 2 times occurred
3 is 1 times occurred
```
### 24. Move zeros into one side in given array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 24. Write a c program to move zeros into one side in given array      *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int arr[100];
  int i=0,j=0,count=0,n;
  printf("Enter number of elements(<99): ");
  scanf("%d", &n);
  if(n<1)
  {
    printf("please Enter Positive Numbers\n");
    return 0;
  }
  printf("Enter array elements: ");
  for (i = 0; i < n; i++)
  {
    scanf("%d", &arr[i]);
  }
  for( i = 0; i < n-count; i++)
  {
    if(arr[i]==0)
    {
      count++;
      for(j=i;j<n-1;j++)
      {
        arr[j]=arr[j+1];
      }
      i--;
      arr[n-1]=0;
    }
  }
  for(j=0;j<n;j++)
  {
    printf("%d ",arr[j]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter number of elements(<99): 10
Enter array elements: 1 0 2 0 3 0 4 0 5 0
1 2 3 4 5 0 0 0 0 0
```
### 25. Find pair given sum in given array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 25. Write a C program to find pair given sum in given array       *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int arr[100],sum=0,i=0,j=0,n=0;
  printf("Enter Number of Element(100):");
  scanf("%d",&n);
  if(n<1)
  {
    printf("Enter positive Number\n");
    return 0;
  }
  printf("Enter Element:");
  for(i=0; i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  printf("Enter Sum value:");
  scanf("%d",&sum);
  for(i=0; i<n-1; i++)
  {
    for(j=i+1; j<n; j++)
    {
      if((arr[i]+arr[j])== sum)
      {
        printf("the first pair is (%d,%d)\n",arr[i],arr[j]);
        return 0;
      }
    }
  }
  return 0;
}
```
### Output
```c
Enter Number of Element(100):5
Enter Element:1 2 3 4 5
Enter Sum value:4
the first pair is (1,3)
```
### 26. Find union and interset in given two arrays
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 26. Write a c program to find union and interset in given two arrays  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int arr1[100], arr2[100], uni[200], inter[100];
  int m, n, i, j, k = 0,x, count = 0,found;
  printf("Enter number of elements in arr1: ");
  scanf("%d", &m);
  if (m < 1)
  {
    printf("Enter positive size\n");
    return 0;
  }
  printf("Enter %d elements for arr1: ", m);
  for (i = 0; i < m; i++)
  {
    scanf("%d", &arr1[i]);
  }
  printf("Enter number of elements in arr2: ");
  scanf("%d", &n);
  if (n < 1)
  {
    printf("Enter positive size\n");
    return 0;
  }
  printf("Enter %d elements for arr2: ", n);
  for (i = 0; i < n; i++)
  {
    scanf("%d", &arr2[i]);
  }
  for (i = 0; i < m; i++)
  {
    uni[k++] = arr1[i];
  }
  for (i = 0; i < n; i++)
  {
    found = 0;
    for(j = 0; j < k; j++)
    {
      if(arr2[i] == uni[j])
      {
        found = 1;
        break;
      }
    }
    if(!found)
    {
       uni[k++] = arr2[i];
    }
  }
  for(i = 0; i < m; i++)
  {
    for(j = 0; j < n; j++)
    {
      if(arr1[i] == arr2[j])
      {
        found = 0;
        for(x = 0; x < count; x++)
        {
          if (inter[x] == arr1[i])
          {
            found = 1;
            break;
          }
        }
        if(!found)
        {
          inter[count++] = arr1[i];
          break;
        }
      }
    }
  }
  printf("\nUnion: ");
  for (i = 0; i < k; i++)
  {
    printf("%d ", uni[i]);
  }
  printf("\nIntersection: ");
  for(i = 0; i < count; i++)
  {
    printf("%d ", inter[i]);
  }
  printf("\n");
  return 0;
}

```
### Output
```c
Enter number of elements in arr1: 6
Enter 6 elements for arr1: 1 2 3 4 5 6
Enter number of elements in arr2: 5
Enter 5 elements for arr2: 0 6 7 8 5

Union: 1 2 3 4 5 6 0 7 8
Intersection: 5 6
```
### 27. Sort Binary array (0s,1s) in one pass 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 27. Write a C program to sort Binary array (0s,1s) in one pass    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int arr[100],n,i=0,j=0,temp=0;
  printf("Enter number of Elements:");
  scanf("%d",&n);
  printf("Enter  Elements:");
  for( i = 0; i < n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<n; i++)
  {
    for(j=1; j<n; j++)
    {
      if(arr[j-1] >arr[j])
      {
        temp=arr[j];
        arr[j]=arr[j-1];
        arr[j-1]=temp;
      }
    }
  }
  for(i=0; i<n; i++)
  {
    printf("%d ",arr[i]);
  }
  printf("\n");
  return 0;
}
```
### Output
```c
Enter number of Elements:8
Enter  Elements:1 0 1 0 1 0 1 0
0 0 0 0 1 1 1 1
```
### 28. 
```c

```
### 29. Print the elements of a 2D matrix in spiral order
```c

/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 29. Write a c program to print the elements of a 2D matrix in spiral order  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
#if 0

#include<stdio.h>
#define row 4
#define col 4

int main(void)
{
  int matrix[row][col],i=0,j=0,k,l;
  printf("Enter the elements:\n");
  for(int i=0;i<row;i++)
  {
    for(int j=0;j<col;j++)
    {
      scanf("%d",&matrix[i][j]);
    }
  }
  printf("2D matrix in spiral order:");
  while(i==0 && j!=col )
  {
    printf("%d->",matrix[i][j]);
    j++;
  }
  j--;
  i++;
  while(i<=row-1)
  {
    printf("%d->",matrix[i][j]);
    i++;
  }
  i--;
  j--;
  while(j>=0)
  {
    printf("%d->",matrix[i][j]);
    j--;
  }
  j++;
  i--;
  while(i>=1)
  {
    printf("%d->",matrix[i][j]);
    i--;
  }
  i++;
  j++;
  while(j!=col-1)
  {
    printf("%d->",matrix[i][j]);
    j++;
  }
  j--;
  i++;
  while(j!=0)
  {
    if(j==1)
    {
      printf("%d\n",matrix[i][j]);
    }
    else
    {
      printf("%d->",matrix[i][j]);
    }
    j--;
  }
}
#endif

#if 1

#include <stdio.h>

#define MAX 100

int main(void)
{
  int matrix[MAX][MAX];
  int row, col;
  printf("Enter number of rows and columns (max %d): ", MAX);
  scanf("%d%d", &row, &col);
  if(row <= 0 || col <= 0 || row > MAX || col > MAX)
  {
    printf("Invalid dimensions!\n");
    return 1;
  }
  // Input matrix elements
  printf("Enter %d elements:\n", row * col);
  for(int i = 0; i < row; i++)
  {
    for(int j = 0; j < col; j++)
    {
      scanf("%d", &matrix[i][j]);
    }
  }
  // Spiral traversal
  int top = 0, bottom = row - 1;
  int left = 0, right = col - 1;
  printf("Spiral order");
  while(top <= bottom && left <= right)
  {
    for(int i = left; i <= right; i++)
    {
      printf("->");
      printf("%d", matrix[top][i]);
    }
    top++;
    for(int i = top; i <= bottom; i++)
    {
      printf("->");
      printf("%d", matrix[i][right]);
    }
    right--;
    if(top <= bottom)
    {
      for(int i = right; i >= left; i--)
      {
        printf("->");
        printf("%d", matrix[bottom][i]);
      }
      bottom--;
    }
    if(left <= right)
    {
      for (int i = bottom; i >= top; i--)
      {
        printf("->");
        printf("%d",matrix[i][left]);
      }
      left++;
    }
  }
  return 0;
}

#endif
```
### Output
```c
Enter the elements:
1  2  3  4
5  6  7  8
9  10 11 12
13 14 15 16
Spiral order:1->2->3->4->8->12->16->15->14->13->9->5->6->7->11->10
```
### 30. Find Most majority element in given array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 30. Write a C program to find Most majority element in given array  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int arr[100],i=0,count=0,temp=0,k=0,j=0,num=0;
  printf("Enter Number of Elements:\n");
  scanf("%d",&num);
  if(num<=0)
  {
    printf("Enter Positive Numbers only\n");
    return 0;
  }
  printf("Enter Elements:\n");
  for(i=0; i<num; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<num; i++)
  {
    if(arr[i]==arr[k] && i != 0)
    {
      continue;
    }
    for(j=i+1; j<num; j++)
    {
      if(arr[i]==arr[j])
      {
        count++;
      }
    }
    if(temp<count)
    {
      temp=count;
      k=i;
    }
  }
  printf("The most mojority Element %d is repeated in %d times\n",arr[k],++temp);
  return 0;
}
```
### Output
```c
Enter Number of Elements:
6
Enter Elements:
1 1 1 2 3 2
The most mojority Element 2 is repeated in 4 times
```
### 31. Rotate Given Array Using Reversal Algorithm
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 31. Write a c program to Rotate Given Array Using Reversal Algorithm      *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

void reverse(int arr[], int start, int end);

int main(void)
{
  int i=0,n=0,k=0,j=0;
  int arr[100],a[50];
  printf("Enter Number of elements(<100): ");
  scanf("%d",&n);
  printf("Enter Elements :");
  for(i=0;i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  printf("Enter kth position:");
  scanf("%d",&k);
  if(n<k)
  {
    printf("K value is greaterthen n value\n");
    return 0;
  }
  // Step 1: Reverse first k elements
  reverse(arr, 0, k - 1);

  // Step 2: Reverse remaining n-k elements
  reverse(arr, k, n - 1);

  // Step 3: Reverse entire array
  reverse(arr, 0, n - 1);
  for(i=0;i<n; i++)
  {
    printf("%d ",arr[i]);
  }
  printf("\n");
  return 0;
}

void reverse(int arr[], int start, int end)
{
  while(start < end)
  {
    int temp = arr[start];
    arr[start] = arr[end];
    arr[end] = temp;
    start++;
    end--;
  }
}
```
### Output
```c
Enter Number of elements(<100): 5
Enter Elements :1 2 3 4 5
Enter kth position:3
3 4 5 1 2
```
### 32. Find Maximum subarray sum using kadane's algorithm 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 32. Write a c program to  find Maximum subarray sum using kadane's algorithm  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int kadane(int arr[], int n);

int main(void)
{
  int t,n=0,i=0,arr[100];
  printf("Enter Number of elements:");
  scanf("%d", &n);
  printf("Enter %d elements: ", n);
  for(i = 0; i < n; i++)
  {
    scanf("%d", &arr[i]);
  }
  printf("Maximum Subarray Sum = %d\n", kadane(arr, n));
  return 0;
}

int kadane(int arr[], int n)
{
  int max = arr[0];
  int i=0,curr_max = arr[0];
  for(i=1; i<n;i++)
  {
    curr_max = (arr[i] > curr_max + arr[i]) ? arr[i] : curr_max + arr[i];
    max = (max > curr_max) ? max : curr_max;
  }
  return max;
}
```
### Output
```c
Enter Number of elements:6
Enter 6 elements: -1 -2 -3 -4 5 6
Maximum Subarray Sum = 11
```
### 33. Search element in rotated sorted array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 33. Write a C program to Search element in rotated sorted array   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int arr[100],num=0,i=0,target=0;
  printf("Enter Number of Elements:");
  scanf("%d",&num);
  printf("Enter Elements:");
  for(i=0;i<num;i++)
  {
    scanf("%d",&arr[i]);
  }
  printf("Enter Target Elements:");
  scanf("%d",&target);
  for(i=0;i<num; i++)
  {
    if(arr[i]==target)
    {
      printf("The Index of Target Element is %d\n",i);
      break;
    }
  }
  return 0;
}
```
### Output
```c
Enter Number of Elements:6
Enter Elements:1 3 6 9 5 7
Enter Target Elements:9
The Index of Target Element is 3
```
### 34. Find maximum diff between two elements
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 34. Write a c program to find maximum diff between two elements   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int arr[50],i=0,max,min,num;
  printf("Enter Number of Elements:");
  scanf("%d",&num);
  printf("Enter Elements:");
  for(i=0; i<num; i++)
  {
    scanf("%d",&arr[i]);
  }
  max=min=arr[0];
  for(i=0;i<num;i++)
  {
    if(max<arr[i])
    {
      max=arr[i];
    }
    else if(min<arr[i])
    {
      min=arr[i];
    }
  }
  printf("Maximum difference Between (%d-%d)=%d\n",max,min,(max-min));
  return 0;
}
```
### Output
```c
Enter Number of Elements:6
Enter Elements:-1 2 4 6 8 10
Maximum difference Between (10--1)=11
```
