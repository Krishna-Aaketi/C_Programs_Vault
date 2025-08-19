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
