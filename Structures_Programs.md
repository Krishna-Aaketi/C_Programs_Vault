###
```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

struct buginfo{
	int bugid;
	char prioprit[3];
	char status[7];
};

int pri(struct buginfo b[],char *c){
	int i,count=0;
	for(i=0;i<3;i++){
		if(strcmp(b[i].prioprit,c)==0)
			count++;
	}
	return count;
}

int sta(struct buginfo b[],char *c){
	int i,count=0;
	for(i=0;i<3;i++){
		if(strcmp(b[i].status,c)==0){
			count++;
		}
	}
	return count;
}



int main(){
	struct buginfo b[3];
	int i,choice;
	char prop[2],stat[7];
	for(i=0;i<3;i++){
		printf("enter bugid\nenter priorty p,q,r\nenter status 0 for anlysis 1 for fixed\n");
		scanf("%d %2s %s",&b[i].bugid,b[i].prioprit,b[i].status);
	}
	do{
		printf("enter 1 for finding priprity \nenter 2 for status\nenter 3 for exit\n");
		scanf("%d",&choice);
		switch(choice){
			case 1:
				printf("enter the priority\n");
				scanf("%3s",prop);
				printf("%d is %s priority count\n",pri(b,prop),prop);
				break;
			case 2:
				/*printf("enter the status to check 1 for fix 0 for analysis\n");
				scanf("%d",&s);*/
				do{
					printf("enter fail or analys only\n");
					scanf("%s",stat);
				}while(strcmp(stat,"fail")!=0&&strcmp(stat,"analys")!=0);
				if(strcmp(stat,"fail")==0)
					printf("%d is the failed status count \n",sta(b,stat));
				else
					printf("%d is the fixed status count \n",sta(b,stat));
				break;
		}
	}while(choice!=3);
}
```


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
