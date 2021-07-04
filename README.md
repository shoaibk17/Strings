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

	#Find First and last Occurance of an element in an Array.
	
#include <iostream>
using namespace std;
int FirstOcuur(int arr[], int n, int i, int key){
    if(i ==n){
        return -1;
    }
    if(arr[i] == key){
        return i;
    }
    return FirstOcuur(arr, n, i+1, key);
}
int lastOccur(int arr[], int n, int i, int key){
    if(i ==n){
        return -1;
    }
    int restArray = lastOccur(arr, n, i+1, key);
    if(restArray != -1){
        return restArray;
    }
    if(arr [i] == key){
        return i;
    }
    return -1;
}
int main() {
    int arr[] = {1,2,3,4,5,6,5,8};
    std::cout << FirstOcuur(arr, 8, 0, 5) << std::endl;
    std::cout << lastOccur(arr, 8, 0, 5) << std::endl;
	// your code goes here
	return 0;
}

	
		#Remove Duplicates in String
	
	
#include <iostream>
using namespace std;

string Removedup(string s){
    if(s.size() ==0){
        return "";
    }
    char ch = s[0];
    string ans = Removedup(s.substr(1));
    
    if(ch == ans[0]){
        return ans;
    }
    else{
        return ch+ans;
    }
}

int main() {
    std::cout <<Removedup("aaabbbccddee") << std::endl;
	// your code goes here
	return 0;
}

	Move all x in ths string to last
	
	
#include <iostream>
using namespace std;

string moveAllx(string s){
    if(s.size() ==0){
        return "";
    }
    char ch = s[0];
    string ans = moveAllx(s.substr(1));
    if(ch == 'x'){
        return ans+ch;
    }
    else{
        return ch+ans;
    }
}
int main() {
    std::cout << moveAllx("xjjhakhxxkhakxxxkhah") << std::endl;
	// your code goes here
	return 0;
}

	
	
	Return Sub-strings from a strings
	
#include <iostream>
using namespace std;

void subseQ(string s, string ans){
    if(s.size() ==0){
        std::cout << ans<<endl;
        return;
    }
    char ch = s[0];
    string ros = s.substr(1);
    subseQ(ros, ans);
    subseQ(ros,ans+ch);
}
int main() {
    subseQ("ABCD", "");
    
	// your code goes here
	return 0;
}

	
	Return subsrings with a ASCII value.
	
#include <iostream>
using namespace std;

void Substring(string s, string ans){
    if(s.size() == 0){
        std::cout << ans << std::endl;
        return;
    }
    char ch = s[0];
    int code = ch;
    string ros = s.substr(1);
    
    Substring(ros, ans);
    Substring(ros, ans+ch);
    Substring(ros, ans+to_string(code));
}
int main() {
    Substring("AB", "");
	return 0;
}

	
	Print all possible mutations from the string
	
	#include <iostream>
using namespace std;

void perMutation(string s, string ans){
    if(s.size() == 0){
        std::cout << ans << std::endl;
        return;
    }
    for(int i =0; i<s.size(); i++){
        char ch = s[i];
        string ros = s.substr(0, i) + s.substr(i+1);
        
        perMutation(ros, ans+ch);
    }
}
int main() {
    perMutation("ABDC", "");
	// your code goes here
	return 0;
}
