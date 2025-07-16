## ------------------------- Strings Programs ---------------------------
### 1.Convert integer string into integer number
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 *  write a c program to convert integer string into integer number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0,num=0;
  printf("Enter String :");
  scanf("%s",str);
  while(str[i])
  {
    if((str[i]>='0') &&  (str[i]<='9'))
    {
      num=( num * 10 ) + (str[i]-48);
    }
    i++;
  }
  printf("%d\n",num);
  return 0;
}
```
### 02. Convert into string into integer number 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 02. write a c program to convert into string into integer number  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(void)
{
  char str[100];
  int  s[100];
  int i=0,sum;
  printf("Enter String :");
  scanf("%s",str);
  //fgets(str,99,stdin);
  //str[strlen(str)-1]='\0';
  while(str[i])
  {
    if((str[i]>='a') && (str[i]<='z'))
    {
      s[i]=(int)str[i];
    }
    else
    {
      s[i]=(int)str[i];
    }
    i++;
  }
  sum=i;
  for(i=0; i<sum; i++)
    printf("%c-%d ",str[i],s[i]);
  printf("\n");
  return 0;
}
```
### 03. Count number of substring in given string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 03.write a c program to count number of substring in given string *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(void)
{
  //char *p="this is krishna aaketi and he is bad boy";
  //char *s="is";
  char str[100],s[10];
  char *ptr=str,*sptr=s;
  int i=0,j=0,count=0,len;
  printf("Enter string\n");
  fgets(str,99,stdin);
  str[strlen(str)-1]='\0';
  printf("Enter Sub string\n");
  scanf("%s",str);
  len=strlen(s);
  while(*(ptr+j) != '\0')
  {
    i=0;
    while(i < len)
    {
      if(*(sptr+i) == *(ptr+i+j))
      {
        i++;
      }
      else
      {
        break;
      }
    }
    if(i == len)
    {
      count++;
    }
    j++;
 }
 printf("\"%s\" is repeated in \"%s\" for %d times\n",s,ptr,count);
 return 0;
}
```
### 04. Find little Endian or Big Endian 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 04. Write a C program to find little Endian or Big Endian               *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>

int main(void)
{
  unsigned int num = 0x12345678;
  unsigned char *ptr = (unsigned char *)&num;
  printf("Number: 0x%X\n", num);
  printf("Byte order: ");
  for (int i = 0; i < sizeof(num); i++)
  {
    printf("%02X ",*(ptr+i));
  }
  printf("\n");
  if (*ptr == 0x78)
        printf("System is Little Endian\n");
    else if (*ptr == 0x12)
        printf("System is Big Endian\n");
    else
        printf("Unknown Endian format\n");
    return 0;
}
```
### 05. Find a last second word length in given string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 05. Write a c program to find a last second word length in given string *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(void)
{
  char str[100];
  int len=0,count=0;
  printf("Enter string\n");
  fgets(str,99,stdin);
  len=strlen(str);
  str[--len]='\0';
  while(str[--len])
  {
    if(str[len]==' ')
    {
      while(str[--len] !=' ')
        count++;
      break;
    }
  }
  printf("%d\n",count);
  return 0;
}
```
### 06. Find a middle word in given string 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 06. Write a c program to find a middle word in given string     *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0,j=0,count=1;
  printf("Enter string\n");
  fgets(str,99,stdin);
  str[strlen(str)-1]='\0';
  while(str[i])
  {
    if(str[i]==' ')
    {
      count++;
    }
    i++;
  }
  j=(count/2)+1;
  i=0,count=1;
  while(str[i])
  {
    if(str[i]==' ')
    {
      count++;
    }
    if(j==count)
    {
      while(str[++i] !=' ')
         printf("%c",str[i]);
      break;
    }
    i++;
  }
  printf("\n");
  return 0;
}
```
### 07. Find substring in given string 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 07. Write a c program to find substring in given string         *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(void)
{
  char *ptr="This is krishna";
  char *s="krishna";
  //char str[100],s[10];
  //char *ptr=str,*sptr=s;
  int i,len=0,j=0,count=0;
  //printf("Enter String\n");
  //fgets(str,99,stdin);
  //str[len=strlen(str)-1]='\0';
  //printf("Enter Sub string\n");
  //scanf("%s",s);
  len=strlen(s);
  while(*(ptr+j) != '\0')
  {
    i=0;
    while(i < len)
    {
      if(*(s+i) == *(ptr+i+j))
      {
        i++;
      }
      else
      {
        break;
      }
    }
    if(i == len)
    {
      count++;
      printf("\"%s\" is present in \"%s\" at index=%d\n",s,s,j);
    }
    j++;
  }
  printf("number of substring=%d\n",count);
  return 0;
}
```
### 08. Find longest non repeating substring in given string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 08. Write a c program to find longest non repeating substring in given string.*
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */
#include<stdio.h>
#include<string.h>

void longest(char *str);

int main(void)
{
  char str[100];
  printf("Enter a string : ");
  fgets(str,sizeof(str),stdin);
  str[strlen(str)-1]='\0';
  longest(str);
  return 0;
}

void longest(char *str)
{
  int i,j,k,start=0,max=0;
  int len = strlen(str);
  for(i=0;i<len;i++)
  {
    int visited[256]={0};
    for(j=i;j<len;j++)
    {
      if(visited[(unsigned char)str[j]] == 1)
      {
        break;
      }
      visited[(unsigned char)str[j]] = 1;
    }
    if((j - i) > max)
    {
      max = j - i;
      start = i;
    }
  }
  printf("The longest substring : ");
  for(k=start;k<start + max;k++)
  {
    printf("%c",str[k]);
  }
  printf("\nThe length of substring is : %d\n",max);
}
```
### 09. Print each character of string  and print its address  
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 09. Write a c program to print each character of string  and print its address    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  int i;
  char str[]="KRISHNA";
  for(i=0; str[i] !='\0'; i++)
  {
    printf("%c\t",str[i]);
    printf("%p\n",&str[i]);
  }
  return 0;
}
```
### 10. Print each character of string  and print its address by using pointers
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 10. Write a c program to print each character of string  and print its address    *
 *  by using pointers                                                                *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  int i;
  char *ptr="KRISHNA";
  for(i=0; i<strlen(ptr); i++)
  {
    printf("%c\t",*(ptr+i));
    printf("%p\n",(ptr+i));
  }
  return 0;
}
```
### 11. Take input from user and print the string 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 12. Write a c program to take input from user and print the string  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  char str[30];
  printf("Enter String :");
  scanf("%s",str);
  printf("%s\n",str);
  return 0;
}
```
### 12. Reverse string using pointer in recursive function 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 12. write a C program to reverse string using pointer in recursive function   *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>
#include <string.h>

void reverse_Recursive(char *start, char *end);

int main(void)
{
  char str[100];
  printf("Enter a string: ");
  scanf("%s", str);  // reads without spaces
  reverseRecursive(str, str + strlen(str) - 1);
  printf("Reversed string: %s\n", str);
  return 0;
}

void reverse_Recursive(char *start, char *end)
{
  if(start >= end)
  {
    return;
  }
  // Swap characters
  char temp = *start;
  *start = *end;
  *end = temp;
  // Recursive call
  reverse_Recursive(start + 1, end - 1);
}
```
### 13. Sum of digit in the given strings
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 13. Write a c program to sum of digit in the given strings      *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0,sum=0;
  printf("Enter String :");
  fgets(str,99,stdin);
  str[strlen(str)-1]='\0';
  while(str[i])
  {
    if((str[i]>='0') && (str[i]<='9'))
    {
      sum=(sum+(str[i]-48));
    }
    i++;
  }
  printf("sum=%d\n",sum);
  return 0;
}
```
### 14. convert upper case letter to lower case letter in given string and viceversa 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 14. write a c++ program to convert upper case letter to lower case letter in          *
 * given string and viceversa                                                            *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0;
  printf("Enter a string\n");
  scanf("%[^\n]",str);
  while(str[i]!='\0')
  {
    if(str[i]>='a' && str[i]<='z')
    {
      str[i]=str[i]-' ';
    }
    else if(str[i]>='A' && str[i]<='Z')
    {

      str[i]=str[i]+' ';
    }
    i++;
  }
  printf("the string is :%s\n",str);
  return 0;
}
```
