#include<conio.h>
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<ctype.h>
#define size 100
char Name[size][30],Address[size][30],DOB[size][30],Class[size][30],Section[size],Gender[size]; 
int Roll[size],ind;
double Mobile[size];
void Insert()
{ 
	printf("Enter Name:"); 
	fflush(stdin);
	gets(Name[ind]);
	printf("Enter Class:"); 
	fflush(stdin);
	gets(Class[ind]); 
	printf("Enter Roll:"); 
	fflush(stdin);
	scanf("%d",&Roll[ind]); 
	printf("Enter Section:"); 
	fflush(stdin);
	scanf("%c",&Section[ind]); 
	printf("Enter Address:"); 
	fflush(stdin);
	gets(Address[ind]);
	printf("Enter DOB:");
	fflush(stdin);
	gets(DOB[ind]);
	printf("Enter Gender:");
	fflush(stdin);
	scanf("%c",&Gender[ind]);
	printf("Enter Mobile:"); 
	fflush(stdin);
	scanf("%lf",&Mobile[ind]);  
		
}
void Show()
{ 
	int a;
	printf("\n---------------------------------------------------------DETAILS--------------------------------------------------------");
	printf("\n%15s %15s %15s %15s %15s %15s %5s %15s","Name","Class","Roll","Section","Address","DOB","Gender","Mobile");
	printf("\n------------------------------------------------------------------------------------------------------------------------");
	for(a=0;a<ind;a++)
	{
		printf("\n%15s %15s %15d %15c %15s %15s %5c %15.0lf",Name[a],Class[a],Roll[a],Section[a],Address[a],DOB[a],Gender[a],Mobile[a]);
		printf("\n------------------------------------------------------------------------------------------------------------------------");
	}

}
void Search()
{ 
	char class1[5],section; 
	int roll,a,S;
	printf("\n[1]. Search By Class."); 
	printf("\n[2]. Search By All.");
	printf("\nEnter Your Choice:");
	scanf("%d",&S); 
	if(S==1)
	{			
		int f=0;
		printf("\nEnter Class:");
		fflush(stdin);  
		gets(class1); 
		for(a=0;a<ind;a++)
		{	
			if(strcmpi(Class[a],class1)==0)
			{ 
				printf("\n%15s %15s %15s %15s %15s %15s %5s %15s","Name","Class","Roll","Section","Address","DOB","Gender","Mobile");
				printf("\n%15s %15s %15d %15c %15s %15s %5c %15.0lf",Name[a],Class[a],Roll[a],Section[a],Address[a],DOB[a],Gender[a],Mobile[a]);
				f=1;
				break;
			}
			
		}
		if(f==0)
			printf("Data is not found"); 
	}
	else if(S==2)
	{
		int f=0;
		printf("\nEnter Class:");
		fflush(stdin);  
		gets(class1); 
		printf("\nEnter Roll:");
		fflush(stdin);  
		scanf("%d",&roll); 
		printf("\nEnter Section:");
		fflush(stdin); 
		scanf("%c",&section); 
		for(a=0;a<ind;a++)
		{	
			if(Roll[a]==roll&&toupper(Section[a])==toupper(section)&&strcmpi(Class[a],class1)==0)
			{	 
				printf("\n%15s %15s %15s %15s %15s %15s %5s %15s","Name","Class","Roll","Section","Address","DOB","Gender","Mobile");
				printf("\n%15s %15s %15d %15c %15s %15s %5c %15.0lf",Name[a],Class[a],Roll[a],Section[a],Address[a],DOB[a],Gender[a],Mobile[a]);
				f=1;
				break;
			}		
		}
		if(f==0)
			printf("Data is not found"); 
	}
	
}
void Update()
{ 
	char class1[5],section; 
	int roll,a,S,f=0,ind2;
	printf("\nEnter Class:");
	fflush(stdin);  
	gets(class1); 
	printf("\nEnter Roll:");
	fflush(stdin);  
	scanf("%d",&roll); 
	printf("\nEnter Section:");
	fflush(stdin); 
	scanf("%c",&section); 
	for(a=0;a<ind;a++)
		{	
			if(Roll[a]==roll&&toupper(Section[a])==toupper(section)&&strcmpi(Class[a],class1)==0)
			{	 
				printf("\n%15s %15s %15s %15s %15s %15s %5s %15s","Name","Class","Roll","Section","Address","DOB","Gender","Mobile");
				printf("\n%15s %15s %15d %15c %15s %15s %5c %15.0lf",Name[a],Class[a],Roll[a],Section[a],Address[a],DOB[a],Gender[a],Mobile[a]);
				ind2=a;
				f=1;
				break;
			}
		}
	if(f==0)
		printf("Data is not found"); 
	else
	{
		printf("\n[1]. Update Name."); 
		printf("\n[2]. Update Class.");
		printf("\n[3]. Update DOB.");
		printf("\n[4]. Update Mobile.");
		printf("\nEnter Your Choice:");
		fflush(stdin);
		scanf("%d",&S); 
		if(S==1)
		{
			char NN[30];
			printf("Enter New Name:");
			fflush(stdin); 
			gets(NN);
			strcpy(Name[ind2],NN);
			printf("Name is succesfully updated");   
		}
		else if(S==2)
		{
			char cs[5];
			printf("Enter New Class:");
			fflush(stdin);
			gets(cs);
			strcpy(Class[ind2],cs);
			printf("Class is succesfully updated.");
		}
		else if(S==3)
		{
			char dob[30];
			printf("Enter New DOB:");
			fflush(stdin);
			gets(dob);
			strcpy(DOB[ind2],dob);
			printf("DOB is succesfully updated");
		}
		else if(S==4)
		{
			double mob;
			printf("Enter New Mobile:");
			fflush(stdin);
			scanf("%lf",&mob);
			Mobile[ind2]=mob;
			printf("Mobile is succesfully updated");			
		}
	}
}
void Delete()
{
	char class1[5],section; 
	int roll,a,S,f=0,ind2;
	printf("\nEnter Class:");
	fflush(stdin);  
	gets(class1); 
	printf("\nEnter Roll:");
	fflush(stdin);  
	scanf("%d",&roll); 
	printf("\nEnter Section:");
	fflush(stdin); 
	scanf("%c",&section); 
	for(a=0;a<ind;a++)
		{	
			if(Roll[a]==roll&&toupper(Section[a])==toupper(section)&&strcmpi(Class[a],class1)==0)
			{	 
				printf("\n%15s %15s %15s %15s %15s %15s %5s %15s","Name","Class","Roll","Section","Address","DOB","Gender","Mobile");
				printf("\n%15s %15s %15d %15c %15s %15s %5c %15.0lf",Name[a],Class[a],Roll[a],Section[a],Address[a],DOB[a],Gender[a],Mobile[a]);
				ind2=a;
				f=1;
				break;
			}
		}
	if(f==0)
		printf("Data is not found"); 
	else
	{
		char YN; 
		int b;
		printf("\nAre you sure to delete the record(Y/N)?"); 
		fflush(stdin);
		scanf("%c",&YN); 
		if(YN=='Y'||YN=='y')
		{ 
			for(b=ind2;b<ind;b++)
			{
				strcpy(Name[b],Name[b+1]);
				strcpy(DOB[b],DOB[b+1]); 
				strcpy(Class[b],Class[b+1]); 
				strcpy(Address[b],Address[b+1]); 
				Section[b]=Section[b+1];
				Gender[b]=Gender[b+1]; 
				Roll[b]=Roll[b+1]; 
				Mobile[b]=Mobile[b+1];
			}
			ind--;
			printf("Record is succesfully deleted.");
		}
	}	
}		
int main()
{ 
	int ch;
	ind=0;
	do
	{
		printf("\n\t\t\t\t\tNAGARUKHRA HIGH SCHOOL[H.S]");
		printf("\n\t\t===================================MENUE==================================");
		printf("\n\t\t||\t\t\t\t[1]. Insert.\t\t\t\t||");
		printf("\n\t\t||\t\t\t\t[2]. Show list.\t\t\t\t||");
		printf("\n\t\t||\t\t\t\t[3]. Search.\t\t\t\t||");
		printf("\n\t\t||\t\t\t\t[4]. Update Details.\t\t\t||");
		printf("\n\t\t||\t\t\t\t[5]. Delete.\t\t\t\t||");
		printf("\n\t\t||\t\t\t\t[0]. Exit.\t\t\t\t||");
		printf("\n\t\t==========================================================================");
		printf("\n\n\t\t\tEnter Your Choise: ");
		fflush(stdin);
		scanf("%d",&ch); 
		switch(ch)
		{ 
			case 1:
				Insert(); 
				ind++;
				break; 
			case 2: 
				Show(); 
				break;
			case 3:
				Search(); 
				break;
			case 4:
				Update(); 
				break;
			case 5:
				Delete(); 
				break;
			case 0:
				break;
			default: 
				printf("Wrong Choice.");
		}	
	}while(ch!=0); 
	return(0);
}
