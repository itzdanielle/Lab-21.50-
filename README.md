# Lab-21.50-
#include <iostream>
using namespace std;

double spoolsOrdered (){
  int num;
  cout << "What is the number of spools ordered? " << endl;
  cin >> num;
  return num;
}
double spoolsInStock () {
int num;
cout << "What is the number of spools in stock? " << endl;
cin >> num;
return num;
}
double charges () {
double answer;
cout << "What is the amount? " << endl;
cin >> answer;
return answer; 
}
double displayTotal (double numOrdered, double numInStock, double& subtotal, double& total, double& shipping) {
   cout << "The number of " << numOrdered << " spools ready to ship from current stock" << endl;
  if (numOrdered > numInStock) { 
  double backOrder = numOrdered - numInStock;
  cout << "The number of " << backOrder << " spools on backorder " << endl;
  }
  subtotal = numOrdered * 100;
  cout << "Subtotal of $" << subtotal << " the portion ready to ship" << endl;
  total = ((numOrdered * shipping) + subtotal);
  cout << "$" << shipping << " Total shipping and handling charges on the portion ready to ship." << endl;
  cout << "$" << total << " Total of the order ready to ship." << endl;
  return total;
 
}

int main() {
double subtotal, total;
double shipping = 10;
string answer;
int numOrdered = spoolsOrdered();
int numInStock = spoolsInStock ();
cout << "Is there any special shipping or handling charges? " << endl;
cin >> answer;
if (answer == "yes" ) {
  shipping = charges (); 
}
displayTotal(numOrdered,numInStock,subtotal,total,shipping);


}
