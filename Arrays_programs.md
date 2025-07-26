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
###
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
