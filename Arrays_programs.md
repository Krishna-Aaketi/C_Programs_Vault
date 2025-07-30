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
### Count number of Occurrence of each element 
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
