# Strings

      #Reverse a String using Recursion
#include <iostream>
using namespace std;

void Reverse(string s){
    if(s.size() == 0){ //base condition
        return;
    }
    string ros = s.substr(1);
    Reverse(ros);
    std::cout << s[0];
}
int main() {
    string a = "Shohaib";
    Reverse(a);
	// your code goes here
	return 0;
}

