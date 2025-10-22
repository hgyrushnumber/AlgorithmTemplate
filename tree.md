# 二叉树

## 二叉树的节点定义

```
struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};
```

### 二叉树的遍历

```
分为三种遍历分别是：前序遍历，中序遍历，后序遍历
前序遍历：根左右
中序遍历：左根右
后序遍历：左右根
区别只是push_back的时候需要注意插入的值
vector<int> preorderTraversal(TreeNode* root) {
        vector<int> res;
        preorder(root, res);
        return res;
    }

    void preorder(TreeNode* node, vector<int>& res) {
        if (!node) return;
        res.push_back(node->val);   // ① 根
        preorder(node->left, res);  // ② 左
        preorder(node->right, res); // ③ 右
    }

    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> res;
        inorder(root, res);
        return res;
    }

    void inorder(TreeNode* node, vector<int>& res) {
        if (!node) return;
        inorder(node->left, res);   // ① 左
        res.push_back(node->val);   // ② 根
        inorder(node->right, res);  // ③ 右
    }

    vector<int> postorderTraversal(TreeNode* root) {
        vector<int> res;
        postorder(root, res);
        return res;
    }

    void postorder(TreeNode* node, vector<int>& res) {
        if (!node) return;
        postorder(node->left, res); // ① 左
        postorder(node->right, res);// ② 右
        res.push_back(node->val);   // ③ 根
    }
```

### 找到树的最大高度

```
int getHeight(TreeNode* root) {
    if (root == nullptr) return 0;              // 空节点高度为 0
    int left = getHeight(root->left);           // 左子树高度
    int right = getHeight(root->right);         // 右子树高度
    return 1 + max(left, right);                // 当前树高度
}
```

### 判断树是否为对称的结构

```
开始我想到的是使用中序遍历，然后转变为数组，这样的话存在一个bug，就是不能区分出左右子树
所以正确的办法还是递归判断
```

