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
    return 0;
}

		#Replace pi in a string with 3.14
	
#include <iostream>
using namespace std;

void rePlacepi(string s){
    if(s.size() ==0){
        return;
    }
    if(s[0]=='p' && s[1] =='i'){
        std::cout << "3.14";
        rePlacepi(s.substr(2));
    }
    else{
        cout<<s[0];
        rePlacepi(s.substr(1));
    }
}
int main() {
    string abc = "pishahhipikhaipi";
    rePlacepi(abc);
	return 0;
}
