# S.I.cpp
//long-term fixed deposit system
#include <iostream>
using namespace std;

class Fixed_deposit
{
  long int P_amount;
  int years;
  float Rate;
  float  R_value;

public:
     Fixed_deposit(){ }
     Fixed_deposit(long int P,int Y,float r=0.12);
     Fixed_deposit(long int P,int Y,int r);
     void display(void);
};

Fixed_deposit :: Fixed_deposit (long int P,int Y,float r)
{
  P_amount = P;
  years = Y;
  Rate = r;
  R_value = P_amount;
  for(int i = 1; i <= Y; i++)
      R_value = R_value * (1.0 + r);
}
Fixed_deposit :: Fixed_deposit (long int P,int Y,int r)
{
    P_amount = P;
  years = Y;
  Rate = r;
  R_value = P_amount;
  for(int i = 1; i <= Y; i++)
    R_value = R_value* (1.0+float (r)/100);
}

void Fixed_deposit :: display(void)
{
  cout << "\n"
       << "principal Amount = " <<P_amount << "\n"
       << "Return value = " <<R_value <<"\n";
       
}
int main()
{
  Fixed_deposit FD1, FD2 ,FD3;
  long int P; //pricipal amount
  

int   Y;
float r;
int R;

// that is a break the line by comment...!
cout << "Enter amount, Period,interest rate(in percent)"<<"\n";
cin >> P >> Y >> R;
FD1 =Fixed_deposit(P,Y,R);

cout << "Enter amount, Period,interest rate(decimal form)"<<"\n";
cin >> P >> Y >> R;
FD2 =Fixed_deposit(P,Y,R);

cout << "Enter amount and Period"<<"\n";
cin >> P >> Y;
FD3 =Fixed_deposit(P,Y);

cout << "\nDeposit 1";
FD1.display();

cout << "\nDeposit 2";
FD2.display();

cout << "\nDeposit 3";
FD3.display();

return 0;

//programme ending 


}
