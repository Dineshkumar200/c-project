#                   plagiarism checker in  C



## DINESHKUMAR V
## 212220230013



```c



#include <stdio.h>
#include<string.h>
void check(char str1[],char str2[]);
int count=0;
int word=0;
int n=0;
int main()
{
    int sum=0;
   char str1[100000]={"The Brihadishvara Temple Also known as the Rajarajeshvara, after the king who built it, the Brihadishvara (or Brhadisvara) temple was constructed between c. 995 and 1025 CE using Chola war booty and tribute from Sri Lanka. The temple was dedicated to the Hindu god Shiva. Reaching a height of 63 metres, it is the tallest temple building in India. The entire rectangular complex measures approximately 140 x 75 metres and is surrounded by a wall with regular interior niches. Inside the compound are various secondary shrines and a monumental double gateway entrance (gopuras)."};
   char str2[100000]={"The gopuras at Thanjavur are two huge monumental gateways which lead to the compound dominated by the Brihadishvara temple. They are the earliest mature examples of the form in southern India. Built on the eastern side of the complex, the outer gopura has five stories and the inner one three. Each gopura has a centrally positioned entrance giving access to a single two-storied chamber on each side of it. The gopuras at Thanjavur are unique because each façade (interior and exterior) is not identical as in later examples. The outer facades each have two large dvarapalas (door guardians) as well as figure sculpture in their many niches and large decorative fan shapes. The top of each gopura is crowned with a massive shala or barrel-vaulted roof. Eventually at other sites gopuras would become even larger and more spectacular than the temples themselves."};
   int n1=strlen(str1);
   int n2=strlen(str2);
  
   
   int k=0;
  char str3[10000];
 
 
 
   for(int i=0;str1[i]!='\0';i++)
   {
       if(str1[i]!=' ')
       {
       str3[k]=str1[i];
         
         k++;
       }
      if(str1[i]==' '||i==n1-1)
       {
           
           
           if(strcmp(str3,"The")==0||strcmp(str3,"the")==0||strcmp(str3,"to")==0||strcmp(str3,"it")==0||strcmp(str3,"by")==0||strcmp(str3,"and")==0||strcmp(str3,"And")==0)
           {
               
               
           }
          else
          {
              word++;
           check(str3,str2);
          }
           for(int n=0;n<k;n++)
           {
               str3[n]=0;
           }
           k=0;
       }
       n++;
       
    }
    int s1=word/3;
    
    
    if(count>=s1)
    {
        printf("plagiarism");
    }
    else
    {
        printf("This is not plagiarism");
    }
    
    
    return 0;
}
void check(char str1[],char news[])
{ 
  
    int k=0;
    char str3[100];
    int n1=strlen(news);
    int n2=strlen(str1);
    
    
    for(int i=0;news[i]!='\0';i++)
   {
       
       if(news[i]!=' ')
       {
       str3[k]=news[i];
         
         k++;
       }
      if(news[i]==' '||i==n1-1)
       {
          
         
           if(strcmp(str3,str1)==0)
           {
               count++;
               
           }
           
           for(int n=0;n<k;n++)
           {
               str3[n]=0;
           }
           k=0;
       }
    }

}




```
