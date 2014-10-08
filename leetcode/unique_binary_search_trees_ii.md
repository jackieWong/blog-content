Title: Unique Binary Search Trees II
Date: 2014-9-30
Category: leetcode

## Unique Binary Search Trees II
Given number n, generate all structurally unique BST's(binary search trees) that store values 1..n.

思路：递归
具体描述：n个数字每个数字都有可能成为根节点，针对不同的根节点，将数组划分为1 ~ i-1, i+1 ~ n;
然后对左右子数组构建BST。
BST构建思路：generate函数负责构建BST，参数为起始val,终止val。从start ~ end,选不同的val作为子树根节点，同时将start ~ end划分为start ~ i - 1, i + 1 ~ end的两部分。针对两部分再次递归调用BST构造函数。假设左子树有M种结构，右子树有N种。那么构造出来的情况一共有MN。

	class Solution {
	public:
    	vector<TreeNode *> generateTrees(int n) {
        	vector<TreeNode *> res;
        	if(n == 0) res.push_back(NULL);
        	for(int i = 1; i <= n; i++){
            	vector<TreeNode *> lV = generate(1, i - 1);
            	vector<TreeNode *> rV = generate(i + 1, n);
            	for(int li = 0; li < lV.size(); li++){
                	for(int ri = 0; ri < rV.size(); ri++){
                   		TreeNode * tmp = new TreeNode(i);
                   		tmp->left = lV[li];
                   		tmp->right = rV[ri];
                    	res.push_back(tmp);
                	}
            	}
        	}
        
        	return res;
    }
    
    
    vector<TreeNode *> generate(int start, int end)
    {
        if(start > end) {
            vector<TreeNode *> res;
            res.push_back(NULL);
            return res;
        }
        
        if(start == end){
            vector<TreeNode *> res;
            TreeNode * tmp = new TreeNode(start);
            res.push_back(tmp);
            return res;
        }
        
        vector<TreeNode *> res;
        for(int i = start; i <= end; i++){           
            vector<TreeNode *> lV = generate(start, i - 1);
            vector<TreeNode *> rV = generate(i + 1, end);
            for(int li = 0; li < lV.size(); li++){
                for(int ri = 0; ri < rV.size(); ri++){
                    TreeNode * tmp = new TreeNode(i);
                    tmp->left = lV[li];
                    tmp->right = rV[ri];
                    res.push_back(tmp);
                }
            }
            
        }
        
        return res;
    }
    
	};