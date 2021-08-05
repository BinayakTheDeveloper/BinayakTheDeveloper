/*My First ATM Project*/
#include <stdio.h>
#include <windows.h>
void pin()
{
	int pin;
	
		system("color 0");
		printf("\033[0;32m");
		printf("\t\t\t===============Welcome To BINAYMITRA ATM===============");
		printf("\033[2;31m");
		printf("\n\n\t\t\t\t{The Security Pin For Everyone Is 1234}\n\n");
	
		do
		{
			printf("\033[0;34m");
			printf("Enter The Security Pin To Start The Transaction: ");
			scanf("%d",&pin);
	
			if(pin!=2005)
			{
				printf("\033[0;31m");
				printf("\nThe PIN You Entered Is Wrong! Please Try Again...\n\n");
			}
		
			else
			{
				printf("\033[0;32m");
				printf("\nThe PIN You Entered Is Correct. Please Proceed...\n");
			}
		}while(pin!=2005);
}

	
void transaction(int bal)
{
	int ch;
	int ad,at=1,withdraw;
	
	printf("\n********Welcome to ATM Service**************\n");
	printf("Enter The Operation To Be Served...");
	printf("\n1. Deposit");
	printf("\n2. Withdraw");
	printf("\n3. Balance Enquiry");
	printf("\n4. Quit\n");
	printf("********************************************\n");
	scanf("%d",&ch);
	
	switch(ch)
	{
		case 3:
		printf("Your Available Balance Is:%d",bal);
		
		printf("\n\nDo You Want Another Transaction?\n1. Agree\n2. Deny\n");
		scanf("%d",&at);
		
		if(at == 1)
		{
			transaction(bal);
		}
		else if(at == 2)
		{
			printf("Thanks For Using Our ATM Services...");
		}
		break;
		
		case 2:
			printf("\n Enter The Amount To Withdraw: ");
			scanf("%d", &withdraw);
			
			if (withdraw >bal)
			{
				printf("\n INSUFFICENT BALANCE !!!");
				
				printf("\nDo You Want Another Transaction?\n1. Agree\n2. Deny\n");
				scanf("%d",&at);
				
				if(at == 1)
				{
					transaction(bal);
				}
				else if(at == 2)
		{
			printf("Thanks For Using Our ATM Services...");
		}
			}
			else
			{
				bal = bal - withdraw;
				printf("\n\n Please Collect Cash");
				printf("\n Your Available Balance Is: %d",bal);
				
				printf("\n\nDo You Want Another Transaction?\n1. Agree\n2. Deny\n");
				scanf("%d",&at);
				
				if(at == 1)
				{
					transaction(bal);
				}
				else if(at == 2)
		{
			printf("Thanks For Using Our ATM Services...");
		}
			}
			break;
		
		case 1:
		printf("\nEnter The Amount To Deposit:");
		scanf("%d",&ad);
		
		bal = bal + ad;
		printf("\nYou Deposited RS %d\n\nYour Available Balance Is %d",ad,bal);
		
		printf("\n\nDo You Want Another Transaction?\n1. Agree\n2. Deny\n");
		scanf("%d",&at);
		
		if(at == 1)
		{
			transaction(bal);
		}
		else if(at == 2)
		{
			printf("Thanks For Using Our ATM Services...");
		}
		break;
		
		default:
		{
			printf("\nInvalid Choice...");
			
			printf("\n\nDo You Want Another Transaction?\n1. Agree\n2. Deny\n");
		scanf("%d",&at);
		
		if(at == 1)
		{
			transaction(bal);
		}
		else if(at == 2)
		{
			printf("Thanks For Using Our ATM Services...");
		}
		break;
		}
		case 4:
			printf("\n THANK U FOR USING OUR ATM SERVICE");
			break;
	}
}

int main()
{
	int balance=0;
	pin();
	transaction(balance);
}
