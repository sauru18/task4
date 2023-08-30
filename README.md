#include<fstream>
#include<iostream>
#include<string>
using namespace std;

int main()
{
char filename[50],ch,str[2000];
int tot=0,i=0,tot_word=0;
ifstream fp;
cout<<"enter the name of file:";
cin>>filename;
fp.open(filename,ifstream::in);
if(!fp)
{
    cout<<"file doesn't exist";
    return 0;
}
while(fp>>noskipws>>ch)
{
    str[tot]=ch;
    tot++;
}
fp.close();
str[tot]='\0';
while(str[i]!='\0')
{
    if(str[i]=='\n')
    {
        if(str[i+1]!='\0' && str[i+1]!=' ')
        tot_word++;
        i++;
    }
    else if(str[i]!=' ')
    i++;
    else
    {
        if(str[i+1]!='\0' && str[i+1]!=' ')
        tot_word++;
        i++;
    }
}
cout<<endl<<"total words="<<tot_word;
cout<<endl;
return 0;
}
  
