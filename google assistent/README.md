```c

#include <stdio.h>
#include<string.h>
char contact[][10]={"dinesh","kumaran","loghul","kumaravel","balaji","pradeep","tamizh","saran"};

void message(char s[]);
void call(char s[]);
void music(char s[]);
int main()
{
    char p;
    char str[100];
    char s[100];
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
       music(str);
       music(str);
       
   }

}
void call(char s[])
{
    int flag=0;
  
  int csize=sizeof(contact)/sizeof(contact[0]);
 
    char revstr[100];
    char name[100];
   
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
          
          printf("calling !!!!");
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
 
    char revstr[100];
    char name[100];
   
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

void music(char s[])
{
    char song[100];
    int flag=1;
   char mu[][100]={"mun","anb","don"};
    int csize=sizeof(mu)/sizeof(mu[0]);
   printf("which song? ");
   scanf("%s",song);
   for(int i=0;i<csize;i++)
   {
       if(strcmp(mu[i],song)==0)
       {
         printf("playing\n");
         flag=0;
       }
       
   }
   if(flag==1)
   {
       printf("not found");
   }
}



```

