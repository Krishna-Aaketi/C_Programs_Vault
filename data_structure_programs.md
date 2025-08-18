### 01. Add at Beginning Single Linked list 
```c
int4_t add_at_begining(sll_t **pphead,int4_t data)
{
  sll_t *pnew=NULL;
  pnew=(sll_t *)malloc(sizeof(sll_t));
  if (pnew==NULL)
  {
    return 1;
  }
  pnew->data=data;
  pnew->pnext=*pphead;
  *pphead=pnew;
}
```
### 02. Display Single Linked list
```c 
void0_t display(sll_t *phead)
{
  sll_t *ptemp=phead;
  while(ptemp!=NULL)
  {
   printf("%d\n",ptemp->data);
   ptemp=ptemp->pnext;
  }
}
```
### 03. Add a Node at N position in Single Linked list 
```c
int4_t addN(sll_t **pphead,int4_t n,int4_t data)
{
  sll_t *ptemp=*pphead,*pnew=NULL;
  if(n<0)
  {
    return 1;
  }

  pnew=(sll_t *)malloc(sizeof(sll_t));
  if (pnew==NULL)
  {
    return 4;
  }
  pnew->data=data;
  if(n==0)
  {
    pnew->pnext=*pphead;
    *pphead=pnew;
    return 0;
  }
  while(--n)
  {
    ptemp=ptemp->pnext;
    if(ptemp==NULL)
    {
      free(pnew);
      return 2;
    }
  }
  pnew->pnext=ptemp->pnext;
  ptemp->pnext=pnew;
  return 0;
}
```
### 04. Delete a Node(using key) Single Linked list 
```c
int4_t delete(sll_t **pphead,int4_t key)
{
  sll_t *ptemp=*pphead,*pprev;
  if(*pphead==NULL)
  {
    return 1;
  }
  else
  {
    while(ptemp!=NULL)
    {
      if (ptemp->data==key)
      {
        if (ptemp==*pphead)
        {
          *pphead=ptemp->pnext;
        }
        else
        {
            pprev->pnext=ptemp->pnext;
        }
        free(ptemp);
        return 0;
      }
      else
        {
          pprev=ptemp;
          ptemp=ptemp->pnext;
        }
    }
    return 2;
  }
}
```
### Single Linked list Full Program 
```c
#include<stdio.h>
#include<stdlib.h>
#define FOREVER 1
typedef int int4_t;
typedef void void0_t;

typedef struct sll
{
  int4_t data;
  struct sll *pnext;
}sll_t;

sll_t *middle_node(sll_t *pHead);
int4_t destroy_entire_list(sll_t **ppHead);
int4_t destroy_from_nth_node(sll_t **ppHead,int4_t n);
int4_t add_at_begining(sll_t **pphead,int4_t data);
int4_t count(sll_t *phead);
void0_t display(sll_t *phead);
sll_t *linearsearch(sll_t *phead,int4_t key);
int4_t delete(sll_t **pphead,int4_t key);
int4_t deleteN(sll_t **pphead,int4_t n);
int4_t addN(sll_t **pphead,int4_t n,int4_t data);
sll_t *loop(sll_t *pHead);
sll_t *remove_loop(sll_t *pHead);
sll_t *create_loop(sll_t *pHead,int4_t n);
sll_t *last_but_nth_node(sll_t *pHead,int4_t n);
sll_t *one_third_node(sll_t *pHead);
sll_t *x_by_yth_node(sll_t *pHeadi,int4_t x,int4_t y);
int4_t remove_dups_in_sorted_list(sll_t *pHead);

int4_t main(void0_t)
{
  sll_t *phead1=NULL,*phead2=NULL;
  sll_t *phead=NULL,*ptail=NULL,*pfound=NULL;

  int4_t op,key,data,c,n;
  int4_t ret;
  int4_t x,y;
  while(FOREVER)
  {
    printf("enter 0: for exit\n");
    printf("enter 1: for add note at begining\n");
    printf("enter 2: for cout\n");
    printf("enter 3: for display\n");
    printf("enter 4: for linear search\n");
    printf("enter 5: for delete\n");
    printf("enter 6: for delete nth node\n");
    printf("enter 7: for add node at nth node\n");
    printf("enter 8: destroy from nth node\n");
    printf("enter 9: destroy entire list\n");
    printf("enter 10: find middle node\n");
    printf("enter 11: find 1/3rd node\n");
    printf("enter 12: find x/yth node\n");
    printf("enter 13: find last but nth node\n");
    printf("enter 14: remove dups from sorted list\n");
    printf("enter 15: create loop at nth node\n");
    printf("enter 16: find loop or not\n");
    printf("enter 17: remove loop\n");
    printf("enter option:");
    scanf("%d",&op);
    switch(op)
    {
      case 0:
         exit(0);

      case 1:
         printf("enter data:");
         scanf("%d",&data);
         add_at_begining(&phead,data);
         break;

      case 2:
         c=count(phead);
         printf("the no of nodes count=%d\n",c);
         break;

      case 3:
         display(phead);
         break;

      case 4:
         printf("enter key for to search");
         scanf("%d",&key);
         pfound=linearsearch(phead,key);
         if(pfound==NULL)
         {
           printf("the node with ey is not found=%d\n",key);
         }
         else
         {
           printf("the node with key is found=%d=%p\n",key,pfound);
         }
         break;

      case 5:
         printf("enter key to delete");
         scanf("%d",&key);
         delete(&phead,key);
         break;

      case 6:
         printf("Enter n:");
         scanf("%d",&n);
         deleteN(&phead,n);
         break;

      case 7:
         printf("Enter n:");
         scanf("%d",&n);
         printf("enter data:");
         scanf("%d",&data);
         addN(&phead,n,data);
         break;

      case 8:
         printf("Enter n:");
         scanf("%d",&n);
         ret=destroy_from_nth_node(&phead,n);
         if(ret == -1)
         {
           printf("Empty Linked List\n");
         }
         if(ret == -2)
         {
           printf("Linked List having less number of nodes than %d\n",n);
         }
         if(ret==0)
         {
           printf("successfully destroyed nodes from %d\n",n);
         }
         break;

      case 9:
         ret=destroy_entire_list(&phead);
         if(ret == -1)
         {
           printf("Empty Linked List\n");
         }
         if(ret==0)
         {
           printf("successfully destroyed entire list\n");
         }
         break;

      case 10:
         pfound=middle_node(phead);
         if(pfound == NULL)
         {
           printf("No middle node\n");
         }
         else
         {
           printf("middle node at %p and data=%d\n",pfound,pfound->data);
         }
         break;

      case 11:
         pfound=one_third_node(phead);
         if(pfound == NULL)
         {
           printf("No 1/3rd node\n");
         }
         else
         {
           printf("1/3rd node at %p and data=%d\n",pfound,pfound->data);
         }
         break;

      case 12:
         printf("Enter x,y:");
         scanf("%d%d",&x,&y);
         pfound=x_by_yth_node(phead,x,y);
         if(pfound == NULL)
         {
           printf("No %d/%d node\n",x,y);
         }
         else
         {
           printf("%d/%d node at %p and data=%d\n",x,y,pfound,pfound->data);
         }
         break;

      case 13:
         printf("Enter n:");
         scanf("%d",&n);
         pfound=last_but_nth_node(phead,n);
         if(pfound == NULL)
         {
           printf("No last but %dth node\n",n);
         }
         else
         {
           printf("last but %dth node at %p and data=%d\n",n,pfound,pfound->data);
         }
         break;

      case 14:
         ret=remove_dups_in_sorted_list(phead);
         if(ret == 1)
         {
           printf("Empty List\n");
         }
         else
         {
           printf("No dups in the final list\n");
         }
         break;

      case 15:
         printf("Enter the node number at which loop should exist:");
         scanf("%d",&n);
         pfound=create_loop(phead,n);
         if(pfound == NULL)
         {
           printf("can not create loop,because list does not have %d No of nodes.\n",n);
         }
         else
         {
           printf("loop started at node %d,address of node= %p and data=%d\n",n,pfound,pfound->data);
         }
         break;

      case 16:
         pfound=loop(phead);
         if(pfound == NULL)
         {
           printf("No loop.\n");
         }
         else
         {
           printf("loop at node %p and data=%d\n",pfound,pfound->data);
         }
         break;

      case 17:
         pfound=remove_loop(phead);
         if(pfound == NULL)
         {
           printf("No loop.\n");
         }
         else
         {
           printf("loop found at node %p and data=%d.loop is successfully removed.\n",pfound,pfound->data);
         }
         break;

      default:
         printf("Enter Correct Options\n");
    }
  }
}

sll_t *middle_node(sll_t *pHead)
{
  sll_t *pTemp1=pHead,*pTemp2=pHead;
  if((pHead == NULL)||(pHead->pnext == NULL))
  {
    return NULL;
  }
  while(pTemp1 !=NULL)
  {
    pTemp1=pTemp1->pnext;
    if((pTemp1 == NULL) || (pTemp1->pnext == NULL))
    {
      break;
    }
    pTemp1=pTemp1->pnext;
    pTemp2=pTemp2->pnext;
  }
  return pTemp2;

}

sll_t *create_loop(sll_t *pHead,int4_t n)
{
  sll_t *pTemp=pHead,*pLoopNode=NULL;
  if(pHead == NULL)
  {
    printf("Empty Linked List\n");
    return NULL;
  }
  if(n<=0)
  {
    printf("Enter n > 1\n");
    return NULL;
  }
  while(--n)
  {
    pTemp=pTemp->pnext;
    if(pTemp == NULL)
    {
      return NULL;
    }
  }
  pLoopNode=pTemp;
  while(pTemp->pnext !=NULL)
  {
    pTemp=pTemp->pnext;
  }
  pTemp->pnext=pLoopNode;
  return pLoopNode;
}

sll_t *loop(sll_t *pHead)
{
  sll_t *pTemp1=pHead,*pTemp2=pHead;
  if((pHead == NULL)||(pHead->pnext == NULL))
  {
    return NULL;
  }
  while(pTemp1 !=NULL)
  {
    pTemp1=pTemp1->pnext;
    if(pTemp1 == NULL)
    {
      return NULL;
    }
    pTemp1=pTemp1->pnext;
    pTemp2=pTemp2->pnext;
    if(pTemp1 == pTemp2)
    {
      return pTemp2->pnext;
    }
  }
  return NULL;

}

sll_t *remove_loop(sll_t *pHead)
{
  sll_t *pTemp1=pHead,*pTemp2=pHead;
  if((pHead == NULL)||(pHead->pnext == NULL))
  {
    return NULL;
  }
  while(pTemp1 !=NULL)
  {
    pTemp1=pTemp1->pnext;
    if(pTemp1 == NULL)
    {
      return NULL;
    }
    pTemp1=pTemp1->pnext;
    pTemp2=pTemp2->pnext;
    if(pTemp1 == pTemp2)
    {
      pTemp1=pTemp1->pnext;
      pTemp2->pnext=NULL;
      return pTemp1;
    }
  }
  return NULL;

}

sll_t *last_but_nth_node(sll_t *pHead,int4_t n)
{
  sll_t *pTemp1=pHead,*pTemp2=pHead;
  while(n)
  {
    if(pTemp1 == NULL)
    {
      return NULL;
    }
    pTemp1=pTemp1->pnext;
    --n;
  }
  if(pTemp1 == NULL)
  {
    return NULL;
  }
  while(pTemp1->pnext != NULL)
  {
    pTemp1=pTemp1->pnext;
    pTemp2=pTemp2->pnext;
  }
  return pTemp2;
}

sll_t *one_third_node(sll_t *pHead)
{
  int4_t i=2;
  sll_t *pTemp1=pHead,*pTemp2=pHead;
  if(pHead == NULL)
  {
    return NULL;
  }
  while(i)
  {
    pTemp1=pTemp1->pnext;
    if(pTemp1 == NULL)
    {
      return NULL;
    }
    i--;
  }
  while(pTemp1 !=NULL)
  {
    pTemp1=pTemp1->pnext;
    if(pTemp1 == NULL)
    {
      break;
    }
    pTemp1=pTemp1->pnext;
    if(pTemp1 == NULL)
    {
      break;
    }
    pTemp1=pTemp1->pnext;
    pTemp2=pTemp2->pnext;
  }
  return pTemp2;
}

sll_t *x_by_yth_node(sll_t *pHead,int4_t x,int4_t y)
{
  sll_t *pTemp1=pHead,*pTemp2=pHead;
  int4_t i=y-1,j=x-1;
  if(pHead == NULL)
  {
    return NULL;
  }
  while(i)
  {
    pTemp1=pTemp1->pnext;
    if(pTemp1 == NULL)
    {
      return NULL;
    }
    if(j)
    {
      pTemp2=pTemp2->pnext;
      --j;
    }
    --i;
  }
  while(pTemp1 !=NULL)
  {
    i=y,j=x;

    while(i)
    {
      pTemp1=pTemp1->pnext;
      if(pTemp1 == NULL)
      {
        break;
      }
      if(j)
      {
        pTemp2=pTemp2->pnext;
        --j;
      }
      --i;
    }
  }
  return pTemp2;
}

int4_t remove_dups_in_sorted_list(sll_t *pHead)
{
  sll_t *pTemp=pHead,*pPrev=NULL;
  if(pHead == NULL)
  {
    return 1;
  }
  else
  {
    pPrev=pTemp;
    pTemp=pTemp->pnext;
  }
  while(pTemp != NULL)
  {
    if(pPrev->data == pTemp->data)
    {
      pPrev->pnext = pTemp->pnext;
      free(pTemp);
      pTemp=pPrev->pnext;
    }
    else
    {
      pPrev=pTemp;
      pTemp=pTemp->pnext;
    }
  }
  return 0;
}


int4_t destroy_from_nth_node(sll_t **ppHead,int4_t n)
{
  sll_t *pTemp=*ppHead;
  sll_t *pPrev=NULL;
  int4_t i=1;
  if(*ppHead == NULL)
  {
    return -1;
  }
  while(i<n)
  {
     pPrev=pTemp;
     pTemp=pTemp->pnext;
     if(pTemp == NULL)
     {
        break;
     }
     i++;
  }
  if(i < n)
  {
    return -2;
  }
  while(pTemp != NULL)
  {
    if(pPrev !=NULL)
    {
      pPrev -> pnext = pTemp->pnext;
    }
    else
    {
      *ppHead=pTemp->pnext;
    }
    free(pTemp);
    if(pPrev !=NULL)
    {
      pTemp=pPrev->pnext;
    }
    else
    {
      pTemp=*ppHead;
    }
  }
  return 0;
}


int4_t destroy_entire_list(sll_t **ppHead)
{
  sll_t *pTemp=*ppHead;
  if(*ppHead == NULL)
  {
    return -1;
  }
  while(pTemp != NULL)
  {
    *ppHead=pTemp->pnext;
    free(pTemp);
    pTemp=*ppHead;
  }
  return 0;
}

int4_t add_at_begining(sll_t **pphead,int4_t data)
{
  sll_t *pnew=NULL;
  pnew=(sll_t *)malloc(sizeof(sll_t));
  if (pnew==NULL)
  {
    return 1;
  }
  pnew->data=data;
  pnew->pnext=*pphead;
  *pphead=pnew;
}

int4_t count(sll_t *phead)
{
  sll_t *ptemp=phead;
  int4_t count=0;
  while(ptemp!=NULL)
  {
    count++;
    ptemp=ptemp->pnext;
  }
  return count;
}

void0_t display(sll_t *phead)
{
  sll_t *ptemp=phead;
  while(ptemp!=NULL)
  {
   printf("%d\n",ptemp->data);
   ptemp=ptemp->pnext;
  }
}

sll_t *linearsearch(sll_t *phead,int4_t key)
{
  sll_t *ptemp=phead;
  while(ptemp!=0)
  {
    if(ptemp->data=key)
    {
      return ptemp;
    }
    else
    {
      ptemp=ptemp->pnext;
    }
  }
  return NULL;
}

int4_t delete(sll_t **pphead,int4_t key)
{
  sll_t *ptemp=*pphead,*pprev;
  if(*pphead==NULL)
  {
    return 1;
  }
  else
  {
    while(ptemp!=NULL)
    {
      if (ptemp->data==key)
      {
        if (ptemp==*pphead)
        {
          *pphead=ptemp->pnext;
        }
        else
        {
            pprev->pnext=ptemp->pnext;
        }
        free(ptemp);
        return 0;
      }
      else
        {
          pprev=ptemp;
          ptemp=ptemp->pnext;
        }
    }
    return 2;
  }
}

int4_t deleteN(sll_t **pphead,int4_t n)
{
  sll_t *ptemp=*pphead,*pprev=NULL;
  if(n>0)
  {
    if(*pphead == NULL)
    {
      return 2;
    }
    while(--n)
    {
      pprev=ptemp;
      ptemp=ptemp->pnext;
      if(ptemp==NULL)
      {
        return 3;
      }
    }
    if(ptemp == *pphead)
    {
      *pphead=ptemp->pnext;
    }
    else
    {
      pprev->pnext=ptemp->pnext;
    }
    free(ptemp);
    return 0;
  }
  else
  {
    return 1;
  }

}

int4_t addN(sll_t **pphead,int4_t n,int4_t data)
{
  sll_t *ptemp=*pphead,*pnew=NULL;
  if(n<0)
  {
    return 1;
  }

  pnew=(sll_t *)malloc(sizeof(sll_t));
  if (pnew==NULL)
  {
    return 4;
  }
  pnew->data=data;
  if(n==0)
  {
    pnew->pnext=*pphead;
    *pphead=pnew;
    return 0;
  }
  while(--n)
  {
    ptemp=ptemp->pnext;
    if(ptemp==NULL)
    {
      free(pnew);
      return 2;
    }
  }
  pnew->pnext=ptemp->pnext;
  ptemp->pnext=pnew;
  return 0;
}
                                                                                                                                                                   
```
