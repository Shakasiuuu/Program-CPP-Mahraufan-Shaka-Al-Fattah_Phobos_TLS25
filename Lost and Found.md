```cpp
#include <iostream>
#include <string>
#include <cctype>
using namespace std;

bool isVowel(char c) {
    c = tolower((unsigned char)c);
    return c=='a' || c=='e' || c=='i' || c=='o' || c=='u';
}

string myReverse(const string &s) {
    string r; r.resize(s.size());
    for (size_t i=0;i<s.size();++i) r[i] = s[s.size()-1-i];
    return r;
}

string encrypt(const string &w) {
    if (w.empty()) return "";
    string cons;
    for (char c : w) if (!isVowel(c)) cons.push_back(c);
    string rev = myReverse(cons);
    int ascii = static_cast<unsigned char>(w[0]);     
    string asciiStr = to_string(ascii);
    size_t pos = rev.size() / 2;
    return rev.substr(0,pos) + asciiStr + rev.substr(pos);
}

int main() {
    string word;
    cout << "Input word: ";
    if (!getline(cin, word)) return 0;
    cout << "Mesin kodenya adalah:";
    cout << encrypt(word) ;
    return 0;
}

