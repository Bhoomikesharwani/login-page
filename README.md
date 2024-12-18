# login-page
#include<iostream>
#include<fstream>
using namespace std;

class temp{
string userName,Email,Password;
fstream file;
public:
void Login();
void Singup();
void Forgetpassword();
}obj;

int main(){
char choice;
cout<<"\n1- Login";
cout<<"\n2- Sign-up";
cout<<"\n3- Forget Password";
cout<<"\n4-Exit";
cout<<"\n Enter your choice ::";
cin>>choice;
switch (choice){
case '1':
obj.Login();

break;
case'2':
obj.Singup();

break;
case'3':
obj.Forgetpassword();

break;
case'4':
return 0;

break;
dafault:
cout<<"Invalid selection...!";
}
}
void temp::Singup(){
cout<<"\n enter your user Name::";
getline(cin,userName);
cout<<"Enter your Email Address ::";
getline(cin,Email);
cout<<"Enter your password::";
getline(cin,Password);

file.open("logic.txt",ios::out|ios :: app);
file<<userName<<"*"<<Email<<"*"<<Password<<endl;
file.close();
}
void temp::Login(){
string searchName,searchPass;
cout<<"..........Login..........."<<endl;
cout<<"Enetr your user Name ::"<<endl;
getline(cin,searchName);
cout<<"Enter your password ::"<<endl;
getline(cin,searchPass);

file.open("LoginData.txt",ios ::in);
getline(file,userName,'*');
getline(file,Email,'*');
getline(file,Password,'\n');
while(!file.eof()){

if(userName==searchName){
if(Password==searchPass){
cout<<"\nAccount Login Succesfull..!";
cout<<"\nuserName::"<<userName<<endl;
cout<<"\nEmail ::"<<Email<<endl;
}
}
getline(file,userName,'*');
getline(file,Email,'*');
getline(file,Password,'\n');
cin.ignore();
}
file.close();
}
void temp ::Forgetpassword (){

cout<<"\n Enter your user Name ::";
getline(cin,searchName);

cout<<"\n Enter your Email Address ::";
getline(cin,searchEmail);

file.open("LoginData.txt",ios ::in);
grtline(file,username,'*');
getline(file,Email,'*');
getline(file,password,'\n');
while(!file.eof()){
if(userNmae == searchName){
if(Email == searchEmail){
cout<<"\nAccount found...!"<<endl;
cout<<"\n Your Password::"<< Password<<endl;
}else{
cout<<"Not found...!\n"
}
else{
cout<<"\nNot found...!\n"
}
}
}
file.close();
}
