Title: C++ 左值和右值
Date: 8/29/2014
Tags: c++, rvalue, lvalue


以下程序中，str1, str2永远是不同的地址，而str3,  str5是同样的地址,char str1[]  = "hello world"；开辟了空间，并且把"hello world"复制到里面。

	int main()
	{
		char str1[] = "hello world";
		char str2[] = "hello world";
		
		char *str3 = "hello wrold";
		char *str4 = "hello";
		char *str5 = "hello wrold";
	
		if (str1 == str2)
			cout << "str1 & str2 are same";
	
		if (str3 == str5)
			cout << "str3 & str5 are same";
		
		return 0;
	}


&(“adc” + string);



	int & foo(){
		cout << 1234;
	}
	
	这个函数可以被调用，只是返回值不确定，返回值应该是预先分配的吧，其机制是什么样子的？


引用从语言级别上来说，就是对象的别名，可以用在函数参数，和函数返回值。

但是从实现上来说，引用只是语法糖，可以采用指针实现；当对引用变量初始化的时候，赋给它的值自动被取地址；当使用引用变量的时候，自动被解引用。

### &("hello world") &('h') &(12345)
这就是为什么它被叫做立即数，没有地址，直接由寄存器产生。字符终究也是一个数字的表示
但是字符串是不一样的，”hello world”被放入到了内存中。


### 数字常量与&
下面的语法会报错：

	int & i = 1;

但是，这个语法并不会报错：
	
	const int & i = 1;
**const type &把右值的生存期延长到了和引用一样的长度。**

### i＋＋ & ＋＋i 与左值和右值
i＋＋返回的是一个右值：建立i的一个临时变量，对i进行＋＋，返回临时变量
++i返回的是一个左值 ：对i进行＋＋，返回i的引用



	#include <iostream>
	using namespace std;
	class T {
		public:
			 T() { cout << "construct" << endl;
			 T(int) { cout << "construct 1" << endl;}
			~T() { cout << "destory" << endl; }
	};
	
	int main()
	{
		{
			const T & rt = T();
			cout << " des it delay"<<endl;
		}
		
		{
			T();
			cout << "doest not delay" << endl;
		}
	}
	


### 
	
	class T{
		public: 
			T() { cout << "constuct" << endl; }
			T(int) { cout << "construct with integer parameters" << endl; }
			~T() { cout << "destory" << endl;}
	}
	
	int main()
	{
		{
			T();
			cout << " after statement";
		}
		
		{
			T(1);
		}
	}
	
T() T(1)产生的对象的生存期只存在一句话中，
	coustuct
	construct with integer parameters
	after statement
	

