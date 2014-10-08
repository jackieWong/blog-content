## word break I & word break II
问题1： 判断字符串"catsanddog" 能否用集合["cat", "cats", "and", "sand","dog"]分解
问题2: 在1的基础上，给出所有的可能组合

**word break 1**
把字符串转换成为树结构，树的节点代表下一个单词的起始位置，两个节点间的边代表单词
所以“catsanddog” 0 --> 3 --> 7 --> 10
0--> 4 --> 7 --> 10

思路：
	1 利用一个队列，进行BFS。
	2 如果找到一个节点，节点值为字符串长度，则返回true
	3 为了避免对节点的重复查找，添加unordered_set<int> visited, 表示已经访问过的节点
		cat sand, cats and 访问过后都会对7节点继续访问
		
	bool wordBreak(sting s, unordered_set<string> &dict){
		queue<int> BFS;
		unordered_set<int> visited;
		BFS.push(0);
		
		while(!BFS.empty()){
			int start = BFS.front();
			BFS.pop();
			
			if(visited.find(start) == visited.end()){
				for(int j = start; j < s.size(); j++){
					string tmp = string(s, start, j-start+1);
					if(dict.find(tmp) != dict.end()){
						BFS.push(j+1);
						if(j+1 == s.size()) return true;
					
					}
				}
			}
		}
		
		return false;
	}
	
	

**word break 2**
这个题目特别坑，原因在于，有一个测试"aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaab" ["a","aa","aaa","aaaaa","aaaaaaa"]

要输出所有结果并不难，添加一个随BFS一起更新的queue<string> BFSS;//BFS String
并且取消了之前的visited判断集合

vector<string> wordBreak(string s, unordered_set<string> &dict){
	queue<int> BFS;
	queue<string> BFSS;
	BFS.push(0);
	BFSS.push("");
	
	while(!BFS.empty()){
		int start = BFS.front();
		sting tmp = BFSS.front();
		BFSS.pop();
		BFS.pop();
		
		for(int j = start; j < s.size(); j++){
			string word = string(s, start, j - start + 1);
			if(dict.find(word) != dict.end()){
				string item = tmp;
				if(tmp != ""){
					item += " ";
				} else { }
				item += word;
				BFSS.push(item);
				BFS.push(j+1);
				if(j+1 == s.size()){
					res.push_back(item);
			}
		}
	}
}


即使最后的结果，已经添加完毕的字符串添加到了BFSS,但是相应的BFS中保存的int为s.size().所以不会有问题。