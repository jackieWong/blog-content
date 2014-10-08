next_permutation

	for(;;){
		BidirectionalIteratior ii = i;
		i --;
		if(*i < *ii) {
				BidirectionalIterator j = last;
				//find until *j>*i
				while( !(*i < *(--j)));
				iter_swap(i, j);
				reverse(ii, last);
				return true;
		}
		
		if ( i == first){
			reverse(first, last);
			return false;
		}
	}
						
						
						
						
prev_permutation
	for(;;) {
		Bidirectional ii = i;
		i--;
		
		if (*i > *ii) {
			BidirectionalIterator j = last;
				while(!(*i > *(--j)) ;
			iter_swap(i,j);
			reverse(ii, last);
			return true;
		}
		if( i == fist){
			reverse(first, last);
			return false;
		}
	}
	
	
	
	#include <vector>
	#include <iostream>
	#include <algorithm>
	using namespace std;
	
	int main()	
	{
		vector<int> iv;
		iv.push_back(4);
		iv.push_back(3);
		iv.push_back(2);
		iv.push_back(1);
	
		next_permutation(iv.begin(), iv.end());
	
		for(auto iter=iv.begin(); iter!= iv.end(); iter++) {
			cout << *iter;
		}

		return 0;
	}
	
	
如何生成k-th permutation 

1 2 3
1 3 2
2 3 1

1 2 3 4
1 2 4 3
1 3 2 4
1 3 4 2
1 4 2 3
1 4 3 2
2 1 3 4
2 1 4 3
2 3 1 4
2 3 4 1
2 4 1 3
2 4 3 1
3 1 2 4
3 1 4 2
3 2 1 4
3 2 4 1
3 4 1 2
3 4 2 1
4 1 2 3
4 1 3 2
4 2 1 3
4 2 3 1
4 3 1 2
4 3 2 1
