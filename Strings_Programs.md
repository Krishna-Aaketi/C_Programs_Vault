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
### Output
```c
Enter String :krishna6244
6244
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
### Output
```c
Enter String :krishna6244
k-107 r-114 i-105 s-115 h-104 n-110 a-97 6-54 2-50 4-52 4-52
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
### Output
```c
Enter string
krishna is good
Enter Sub string
is
"" is repeated in "is" for 2 times
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
### Output
```c
Number: 0x12345678
Byte order: 78 56 34 12
System is Little Endian
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
### Output
```c
Enter string
this is krishna aaketi
7
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
### Output
```c
Enter string
this is krishna aaketi
krishna
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
### Output
```c
Enter String
krishna is a name
Enter Sub string
name
"name" is present in "name" at index=13
number of substring=1
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
### Output
```c
Enter a string : krishnaaaketiisaname
The longest substring : krishna
The length of substring is : 7
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
### Output
```c
K       0x7ffe6c5b2340
R       0x7ffe6c5b2341
I       0x7ffe6c5b2342
S       0x7ffe6c5b2343
H       0x7ffe6c5b2344
N       0x7ffe6c5b2345
A       0x7ffe6c5b2346
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
### Output
```c
K       0x61bf072db004
R       0x61bf072db005
I       0x61bf072db006
S       0x61bf072db007
H       0x61bf072db008
N       0x61bf072db009
A       0x61bf072db00a
```
### 11. Take input from user and print the string 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 11. Write a c program to take input from user and print the string  *
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
### Output
```c
Enter String :krishna
krishna
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
### Output
```c

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
### Output
```c
Enter String :krishna6244
sum=16
```
### 14. convert upper case letter to lower case letter in given string and viceversa 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 14. write a c++ program to convert upper case letter to lower case letter in given string and viceversa *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

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
### Output
```c
Enter a string
KrisHNA AaKeti
the string is :kRIShna aAkETI
```
### 15. Remove duplicate character in given string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 15. Write a c program to remove duplicate character in given string *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#if 0

#include <stdio.h>
#include <string.h>

int main(void)
{
  char str1[100],str2[100];
  int i,j=0,k,temp;
  printf("Enter a string: ");
  scanf("%s",str1);
  for(i=0;str1[i] != '\0';i++)
  {
    temp=0;
    for(k=0;k<j;k++)
    {
      if(str2[k] == str1[i])
      {
        temp=1;
        break;
      }
    }
    if(!temp)
    {
      str2[j++] = str1[i];
    }
  }
  str2[j] = '\0';
  printf("%s\n", str2);
  return 0;
}

#endif

#if 1

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i, j, k;
  printf("Enter String: ");
  scanf("%s", str);
  for(i=0;str[i] != '\0';i++)
  {
    j=i+1;
    while(str[j])
    {
      if(str[i]==str[j])
      {
        for(k=j;str[k]!='\0';k++)
        {
          str[k]=str[k + 1];
        }
      }
      else
      {
        j++;
      }
    }
  }
  printf("The String is=%s\n", str);
  return 0;
}
#endif

```
### Output
```c
Enter String: aaavvvbbbbeecccdd
The String is=avbecd
```
### 16. Count vowels consonants, digits, and spaces in a string 
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 16. Write a C program to count vowels consonants, digits, and spaces in a string      *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0,count=0,vowels=0,digits=0,spaces=0;
  printf("Enter a string(<99):\n");
  scanf("%[^\n]",str);
  while(str[i])
  {
    if((str[i] == 'a' || str[i] == 'e' || str[i] =='i' || str[i]=='o' || str[i] =='u') ||
      (str[i] == 'A' || str[i] == 'E' || str[i] =='I' || str[i]=='O' || str[i] =='U'))
    {
      vowels++;
    }
    else if((str[i] >= 'a' && str[i] <='z') || (str[i] >='A' && str[i] <='Z'))
    {
      count++;
    }
    else if(str[i]==' ')
    {
      spaces++;
    }
    else if(str[i] >='0' && str[i] <= '9')
    {
      digits++;
    }
    i++;
  }
  printf("In given string Vowels=%d consonants=%d digits=%d spaces=%d \n",vowels,count,digits,spaces);
  return 0;
}
```
### Output
```c
Enter a string(<99):
krishna aaketi
In given string Vowels=6 consonants=7 digits=0 spaces=1
```
### 17. Implement strrev() function without using strrev()
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 17.write a C program to implement strrev() function without using strrev  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

void my_strrev(char *ptr);

int main(void)
{
  char str[100];
  int i=0;
  printf("Enter String :");
  fgets(str,99,stdin);
  str[strlen(str)-1]='\0';
  my_strrev(str);
  printf("Reverse String=%s\n",str);
  return 0;
}

void my_strrev(char *ptr)
{
  int i=0;
  char temp;
  int len=strlen(ptr);
  for(i=0; i<len; i++)
  {
    len--;
    temp=*(ptr+i);
    *(ptr+i)=*(ptr+len);
    *(ptr+len)=temp;
  }
  return ;
}
```
### Output
```c
Enter String :krishna aaketi
Reverse String=itekaa anhsirk
```
### 18. Check given string is Palindrome or not
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 18. Write a C program to Check given string is Palindrome or not          *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0,len,flag=0;
  printf("Enter String(<99):");
  fgets(str,99,stdin);
  str[strlen(str)-1]='\0';
  len=strlen(str);
  for(i=0; i<=len; i++)
  {
    if(str[i] !=str[--len])
    {
      flag=1;
      break;
    }
  }
  if(flag==1)
  {
    printf("\"%s\" is not palindrome string\n",str);
  }
  else
  {
    printf("%s is palindrome string\n",str);
  }
  return 0;
}
```
### Output
```c
Enter String(<99):malayalam
malayalam is palindrome string
```
### 19. Check given two strings is anagrams or not
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 19. Write a C program to Check given two strings is anagrams or not       *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str1[100],str2[100];
  int i=0,j,len,flag=0;
  printf("Enter String 1:(<99):");
  fgets(str1,99,stdin);
  str1[strlen(str1)-1]='\0';
  len=strlen(str1);
  printf("Enter String 2:(<99):");
  fgets(str2,99,stdin);
  str2[strlen(str2)-1]='\0';

  if(strlen(str1)==strlen(str2))
  {
    flag=0;
    for(i=0; i<len; i++)
    {
      for(j=0; j<strlen(str2); j++)
      {
        if(str1[i] ==str2[j])
        {
          flag=1;
          break;
        }
      }
      if(flag==0)
      {
        break;
      }
    }
    if(flag==1)
    {
      printf("given two string are anagram string\n");
    }
    else
    {
      printf("given two strings are not anagram string\n");
    }
    return 0;
  }
  else
  {
    printf("Given two string are Not anagram\n");
  }
  return 0;
}
```
### Output
```c
Enter String 1:(<99):silent
Enter String 2:(<99):lisent
given two string are anagram string
```
### 20. Count number of words in given string  
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 20. Write a C program to count number of words in given string  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0,count=0;
  printf("Enter a string(<99):\n");
  fgets(str,99,stdin);
  // Remove newline character if present
  str[strcspn(str, "\n")] = '\0';
  while(str[i])
  {
    if(str[i]==' ' || str[i+1]=='\0' || str[i]=='.')
    {
      count++;
    }
    i++;
  }
  printf("In given string Number of Words=%d \n",count);
  return 0;
}
```
### Output
```c
Enter a string(<99):
krishna aaketi this is a name.and he is a man
In given string Number of Words=11
```
### 21. Implement strcat function
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 21. Write a C program to implement strcat function    *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include <stdio.h>
void my_strcat(char *,char *);

int main(void)
{
    char str1[200],str2[100];
    int i,count=0;
    printf("Enter string 1:");
    scanf("%s",str1);
    printf("Enter String 2:");
    scanf("%s",str2);
    my_strcat(str1,str2);
    printf("%s\n",str1);
    return 0;
}

void my_strcat(char *str1,char *str2)
{
  int i=0,j=0;
  while(str1[i])
  {
    i++;
  }
  while(str1[i]=str2[j])
  {
      i++;
      j++;
  }
}
```
### Output
```c
Enter string 1:krishna
Enter String 2:aaketi
krishnaaaketi
```
### 22. Most frequent character in given string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 22. Write a C program to Find the most frequent character in given string *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str[100],arr[256]={0};
  int i=0,temp=0,x=0;
  printf("Enter a string(<99):\n");
  fgets(str,99,stdin);
  // Remove newline character if present
  str[strcspn(str, "\n")] = '\0';
  while(str[i])
  {
    arr[str[i]] += 1;
    i++;
  }
  i=0;
  temp=arr[0];
  while(i<256)
  {
    if(temp < arr[i])
    {
      temp=arr[i];
      x=i;
    }
    i++;
  }
  printf("Most frequent character is '%c' and %d times\n",x,temp);
  return 0;
}
```
### Output
```c
Enter a string(<99):
krishna aaketi
Most frequent character is 'a' and 3 times
```
### 23. Replace spaces with Hyphens in given a string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 23. Write a C program to Replace spaces with Hyphens in given a string  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

int main(void)
{
  char str[100];
  int i=0;
  printf("Enter a string(<99):\n");
  scanf("%[^\n]",str);
  while(str[i])
  {
    if(str[i]==' ')
    {
      str[i]='-';
    }
    i++;
  }
  printf("In given string is %s\n",str);
  return 0;
}
```
### Output
```c
Enter a string(<99):
i am krishna aaketi
The string is i-am-krishna-aaketi
```
### 24. Remove all Spaces in given string
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 24. Write a C program to Remove all Spaces in given string  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  char str[100],str2[100];
  int i=0,j=0;
  printf("Enter a string(<99):\n");
  scanf("%[^\n]",str);
  while(str[i])
  {
    if(str[i] !=' ')
    {
      str2[j]=str[i];
      j++;
    }
    i++;
  }
  str2[j]='\0';
  printf("In given string is %s\n",str2);
  return 0;
}
```
### Output
```c
Enter a string(<99):
i am krishna aaketi
In given string is iamkrishnaaaketi
```
### 25. Remove all Spaces in given string using one array
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 25. Write a C program to Remove all Spaces in given string using one array  *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>

int main(void)
{
  char str[100];
  int i=0,j=0;
  printf("Enter a string(<99):\n");
  scanf("%[^\n]",str);
  while(str[i])
  {
    if(str[i] !=' ')
    {
      str[j]=str[i];
      j++;
    }
    i++;
  }
  str[j]='\0';
  printf("In given string is %s\n",str);
  return 0;
}
```
### Output
```c
Enter a string(<99):
i am krishna aaketi
In given string is iamkrishnaaaketi
```
### 26. Implement the strstr function  
```c
/* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
 * 26. Write a C program to implement the strstr function      *
 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * */

#include<stdio.h>
#include<string.h>

void my_strstr(char *str,char *s);

int main(void)
{
  char str[100],s[20];
  printf("Enter a string(<99):\n");
  scanf("%[^\n]",str);
  printf("Enter a substring:\n");
  scanf("%s",s);
  my_strstr(str,s);
  return 0;
}

void my_strstr(char *str,char *s)
{
  int i=0,j=0,k=0;
  while(str[i])
  {
    if(str[i] == s[j])
    {
      j++;
      if(s[j]=='\0')
      {
        k=1;
        break;
      }
    }
    else
    {
      j=0;
    }
    i++;
  }
  if(k)
  {
    printf("The Substring is present in Index=%d\n",i-j+1);
  }
  else
  {
    printf("The Substring is not present in Given string\n");
  }
}
```
### Output
```c
Enter a string(<99):
krishna aaketi is a name
Enter a substring:
is
The Substring is present in Index=2
```
