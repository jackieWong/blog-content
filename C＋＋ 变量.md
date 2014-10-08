C＋＋语言中变量
#include <iostream>
#include <string>
using namespace std;

int main()
{
	char str1[] = "hello world";
	char str2[] = "hello world";
	
	const char * str3 = "hello world";
	char * str4 = "ello world";
	char * str5 = "world";
	cout << "address of str3: " << static_cast<const void *>(str3) << endl;
	cout << "address of str4: " << static_cast<const void *>(str4) << endl;
	cout << "address of str5: " << static_cast<const void *>(str5) << endl;

	if (str1 == str2)
		cout << " str1 & str2 are same";
	if (str3 == str4)
		cout << "str3 & str4 are same";
	if (str3 == str5)
		cout << "str3 & str5 are same";

	string str;
	const int &i = 1;
	cout << i << endl;
	cout << "address of int1: " << static_cast<const void *>(&i) << endl;
	//if (&i == &(1))
	//	cout << "str3 are point to const string";

	cout << static_cast<const void *>(&"hello world") << endl;
	cout << static_cast<const void *>(&"a") << endl;
	cout << static_cast<const void *>(&("hello world" + str)) << endl;


	
	return 0;
}




#include <iostream>
using namespace std;

int main()
{
	int i = 1;
	int j = 1;
	char * p = "hello world";
	//cout << "address of reference i" << static_cast< int *> (&i) << endl;	
	const int& r0 = 1;
	const int& r1 = 1;
	//printf("%x\n", &r0);
	//printf("%x\n", &r1);
	//printf("%x\n", main);
	//printf("%x\n", &"hello world");
	//printf("%x\n", &i);
	//cout << static_cast<int *>(&main) << endl;
	cout << static_cast<const int *>(&r0) << endl;
	cout << static_cast<const int *>(&i) << endl;
	cout << static_cast<const int *>(&j) << endl;
	cout << static_cast<const void *>(p) << endl;
	cout << static_cast<const void *>(&p) << endl;
	
	cout << static_cast<const void *>(&"hello world") << endl;

	int value = 14;
	int & ri = value;
	
	cout << static_cast<const void *>(&value) << endl;
	cout << static_cast<const void *>(&ri) << endl;
	return 0;
}
