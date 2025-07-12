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
