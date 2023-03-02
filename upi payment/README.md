```c

#include <stdio.h>
#include<string.h>
void sendmoney();
int contactcheck(long long int num);
int his[100];
char historyb[100];
int i=0;
void pnb(int a,char b);
void indian(int a,char b);
void state(int a,char b);
void send(int a);
void checkbal();
void history();
void recharge();
void jio();
void vodaphone();
void airtel();
int main()
{
  
     int n1;
   char n2;
   
    printf("Welcome !!!!!\n");
    while(1)
    {
    printf("Enter what do you want?\n");
   printf("1.send money\n2.check balance\n3.phone recharge\n4.History\n5.exit\n");
   scanf("%d",&n1);
   switch(n1)
   {
       case 1:
       sendmoney();
       break;
       case 2:
       checkbal();
       break;
       case 3:
       recharge();
       break;
       case 4:
       history();
       break;
       case 5:
       printf("Are you Exit : ");
       scanf("%s",&n2);
       break;
      
   }
   if(n2=='y')
   {
       break;
   }
    }
    return 0;
}
void sendmoney()
{
    char str[100];
    printf("Enter a Mobile number: ");
    long long int n;
    int a;
    scanf("%lld",&n);
    if(contactcheck(n))
    {
        
      printf("Enter Amount: ");
      scanf("%d",&a);
        
        send(a);
    }
    else
    {
        printf("This number is not in your contact list shall we proceed?   ");
        printf("Enter \"yes\" or \"no\"  :  ");
        scanf("%s",str);
        if(strcmp(str,"yes")==0)
        {
            printf("Enter Amount: ");
            scanf("%d",&a);
           send(a);
        }
        
    }
    
}
int contactcheck(long long int num)
{
    long long int n[]={9878994674,9878994675,9878994634,9878994624};
    int size=sizeof(n)/sizeof(n[0]);
    for(int i=0;i<size;i++)
   {
      if(num==n[i])
      {
          return 1;
      }
   }
   return 0;
}
void send(int a)
{
    
    int n;
   
    printf("Select your Bank\n");
     printf("1.pnb\n2.state bank\n3.indian bank\n");
     scanf("%d",&n);
      switch(n)
      {
          case 1:
          pnb(a,'s');
          break;
          case 2:
          state(a,'s');
          break;
          case 3:
          indian(a,'s');
          break;
      }

    
}
void pnb(int a,char b)
{
   char an[100];
   int upipin=3456;
   static int amount=1000000;
   int upi;
   amount=amount-a;
   if(b=='s')
   {
    if(a<=amount)
    {
        his[i]=-a;
        historyb[i]='p';
            i++;
            
        printf("Enter upi pin: ");
        scanf("%d",&upi);
        if(upi==upipin)
        {
            printf("money sent!!!\n");
           
            printf("Your balance is : %d\n",amount);
            
        }
        else
        {
            printf("upi wrong\n");
            pnb(a,b);
        }
    }
    else
    {
        printf("low balance\n");
        printf("Do you want to check another bank? ");
        printf("Enter \"yes\" or \"no\"");
        scanf("%s",an);
        if(strcmp(an,"yes")==0)
        {
            send(a);
            
        }
    }
   }
   
   else
   {
        printf("Enter upi pin: ");
        scanf("%d",&upi);
       if(upi==upipin)
        {
            printf("Your Balance is : %d\n",amount);
        }
        else
        {
            printf("upi wrong\n");
            pnb(a,b);
        }
   }
  
  
}
void state(int a,char b)
{
    char an[100];
   int upipin=3456;
   static int amount=50000;
  
   int upi;
   amount=amount-a;
   if(b=='s')
   {
    if(a<=amount)
    {
         his[i]=-a;
        historyb[i]='s';
            i++;
            
        printf("Enter upi pin: ");
        scanf("%d",&upi);
        if(upi==upipin)
        {
            printf("money sent!!!\n");
            
            printf("Your balance is: %d \n",amount);
        }
        else
        {
            printf("upi wrong\n");
            pnb(a,b);
        }
    }
    else
    {
        printf("low balance\n");
        printf("Do you want to check another bank?");
        printf("Enter \"yes\" or \"no\"");
        scanf("%s",an);
        if(strcmp(an,"yes")==0)
        {
            send(a);
            
        }
       
        
    }
   }
   
   
   else
   {
       printf("Enter upi pin: ");
        scanf("%d",&upi);
       if(upi==upipin)
        {
            printf("Your Balance is %d\n",amount);
        }
        else
        {
            printf("upi wrong\n");
            pnb(a,b);
        }
   }
    
}
void indian(int a,char b)
{
    
    
    char an[100];
   int upipin=3456;
   static int amount=50000;
   int upi;
   amount=amount-a;
   if(b=='s')
   {
    if(a<=amount)
    {
            his[i]=-a;
           historyb[i]='i';
            i++;
           
        printf("Enter upi pin: ");
        scanf("%d",&upi);
        if(upi==upipin)
        {
            printf("money sent!!!\n");
            
            printf("Your balance is: %d \n",amount);
        }
        else
        {
            printf("upi wrong\n");
            pnb(a,b);
        }
    }
    else
    {
         printf("low balance\n");
        printf("Do you want to check another bank?     ");
        printf("Enter \"yes\" or \"no\"  :  ");
        scanf("%s",an);
        if(strcmp(an,"yes")==0)
        {
            send(a);
            
        }
    }
   }
   
   else
   {
       printf("Enter upi pin: ");
        scanf("%d",&upi);
       if(upi==upipin)
        {
            printf("Your Balance is : %d\n\n",amount);
        }
        else
        {
            printf("upi wrong\n");
            pnb(a,b);
        }
   }
   
  
}
void checkbal()
{
     printf("Select your Bank\n");
     printf("1.pnb\n2.state bank\n3.indian bank\n");
     int n;
     scanf("%d",&n);
      switch(n)
      {
          case 1:
          pnb(0,'b');
          break;
          case 2:
          state(0,'b');
          break;
          case 3:
          indian(0,'b');
          break;
      }
}
void history()
{
     for(int j=0;j<i;j++)
     {
         if(historyb[j]=='p')
         {
             printf("Debit from pnb Bank       ");
         }
         if(historyb[j]=='s')
         {
             printf("Debit from state Bank     ");
         }
         if(historyb[j]=='i')
         {
             printf("Debit from indian Bank     ");
         }
         printf("%d\n",his[j]);
         
     }  
     
}
void recharge()
{
   char str[100];
    long long int n;
     int n1;
    printf("Enter a Mobile number: ");
   
    scanf("%lld",&n);
    if(contactcheck(n))
    {
        
      printf("enter your mobile network\n");
      printf("1.jio\n2.Airtel\n3.vodaphone\n");
    scanf("%d",&n1);
    switch(n1)
    {
        case 1:
        jio();
        break;
        case 2:
        airtel();
        break;
        case 3:
        vodaphone();
        break;
       
        
    }
      
    }
    else
    {
         printf("This number is not in your contact list shall we proceed?   ");
        printf("Enter \"yes\" or \"no\"  :  ");
        scanf("%s",str);
        if(strcmp(str,"yes")==0)
        {
            printf("enter your mobile network\n");
      printf("1.jio\n2.Airtel\n3.vodaphone\n");
    scanf("%d",&n1);
    switch(n1)
    {
        case 1:
        jio();
        break;
        case 2:
        airtel();
        break;
        case 3:
        vodaphone();
        break;
       
        
    }
            
        }
        
    }  
}
void jio()
{
    int n;
    
    printf("Select Your pack\n");
    printf("1.Data=2GB/day   Validity : 28 days Unlimited Call  $299\n");
    printf("2.Data=2.5GB/day   Validity : 90 days Unlimited Call  $899\n");
    printf("3.Data=1.5GB/day   Validity : 84 days Unlimited Call  $666\n");
    scanf("%d",&n);
    switch(n)
    {
        case 1:
        send(299);
        break;
        case 2:
        send(899);
        break;
        case 3:
        send(666);
        break;
        
    }
}
void airtel()
{
    int n;
    
    printf("Select Your pack\n");
    printf("1.Data=2GB/day   Validity : 98 days Unlimited Call  $749\n");
    printf("2.Data=2.5GB/day   Validity : 90 days Unlimited Call  $799\n");
    printf("3.Data=1.5GB/day   Validity : 24 days Unlimited Call  $315\n");
    scanf("%d",&n);
    switch(n)
    {
        case 1:
        send(749);
        break;
        case 2:
        send(799);
        break;
        case 3:
        send(315);
        break;
        
    }
}
void vodaphone()
{
    int n;
    
    printf("Select Your pack\n");
    printf("1.Data=1GB/day   Validity : 28 days Unlimited Call  $299\n");
    printf("2.Data=2.5GB/day   Validity : 365 days Unlimited Call  $2999\n");
    printf("3.Data=1.5GB/day   Validity : 84 days Unlimited Call  $666\n");
    scanf("%d",&n);
    switch(n)
    {
        case 1:
        send(299);
        break;
        case 2:
        send(2999);
        break;
        case 3:
        send(666);
        break;
        
    }
}


```
