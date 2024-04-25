# 814. Binary Tree Pruning

[Leetcode](https://leetcode.com/problems/binary-tree-pruning/)

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left),
 * right(right) {}
 * };
 */
class Solution {

    bool hasChildren(TreeNode* root) { return root->left || root->right; }

public:
    TreeNode* pruneTree(TreeNode* root) {

        // isNull
        if (!root)
            return nullptr;

        // now this check is before
        root->left = pruneTree(root->left);
        root->right = pruneTree(root->right);

        // val == 1 but reversed
        if (root->val == 0 && !hasChildren(root))
            return nullptr;

        return root;
    }
};
```
