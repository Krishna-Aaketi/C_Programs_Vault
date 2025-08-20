### 
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void toLowerStr(char *str) 
{
    for(int i=0; str[i]; i++) 
    {
        str[i] = tolower(str[i]);
    }
}

int getMonthNumber(char *month) 
{
    char *months[] = {"jan","feb","mar","apr","may","jun","jul","aug","sep","oct","nov","dec"};
    for(int i=0; i<12; i++) 
    {
        if(strcmp(month, months[i]) == 0)
            return i+1;
    }
    return -1;
}

int main() 
{
    char month[10];
    char supportType[10];
    
    printf("Enter month (e.g., Jan): ");
    scanf("%s", month);
    toLowerStr(month);
    int monthNum = getMonthNumber(month);
    if(monthNum == -1) 
    {
        printf("Invalid month name.\n");
        return 1;
    }

    printf("Enter support type (e.g., LTS or Standard): ");
    scanf("%s", supportType);
    toLowerStr(supportType);
    
    int active = 0;
    if(strcmp(supportType, "lts") == 0) 
    {
	if(monthNum!= 6 && monthNum!=1)
	{
		printf("%s month no lts releases\n",month);
		return 1;
	}
        if(monthNum >= 6 && monthNum <= 12) 
	{
            active = 1;
        }
    } 
    else if(strcmp(supportType, "standard") == 0) 
    {
        if(monthNum == 8) 
	{
            active = 1;
        }
    }
    if(strcmp(supportType,"standard")==0)
    {
    	if(active) 
    	{
        	printf("Support for %s (%s) is ACTIVE.it's going to be exparied on Aug 31st\n", month, supportType);
    	} 
    	else if(monthNum<8 && monthNum>=1) 
    	{
        	printf("Support for %s (%s) is EXPIRED(%s 31st)\n", month, supportType,month);
    	}
	else
	{
		printf("%s month support is not relesed(relese on %s 1st)\n",month,month);
	}
    }
    else if(strcmp(supportType,"lts")==0)
    {
    	if(active) 
    	{
        	printf("Support for %s (%s) is ACTIVE.it's going to be exparied on Dec 31st\n", month, supportType);
    	} 
    	else 
    	{
        	printf("Support for %s (%s) is EXPIRED(Jun 30)\n", month, supportType);
    	}
    }

    return 0;
}
```
