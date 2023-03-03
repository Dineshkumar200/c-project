#  Siri/Google assistant in C program

## DINESHKUMAR V
## 212220230013


```c

#include <stdio.h>
#include<string.h>
char contact[][10]={"dinesh","kumaran","loghul","kumaravel","balaji","pradeep","tamizh","saran"};

void message(char s[]);
void call(char s[]);
void music();
int n=0;

int main()
{
    
    
    char str[100];
    char s[100];
    printf("     WELCOME !! Tell me what do you want?\n");
    
    scanf("%[^\n]s",str);
    
    int i=0;
    if(strcmp(str,"good morning")==0)
   {
       printf("Good Morning!!! Have a Nice Day");
   }
   if(strcmp(str,"good night")==0)
   {
       printf("Good Night!!! ");
   }
    while(str[i]!=0)
    {
        if(str[i]==' ')
        {
            break;
        }
        s[i]=str[i];
        i++;
        
    }
   if(strcmp(s,"call")==0)
   {
       call(str);
   }
   
    if(strcmp(s,"message")==0)
   {
       message(str);
   }
    if(strcmp(s,"play")==0)
   {
       music();
       
       
   }

}
void call(char s[])
{
    int flag=0;
  
  int csize=sizeof(contact)/sizeof(contact[0]);
 
    char revstr[100]={'\0'};
    char name[100]={'\0'};
  
    int n=strlen(s);
    int count=0;
    for(int i=n-1;i>=0;i--)
    {
        if(s[i]==' ')
        {
            break;
        }
        revstr[(n-1)-i]=s[i];
        count++;
        
        
    }
     
    for(int i=count-1;i>=0;i--)
    {
        name[(count-1)-i]=revstr[i];
        
        
    }
    
    int n3=strlen(name);
   
   
 for(int i=0;i<csize;i++)
   {
       
      if(strcmp(contact[i],name)==0)
      {
          
          printf("calling %s !!!!",name);
          flag=1;
      }
   }
   if(flag==0)
   {
       printf("%s not found in your contact list",name);
   }
    
}

void message(char s[])
{
    int flag=0;
   char mess[100];
  int csize=sizeof(contact)/sizeof(contact[0]);
 
    char revstr[100]={'\0'};
    char name[100]={'\0'};
   
    int n=strlen(s);
    int count=0;
    for(int i=n-1;i>=0;i--)
    {
        if(s[i]==' ')
        {
            break;
        }
        revstr[(n-1)-i]=s[i];
        count++;
        
        
    }
    for(int i=count-1;i>=0;i--)
    {
        name[(count-1)-i]=revstr[i];
        
        
    }
    int n3=strlen(name);
    
   
 for(int i=0;i<csize;i++)
   {
       
      if(strcmp(contact[i],name)==0)
      {
          printf("Enter the message you want to sent : ");
          scanf("%s",mess);
          printf("%s message sent !!!",mess);
          flag=1;
      }
   }
   if(flag==0)
   {
       printf("%s not found in your contact list",name);
   }
    
  
}

void music()
{
    
   char c[100];
   
    char song[100];
    
    int flag=1;
   char mu[][1000]={"munbae vaa","vaa vathi","tum tum","bodhai kanamae","neeyum naanum","thendral vanthu","engeyum epothum"};
    int csize=sizeof(mu)/sizeof(mu[0]);
   printf("\nwhich song you Want to play ? : ");
   scanf("\n%[^\n]s",song);
   
    printf("%s",song);
   if(strcmp(song,"next")==0)
   {
       if(n==csize-1)
       {
           printf("\n\n     %s playing...\n\n",mu[0]);
           n=0;
           flag=0;
       }
       else
       {
       printf("\n\n     %s playing...\n\n",mu[n+1] );
       flag=0;
       n=n+1;
       }
   }
   else if(strcmp(song,"prev")==0)
   {
       
       if(n==0)
       {
           printf("\n\n     %s playing...\n\n",mu[csize-1]);
           n=csize-1;
           flag=0;
       }
       else
       {
        printf("\n\n     %s playing...\n\n",mu[n-1] );
        flag=0;
        n=n-1;
       }
   }
   else
   {
   for(int i=0;i<csize;i++)
   {
       if(strcmp(mu[i],song)==0)
       {
           n=i;
         printf("\n\n    %s playing...\n\n",song );
         flag=0;
       }
       
   }
   }
   if(flag==1)
   {
       printf("This Music not in your play list!!!\n\n");
   }
   printf("Do You Want Play Again? \n\n");
   printf("Enter \"y\" or \"n\" \n\n");
   scanf("%s",c);
   
   if(strcmp(c,"y")==0)
   {
       music();
   }
   
}





```
