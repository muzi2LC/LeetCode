## 第一次  
```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    string tree2str(TreeNode* t) {
        if(t==NULL)  return "";
        string res="";
        if(t->right!=NULL)
            res=res+numToStr(t->val)+"("+tree2str(t->left)+")("+tree2str(t->right)+")";
        else if(t->left!=NULL)
             res=res+numToStr(t->val)+"("+tree2str(t->left)+")";
        else
            res=res+numToStr(t->val);
        return res;
    }
    string numToStr(int n)
    {
        if(n==0)   return "0";
        int num=n;
        if(n<0)    num=-n;
        string res="";
        while(num!=0)
        {
            res=char(num%10+'0')+res;
            num=num/10;
        }
        if(n<0)  res="-"+res;
        return res;
    }
};
```
