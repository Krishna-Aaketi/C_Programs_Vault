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
### Output
```c
Enter Number:115
Number is odd
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
    a= a ^ b;
    b= b ^ a;
    a= a ^ b;
    printf("a=%d b=%d\n",a,b);
    return 0;
}
```
### Output
```c
Enter a,b:50 20
a=20 b=50
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
### Output
```c
Enter Number:30
Enter 1 for mulitiply:
Enter 2 for division:
1
Given number Multiple by 2=60
```  
### 04. Count number of Set bits in give number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 04. write a c program count number of SET bits in give number   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
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
### Output
```c
Enter Number:10
number of set bits=2
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
### Output
```c
Enter Number:10
Enter k value:
0
Kth Bit is not set
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
### Output
```c
Enter Number:10
Enter k value:
0
number of set bits=11
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
### Output
```c
Enter Number:10
Enter k value:
1
number of set bits=8
```  
### 08. Toggle the k-th bit of a number
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
### Output
```c
Enter Number:10
Enter k value:
0
number of set bits=11
```
### 09.Check power of 2 or not in given number
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
### Output
```c
Enter Positive Number:
1024
Given number is power of 2
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
### Output
```c
Enter Number:10
i=1
After Turnoff Right Most Bit Value=8
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
### Output
```c
Enter Number:10
i=1
After Isolate Right Most Bit Value=2
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
### Output
```c
Enter Number:10
i=3
After Turnoff left Most Bit Value=2
```  
### 13. Isolate left most bit in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 13.write a C program to isolate left most bit in given number   *
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
    num &= (1 << i);
    printf("i=%d\n",i);
    printf("After Isolate left Most Bit Value=%d\n",num);
    return 0;
}
```
### Output
```c
Enter Number:10
i=3
After Isolate left Most Bit Value=8
```
### 14.Assign value between m to n bits
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 14. write a c program to assign value between m to n bits all bits filled with 1's  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

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
### Output
```c
Enter Value:10
Enter m,n bits:0 16
set=FFFE000A
```
### 15.Bit is set or not in a number using Macro
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 15.How to check if a particular bit is set or not in a number in macro  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

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
### Output
```c
Enter Number:12
Enter bit:0
Bit is Reset
```
### 16.Convert decimal to binary in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 16.write a c program to convert decimal to binary in given number   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

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
### Output
```c
Enter Number:10
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1 0 1 0
```
### 17.Count leading zeros and tailing zeros in the given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 17.write a c program count leading zeros and tailing zeros in the given number    *
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
### Output
```c
Enter Number:32
Leading zero's=26 Tails zero's=5
```
### 18.Count number of set and reset bits in give number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 18.write a c program count number of set and reset bits in give number    *
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
### Output
```c
Enter Number:32
one's=1 zero's=31
```  
### 19. Count number of set bits in a number with less iterations
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 19.write a c program to count number of set bits in a number with less iterations *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,count = 0;
  printf("Enter a number: ");
  scanf("%d", &num);
  while (num)
  {
    num = num & (num - 1);
    count++;
  }
  printf("Number of set bits: %d\n", count);
  return 0;
}
```
### Output
```c
Enter a number: 32
Number of set bits: 1
```
### 20. Convert decimal to binary in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 20.Write a c program to convert decimal to binary in given number *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,i=0,total_bits=0;
    printf("Enter Number:");
    scanf("%d",&num);
    total_bits=(sizeof(num)*8-1);
    for(i=0; i<=total_bits; i++)
    {
      printf("%u ",((num>>i)&1));
    }
    printf("\n");
    return 0;
}
```
### Output
```c
Enter Number:10
0 1 0 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
```
### 21. Print total nmuber of bits in given number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 21.write a c program to print total nmuber of bits in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

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
### Output
```c
Enter Number:32
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1 0 0 0 0 0
```
### 22.Count number of zero's in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 22.write a C program to count number of zero's in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#if 0
#include <stdio.h>

int main(void)
{
    int num,count=0;
    printf("Enter Number:");
    scanf("%d",&num);
    while(num)
    {
      if((num & 1) == 0)
      {
        count++;
      }
      num >>=1;
    }
    printf("number of zeros=%d\n",count);
    return 0;
}
#endif

#if 1
#include <stdio.h>

int main(void)
{
  int num,count=0,i;
  printf("Enter Number:");
  scanf("%d",&num);
  while(num)
  {
    if(num%2==0)
    {
      count++;
    }
    num=num/2;
  }
  printf("number of zeros=%d\n",count);
  return 0;
}
#endif
```
### Output
```c
Enter Number:32
number of zeros=5
```
### 23. Reset m to n bits in the given number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 23.write a program to c reset m to n bits in the given number   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,m,n,mask;
    printf("Enter Number :");
    scanf("%d",&num);
    printf("Enter m,n values:");
    scanf("%d%d",&m,&n);
    mask =~((((unsigned)1 << (n - m + 1)) - 1) << m);
    num &=mask;
    printf("Reset=%d\n", num);
    return 0;
}
```
### Output
```c
Enter Number :33
Enter m,n values:0 2
Reset=32
```
### 24. Reset right side last two bits
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 24.write a c program reset right side last two bits         *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num;
    printf("Enter Number:");
    scanf("%d",&num);
    num=num & ~(0x3);
    printf("%d\n",num);
    return 0;
}
```
### Output
```c
Enter Number:7
4
```
### 25. Set m to n bits in the given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 25.write a program to c set m to n bits in the given number   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,m,n,mask;
    printf("Enter Number :");
    scanf("%d",&num);
    printf("Enter m,n values:");
    scanf("%d%d",&m,&n);
    mask = ((1 << (n - m + 1)) - 1) << m;
    num |=mask;
    printf("set=%d\n", num);
    return 0;
}
```
### Output
```c
Enter Number :33
Enter m,n values:1 4
set=63
```
### 26. Swap the bytes in 16 bit Integer Variable using macro
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 26. Write a c program to Swap the bytes in 16 bit Integer Variable using macro  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

#define SWAP_BYTES_16(x)  (unsigned short)((((x) & 0x00FF) << 8) | (((x) & 0xFF00) >> 8))

int main(void)
{
    unsigned short num,swapped;
    printf("Enter Number:");
    scanf("%hX",&num);
    swapped = SWAP_BYTES_16(num);
    printf("Original: 0x%04X\n", num);
    printf("Swapped : 0x%04X\n", swapped);
    return 0;
}
```
### Output
```c
Enter Number:1234
Original: 0x1234
Swapped : 0x3412
```
### 27.Swap the bytes in 32 bit Integer Variable using macro 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 27.Write a c program to Swap the bytes in 32 bit Integer Variable using macro *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

#define SWAP_BYTES_32(x)  ( ((x & 0x000000FFU) << 24) | \
                            ((x & 0x0000FF00U) << 8)  | \
                            ((x & 0x00FF0000U) >> 8)  | \
                            ((x & 0xFF000000U) >> 24) )

int main(void)
{
    unsigned int val, swapped;
    unsigned char *ptr;

    printf("Enter Value (in hex, e.g., AABBCCDD): ");
    scanf("%X", &val);

    swapped = SWAP_BYTES_32(val);

    ptr = (unsigned char *)&swapped;

    printf("Bytes of swapped value: %02X %02X %02X %02X\n", ptr[0], ptr[1], ptr[2], ptr[3]);
    printf("Original: 0x%08X\n", val);
    printf("Swapped : 0x%08X\n", swapped);
    printf("Size of unsigned int: %zu bytes\n", sizeof(unsigned int));

    return 0;
}
```
### Output
```c
Enter Value (in hex, e.g., AABBCCDD): AABBCCDD
Bytes of swapped value: AA BB CC DD
Original: 0xAABBCCDD
Swapped : 0xDDCCBBAA
Size of unsigned int: 4 bytes
```
### 28. Swap nibble in the given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 28.write a program to swap nibble in the given number   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,mask;
    printf("Enter Number :");
    scanf("%x",&num);
    num=num & 0x0F;
    mask=(((num & 0xC) >>2) | ((num & 0x3) <<2));
    printf("swapped=0x%X\n",mask);
    return 0;
}
```
### Output
```c
Enter Number :31
swapped=0x4
```
### 29. Swap bits within give value
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 29.write a c program to swap bits within give value *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#define RESET_M_TO_N(a,m,n)  a&(~(((~((unsigned)0))>>(sizeof(unsigned)*8-(m-n+1)))<<n))
#define EXTRACT_M_TO_N(a,m,n)  a&(((~((unsigned)0))>>(sizeof(unsigned)*8-(m-n+1)))<<n)
int main(void)
{
  unsigned int a=0xabcdef98;
  unsigned int m1,n1,m2,n2;
  printf("Enter m1,n1:");
  scanf("%d%d",&m1,&n1);
  printf("Enter m2,n2:");
  scanf("%d%d",&m2,&n2);
  a=((RESET_M_TO_N(a,m1,n1)&(RESET_M_TO_N(a,m2,n2)))|
    (((EXTRACT_M_TO_N(a,m1,n1))>>(m1-m2))|((EXTRACT_M_TO_N(a,m2,n2))<<(m2-m1))));
  printf("a=%x\n",a);
  return 0;
}
```
### Output
```c
Enter m1,n1:2 4
Enter m2,n2:4 2
a=62
```
### 30. Toggle m to n bits in the given number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 30.write a program to c toggle m to n bits in the given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,m,n,mask;
    printf("Enter Number :");
    scanf("%d",&num);
    printf("Enter m,n values:");
    scanf("%d%d",&m,&n);
    mask = (((unsigned)1 << (n - m + 1)) - 1) << m;
    num ^=mask;
    printf("Toggle value=%d\n", num);
    return 0;
}

```
### Output
```c
Enter Number :31
Enter m,n values:0 3
Toggle value=16
```
### 31. Non-repeating element in an array where every other element repeats twice
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 31. Find the only non-repeating element in an array where every other element repeats twice.*
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int arr[100],n,res=0,i=0;
  printf("Enter Number:");
  scanf("%d",&n);
  printf("Enter Elements\n");
  for(i=0; i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<n; i++)
  {
    res ^=arr[i];
  }
  printf("first non repeated element=%d\n",res);
  return 0;
}
```
### Output
```c
Enter Number:5
Enter Elements
1 2 3 4 5
first non repeated element=1
```
### 32. Add two number using bit-wise operators
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 32. Write a C program to add two number using bit-wise operators  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int a,b,carry=0;
  printf("Enter a,b:");
  scanf("%d%d",&a,&b);
#if 1
  while(b)
  {
    carry=a & b;
    a = a ^ b;
    b = carry<<1;
  }
#endif
  printf("sum=%d\n",a);
  return 0;
}
```
### Output
```c
Enter a,b:3 7
sum=10
```
### 33. Add one to number using bit-wise operators 
```c

```
### Output
```c

```
### 34. Find all elements of XOR value in given elements
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 34. write a c Program to find all elements of XOR value in given elements   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int arr[100],n,res=0,i=0;
  printf("Enter Number:");
  scanf("%d",&n);
  printf("Enter Elements\n");
  for(i=0; i<n; i++)
  {
    scanf("%d",&arr[i]);
  }
  for(i=0; i<n; i++)
  {
    res ^=arr[i];
  }
  printf("All elements XOR value=%d\n",res);
  return 0;
}
```
### Output
```c
Enter Number:5
Enter Elements
10 20 30 40 50
All elements XOR value=26
```
### 35. Check Parity of Given Number (Odd_or_even_bits) 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 35. Write a c program to Check Parity of Given Number (Odd_or_even_bits)  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num=0,even=0,odd=0;
  printf("Enter Number:");
  scanf("%d",&num);
  if(num>0)
  {
    while(num)
    {
      if(num & 1 )
      {
  even++;
      }
      else
      {
        odd++;
      }
      num >>= 1;
    }
    if(even==odd)
    {
      printf("Even and Odd Bits are Equal\n");
    }
    else
    {
      (even > odd) ? printf("Even bits=%d\n",even) : printf("Odd bits=%d\n",odd);
    }
  }
  else
  {
    printf("Enter Positive Number\n");
  }
  return 0;
}
```
### Output
```c
Enter Number:12
Even and Odd Bits are Equal

Enter Number:7
Even bits=3
```
### 36. Clear All MSB bits given bit position
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 36. Write a c program to clear All MSB bits given bit position  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
    int num,n,mask;
    printf("Enter Number:");
    scanf("%d",&num);
    if(n<1)
    {
      printf("Enter Positive Numbers\n");
      return 0;
    }
    printf("Enter position:");
    scanf("%d",&n);
    mask= ((((unsigned)1)<<(n))-1);
    num &= mask;
    printf("After number is=%d\n",num);
    return 0;
}
```
### Output
```c
Enter Number:7
Enter position:1
After number is=1
```
### 37. Find right most bit position given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 37. Write a c program to find right most bit position given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  int num,position=0;
  printf("Enter Number:");
  scanf("%d",&num);
  if(num<1)
  {
    printf("Enter Positive Numbers\n");
    return 0;
  }
  while(num)
  {
    if(num&1)
    {
      printf("Right most position=%d\n",position);
      break;
    }
    position++;
    num >>= 1;
  }
  return 0;
}
```
### Output
```c
Enter Number:16
Right most position=4
```
### 38. Given number is sparse or not 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 38. Write a c prograam to given number is sparse or not     *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int num=0,flag=0;
  printf("Enter Positive number:\n");
  scanf("%d",&num);
  if(num<2)
  {
    printf("Enter above 1 value\n");
    return 0;
  }
  while(num)
  {
    if((num & 1) && ((num >>1)&1))
    {
      flag=1;
      break;
    }
    num >>= 1;
  }
  if(flag==1)
  {
    printf("Given Number is not Sparse\n");
  }
  else
  {
    printf("Given Number is Sparse\n");
  }
  return 0;
}
```
### Output
```c
Enter Positive number:
10
Given Number is Sparse

Enter Positive number:
15
Given Number is not Sparse
```
### 39. Subtract two number using bit-wise operators
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 39. Write a C program to subtract two number using bit-wise operators   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int a,b,carry=0;
  printf("Enter a,b:");
  scanf("%d%d",&a,&b);
  while(b)
  {
    carry=(~a) & b;
    a = a ^ b;
    b = carry<<1;
  }
  printf("subtraction=%d\n",a);
  return 0;
}
```
### Output
```c
Enter a,b:5 9
subtraction=-4
```
### 40. Multiple two variables using bitwise operators 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 40. Write a c program to multiple two variables using bitwise operators *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int a,b,result=0,sign=1;
  printf("Enter the numbers:\n");
  scanf("%d%d",&a,&b);
  result = 0;
  if(b<0)
  {
    sign=-1;
  }
  while( b > 0)
  {
    if(b & 1)
    {
      result += a;
    }
    a <<= 1;
    b >>= 1;
  }
  printf("mul = %d\n",result);
  return 0;
}
```
### Output
```c
Enter the numbers:
5 2
mul = 10
```
### 41. Count bits to flip to convert Number A to Number B
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 41. Write a C program to Count bits to flip to convert Number A to Number B *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int a,b,count=0;
  printf("Enter a,b:");
  scanf("%d%d",&a,&b);
  while(a || b)
  {
    if((a & 1) != (b & 1))
    {
      count++;
    }
    a >>=1;
    b >>=1;
  }
  printf("%d bits need to be flipped\n",count);
  return 0;
}
```
### Output
```c
Enter a,b:15 10
2 bits need to be flipped
```
### 42. Fast Exponentiation( power of x^y using bits)
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 42. Write a c program to Fast Exponentiation( power of x^y using bits)  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int x,y,temp,result=1;
  printf("Enter X,Y:");
  scanf("%d%d",&x,&y);
  temp=x;
  while(y)
  {
    if(y & 1)
    {
      result *=temp;
    }
    temp *= temp;
    y >>= 1;
  }
  printf("Power Of x^y=%d\n",result);
  return 0;
}
```
### Output
```c
Enter X,Y:2 10
Power Of x^y=1024
```
### 43. Implement XOR using ~and & operators
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 43. Write a c Program to implement XOR using ~and & operators     *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int a,b,result=0;
  printf("Enter a,b:");
  scanf("%d%d",&a,&b);
  result =~(~(~a & b) & ~(a & ~b));
  printf("a ^ b = %d\n",result);
  return 0;
}
```
### Output
```c
Enter a,b:10 5
a ^ b = 15
```
### 44. check given number is power of 4 or not
```c

```
### Output
```c

```
### 45. Toggle All bits up to the Most significant bits
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 45. Write a C  program to Toggle All bits up to the Most significant bits *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  unsigned int num,mask,temp,msb=0;
  printf("Enter Positive integers:");
  scanf("%d",&num);
  if(num<0)
  {
    printf("Enter Positive Numbers\n");
    return 0;
  }
  temp=num;
  while(temp)
  {
    msb++;
    temp >>=1;
  }
  mask=((1U << msb)-1);
  num ^= mask;
  printf("Toggle number is %d\n",num);
  return 0;
}
```
### Output
```c
Enter Positive integers:10
Toggle number is 5
```
### 46. Check all bits are set or not in given number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 46. Write a C program to Check all bits are set or not in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int num;
  printf("Enter Positive number:");
  scanf("%d",&num);
  if(num<1)
  {
    printf("Enter Positive Number\n");
    return 0;
  }
  while(num)
  {
    if((num & 1) == 0)
    {
      printf("Given number not all bits are Set\n");
      return 0;
    }
    num >>= 1;
  }
  printf("Given number all bits are Set\n");
  return 0;
}
```
### Output
```c
Enter Positive number:15
Given number all bits are Set
```
### 47. Reverse n Bits from LSB in given number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 47. Write a c Program to Reverse n Bits from LSB in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  unsigned int num,n,i=0,result=0;
  printf("Enter Number:");
  scanf("%d",&num);
  printf("Enter n bits:");
  scanf("%d",&n);
  while(i<n)
  {
    result <<= 1;
    result |=(num&1);
    num >>= 1;
    i++;
  }
  printf("The Reverse Number is %d\n",result);
  return 0;
}
```
### Output
```c
Enter Number:13
Enter n bits:4
The Reverse Number is 11
```
### 48. Count total set bits from 1 to N in given number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 48.Write a c program to Count total set bits from 1 to N in given number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int num,i=0,temp=0,count=0;
  printf("Enter Number:");
  scanf("%d",&num);
  for(i=1; i<=num; i++)
  {
    temp=i;
    while(temp)
    {
      if(temp & 1)
      {
        count++;
      }
      temp >>= 1;
    }
  }
  printf("Total set bits from 1 To %d is %d\n",num,count);
  return 0;
}
```
### Output
```c
Enter Number:5
Total set bits from 1 To 5 is 7
```
