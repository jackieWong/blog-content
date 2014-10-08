##array size
当把一个array作为参数传递给函数的时候，array就自动退化为pointer,所以下面的程序输出结果为：8, 4
int size(int a[])
{
	cout << sizeof(a);
	return sizeof(a);
}

int main() {
	int a[2];
	cout << sizeof(a) << endl;
	
	cout << size(a) << endl;
	
	return 0;
}