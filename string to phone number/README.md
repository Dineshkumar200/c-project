
#                   Converting mobile number from string to integer in C

## DINESHKUMAR V
## 212220230013




```c
#include <stdio.h>
#include<string.h>
void check(char str[],int n);
int arr[1000];
int s=0;


int main()
{
    int tot=1;
   int k=0;
  char str1[100];
  char str2[20];
 scanf("%[^\n]s",str1);
  int n3=strlen(str1);
   for(int i=0;str1[i]!='\0';i++)
   {
       if(str1[i]!=' ')
       {
       str2[k]=str1[i];
         
         k++;
       }
      if(str1[i]==' '||i==n3-1)
       {
          
          
          if(strcmp(str2,"double")==0)
           {
               tot=2;
           }
            else if(strcmp(str2,"triple")==0)
           {
               tot=3;
           }
           else
           {
         
           check(str2,tot);
           tot=1;
           }
           for(int n=0;n<k;n++)
           {
               str2[n]=0;
           }
           k=0;
       }
}
printf("The number is : ");
  for(int j=0;j<s;j++)
   {
       printf("%d",arr[j]);
   }
   
return 0;

}
void check(char str[],int n)
{
   
   
   
   for(int i=1;i<=n;i++)
   {
       if(strcmp(str,"zero")==0)
    {
       
      arr[s]=0;
      s++;
    }
    if(strcmp(str,"one")==0)
    {
       
      arr[s]=1;
      s++;
    }
    if(strcmp(str,"two")==0)
    {
      arr[s]=2;
      s++;
    }
    if(strcmp(str,"three")==0)
    {
      arr[s]=3;
      s++;
    }
    if(strcmp(str,"four")==0)
    {
      arr[s]=4;
      s++;
    }if(strcmp(str,"five")==0)
    {
      arr[s]=5;
      s++;
    }
    if(strcmp(str,"six")==0)
    {
      arr[s]=6;
      s++;
    }
    if(strcmp(str,"seven")==0)
    {
      arr[s]=7;
     s++;
    }
    if(strcmp(str,"eight")==0)
    {
      arr[s]=8;
      s++;
    }
    if(strcmp(str,"nine")==0)
    {
      arr[s]=9;
      s++;
    }
   }
  
}

```
