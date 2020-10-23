#include<stdio.h>
#include<stdlib.h>
struct node
{
int data;
struct node * next;
}*head=NULL;
void insert_nodes();
void display();
void selection_sorting();
int main()
{
int choice;
while(1)
{
printf("enter choice :");
scanf("%d",&choice);

switch(choice)
{
case 1:insert_nodes();
break;
case 2: display();
break;

case 3: selection_sorting();
break;
case 4: exit(0);
break;
default:printf("wrong input");
break;
}
}
return 0;
}
void insert_nodes()
{
struct node *newnode,*temp;
newnode = (struct node*)malloc(sizeof(struct node));
printf("enter data: ");
scanf("%d",&newnode->data);
newnode->next=NULL;
if(head==NULL)
{
head=newnode;
}
else
{
temp=head;
while(temp->next!=NULL)
{

temp=temp->next;
}
temp->next=newnode;
}
}
void display()
{
struct node *temp;
if(head==NULL)
{
printf("\nList is empty:\n");
return;
}
else
{
temp=head;
printf("\nThe List elements are:\n");
while(temp!=NULL)
{
printf("%d\t",temp->data );
temp=temp->next ;
}
}
printf("\n");
}
void selection_sorting()

{
struct node *ptr,*cpt;
int temp;
ptr= head;
while(ptr->next!=NULL)
{
cpt = ptr->next;
while(cpt!=NULL)
{
if(ptr->data > cpt->data)
{
temp = ptr->data;
ptr->data = cpt->data;
cpt->data = temp;
}
cpt= cpt->next;
}
ptr = ptr->next;
}
}
