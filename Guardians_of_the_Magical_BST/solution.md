## CPP

### SOLUTION

TreeNode* findMin(TreeNode* node) {
    while (node->left) node = node->left;
    return node;
}

TreeNode* deleteNode(TreeNode* root, int key) {
    if (!root) return NULL;
    if (key < root->val) root->left = deleteNode(root->left, key);
    else if (key > root->val) root->right = deleteNode(root->right, key);
    else {
        if (!root->left) return root->right;
        else if (!root->right) return root->left;
        TreeNode* temp = findMin(root->right);
        root->val = temp->val;
        root->right = deleteNode(root->right, temp->val);
    }
    return root;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION

static TreeNode findMin(TreeNode node) {
    while (node.left != null) node = node.left;
    return node;
}

static TreeNode deleteNode(TreeNode root, int key) {
    if (root == null) return null;
    if (key < root.val) root.left = deleteNode(root.left, key);
    else if (key > root.val) root.right = deleteNode(root.right, key);
    else {
        if (root.left == null) return root.right;
        else if (root.right == null) return root.left;
        TreeNode temp = findMin(root.right);
        root.val = temp.val;
        root.right = deleteNode(root.right, temp.val);
    }
    return root;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION

struct TreeNode* findMin(struct TreeNode* node) {
    while (node->left) node = node->left;
    return node;
}

struct TreeNode* deleteNode(struct TreeNode* root, int key) {
    if (!root) return NULL;
    if (key < root->val) root->left = deleteNode(root->left, key);
    else if (key > root->val) root->right = deleteNode(root->right, key);
    else {
        if (!root->left) {
            struct TreeNode* r = root->right;
            free(root);
            return r;
        } else if (!root->right) {
            struct TreeNode* l = root->left;
            free(root);
            return l;
        }
        struct TreeNode* temp = findMin(root->right);
        root->val = temp->val;
        root->right = deleteNode(root->right, temp->val);
    }
    return root;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function findMin(node) {
    while (node.left) node = node.left;
    return node;
}

function deleteNode(root, key) {
    if (!root) return null;
    if (key < root.val) root.left = deleteNode(root.left, key);
    else if (key > root.val) root.right = deleteNode(root.right, key);
    else {
        if (!root.left) return root.right;
        if (!root.right) return root.left;
        let temp = findMin(root.right);
        root.val = temp.val;
        root.right = deleteNode(root.right, temp.val);
    }
    return root;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def findMin(node):
    while node.left:
        node = node.left
    return node

def deleteNode(root, key):
    if not root:
        return None
    if key < root.val:
        root.left = deleteNode(root.left, key)
    elif key > root.val:
        root.right = deleteNode(root.right, key)
    else:
        if not root.left:
            return root.right
        elif not root.right:
            return root.left
        temp = findMin(root.right)
        root.val = temp.val
        root.right = deleteNode(root.right, temp.val)
    return root

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256