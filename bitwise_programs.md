## ------------------------------Bitwise Programs-----------------------------

### 01. Check given number is even or odd   
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 
 * 01.write a c program to check given number is even or odd *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,bit;
    printf("Enter Number:");
    scanf("%d",&num);
    if(num & 1)
    {
      printf("Number is odd\n");
    }
    else
    {
      printf("Number is even\n");
    }
    return 0;
}
```
### 02. Swap two numbers without using a temporary variable.
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 
 * 02.write a c program to Swap two numbers without using a temporary variable.      *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int a,b;
    printf("Enter a,b:");
    scanf("%d %d",&a,&b);
    a= a | b;
    b= b ^ a;
    a= a ^ b;
    printf("a=%d b=%d\n",a,b);
    return 0;
}
```  
### 03. Multiply or divide a number by 2
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 03.write a c program Multiply or divide a number by 2 using bitwise shift.*
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,op=0;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter 1 for mulitiply:");
  printf("\nEnter 2 for division:\n");
  scanf("%d",&op);
  switch(op)
  {
    case 1:
      printf("Given number Multiple by 2=%d\n",(num<<1));
      break;
    case 2:
      printf("Given number Divisible by 2=%d\n",(num>>1));
      break;
    default:
      printf("Enter valid number(1 or 2)");
  }
  return 0;
}

```  
### 04. Count number of bits in give number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 04. write a c program count number of bits in give number   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
#if 1
#include <stdio.h>

int main(void)
{
    int num,count=0;
    printf("Enter Number:");
    scanf("%d",&num);
    while(num)
    {
      if(num & 1)
      {
        count++;
      }
      num >>=1;
    }
    printf("number of set bits=%d\n",count);
    return 0;
}
#endif
#if 0
#include <stdio.h>

int main(void)
{
    int num,count=0,i;
    printf("Enter Number:");
    scanf("%d",&num);
    for(i=0; i<32; i++)
    {
      if((1<<i)& num)
      {
        count++;
      }
    }
    printf("number of bits=%d\n",count);
    return 0;
}
#endif
```  
### 05. Check if the k-th bit is set in a number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 5.write a c program to check if the k-th bit is set in a number.  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,k;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter k value:\n");
  scanf("%d",&k);
  if(((1 << k ) & num) == 0)
    printf("Kth Bit is not set\n");
  else
    printf("Kth Bit is set\n");
  return 0;
}
```  
### 06. Set the k-th bit of a number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 6.write a C program to Set the k-th bit of a number.    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,k;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter k value:\n");
  scanf("%d",&k);
  num |= (1 << k ) ;
  printf("number of set bits=%d\n",num);
  return 0;
}
```  
### 07. Reset the k-th bit of a number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 07.write a C program to reset the k-th bit of a number. *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,k;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter k value:\n");
  scanf("%d",&k);
  num &= ~(1 << k ) ;
  printf("number of set bits=%d\n",num);
  return 0;
}
```  
### 8. Toggle the k-th bit of a number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 8.write a C program to toggle the k-th bit of a number. *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,k;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter k value:\n");
  scanf("%d",&k);
  num ^= (1 << k ) ;
  printf("number of set bits=%d\n",num);
  return 0;
}
```  
### 9.Check power of 2 or not in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 9.write a c program to check power of 2 or not in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,bit=0;
    printf("Enter Number:");
    scanf("%d",&num);
    bit= ((num !=0) && (num & (num-1)));
    if(bit == 1)
    {
      printf("Given number is not power of 2\n");
    }
    else
    {
      printf("Given number is power of 2\n");
    }
    return 0;
}
```  
### 10. Turn off most right Bit in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 10.write a c program to turn off most right Bit in given number *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,i=0,temp;
    printf("Enter Number:");
    scanf("%d",&num);
    temp=num;
    while(temp)
    {
      if(temp & 1)
      {
        num &= ~ (1 << i);
        break;
      }
      temp >>= 1;
      i++;
    }
    printf("i=%d\n",i);
    printf("After Turnoff Right Most Bit Value=%d\n",num);
    return 0;
}
```  
### 11. Isolate right most bit in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 11.write a C program to isolate right most bit in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,i=0,temp;
    printf("Enter Number:");
    scanf("%d",&num);
    temp=num;
    while(temp)
    {
      if(temp & 1)
      {
        num &= (1 << i);
        break;
      }
      temp >>= 1;
      i++;
    }
    printf("i=%d\n",i);
    printf("After Isolate Right Most Bit Value=%d\n",num);
    return 0;
}
```  
### 12. Turnoff most left bit in given number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 12.write a c program to turn off most left bit in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,i=0,temp;
    printf("Enter Number:");
    scanf("%d",&num);
    temp=num;
    while(temp >>= 1)
    {
      i++;
    }
    num &= ~ (1 << i);
    printf("i=%d\n",i);
    printf("After Turnoff left Most Bit Value=%d\n",num);
    return 0;
}
```  

### 1.Assign value between m to n bits
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * write a c program to assign value between m to n bits     *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num=0xFFFFFFFF,m,n,mask,value;
  printf("Enter Value:");
  scanf("%d",&value);
  printf("Enter m,n bits:");
  scanf("%d%d",&m,&n);
  mask = (((unsigned)1 << (n - m + 1)) - 1) << m;
  num &= ~(mask);
  num |=(value<<m);
  printf("set=%X\n", num);
  return 0;
}
```
### 2.Bit is set or not in a number?
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * How to check if a particular bit is set or not in a number? *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,bit;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter bit:");
  scanf("%d",&bit);
  (num & (1 << bit)) ? printf("Bit is Set\n") : printf("Bit is Reset\n");
  return 0;
}
```
### 3.Bit is set or not in a number in macro
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * How to check if a particular bit is set or not in a number in macro *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>
#define BIT_IS_SET_OR_NOT(num,bit) (num & (1 << bit))

int main(void)
{
  int num,bit;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter bit:");
  scanf("%d",&bit);
  if(BIT_IS_SET_OR_NOT(num,bit))
    printf("Bit is Set\n");
  else
    printf("Bit is Reset\n");
  return 0;
}
```
### 4.Convert decimal to binary in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * write a c program to convert decimal to binary in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,i=0,total_bits=0;
  printf("Enter Number:");
  scanf("%d",&num);
  total_bits=(sizeof(num)*8-1);
  for(i=total_bits; i>=0; i--)
  {
    printf("%u ",((num>>i)&1));
  }
  printf("\n");
  return 0;
}
```
### 5.Count leading zeros and tailing zeros in the given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * write a c program count leading zeros and tailing zeros in the given number       *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,t_count=0,l_count,i;
  printf("Enter Number:");
  scanf("%d",&num);
  for(i=0; i<(sizeof(int)*8);i++)
  {
    if((num & 1)==0)
    {
      t_count++;
    }
    else
    {
      for(  ;i<(sizeof(int)*8); i++)
      {
        if((num & 1)==0)
        {
          l_count++;
        }
        else
        {
          l_count=0;
        }
        num >>=1;
      }
    }
    num >>=1;
  }
  printf("Leading zero's=%d Tails zero's=%d\n",l_count,t_count);
  return 0;
}
```
### 6.Count number of set and reset bits in give number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * write a c program count number of set and reset bits in give number       *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
#include <stdio.h>

int main(void)
{
  int num,i=0,ones=0,zeros=0;
  printf("Enter Number:");
  scanf("%d",&num);
  for(i=0; i< (8*sizeof(int)); i++)
  {
    if(num & 1)
    {
      ones++;
    }
    else
    {
      zeros++;
    }
    num >>=1;
  }
  printf("one's=%d zero's=%d\n",ones,zeros);
  return 0;
}
```
### 7.Count number of bits in give number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * write a c program count number of bits in give number       *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
#if 1
#include <stdio.h>

int main(void)
{
    int num,count=0;
    printf("Enter Number:");
    scanf("%d",&num);
    while(num)
    {
      if(num & 1)
      {
        count++;
      }
      num >>=1;
    }
    printf("%d\n",count);
    return 0;
}
#endif

#if 0
#include <stdio.h>

int main(void)
{
    int num,count=0,i;
    printf("Enter Number:");
    scanf("%d",&num);
    for(i=0; i<32; i++)
    {
      if((1<<i)& num)
      {
        count++;
      }
    }
    printf("%d\n",count);
    return 0;
}
#endif
```
### 8.
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * Write a c program to interchange the first 4bits with next 4bits bytes in 32 bit Integer Variable *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
```
### 9.Given number is even or odd
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * 
 * write a c program to given number is even or odd      *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,bit;
    printf("Enter Number:");
    scanf("%d",&num);
    if(num & 1)
    {
      printf("Number is odd\n");
    }
    else
    {
      printf("Number is even\n");
    }
    return 0;
}
```
### 10.Given number is power of 2 or not 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * write a c program to check power of 2 or not in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,bit=0;
    printf("Enter Number:");
    scanf("%d",&num);
    bit= ((num !=0) && (num & (num-1)));
    if(bit == 1)
    {
      printf("Given number is not power of 2\n");
    }
    else
    {
      printf("Given number is power of 2\n");
    }
    return 0;
}
```
