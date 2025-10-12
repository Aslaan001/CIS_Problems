## CPP

### SOLUTION

int kthSmallestHelper(TreeNode* root, int& k) {
    if(!root) return -1;
    int left = kthSmallestHelper(root->left, k);
    if(left != -1) return left;
    k--;
    if(k == 0) return root->val;
    return kthSmallestHelper(root->right, k);
}

int kthSmallest(TreeNode* root, int k) {
    return kthSmallestHelper(root, k);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int kthSmallestHelper(TreeNode root, int[] kArr) {
    if(root == null) return -1;
    int left = kthSmallestHelper(root.left, kArr);
    if(left != -1) return left;
    kArr[0]--;
    if(kArr[0] == 0) return root.val;
    return kthSmallestHelper(root.right, kArr);
}

public static int kthSmallest(TreeNode root, int k) {
    return kthSmallestHelper(root, new int[]{k});
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int kthSmallestHelper(struct TreeNode* root, int* k) {
    if(!root) return -1;
    int left = kthSmallestHelper(root->left, k);
    if(left != -1) return left;
    (*k)--;
    if(*k == 0) return root->val;
    return kthSmallestHelper(root->right, k);
}

int kthSmallest(struct TreeNode* root, int k) {
    return kthSmallestHelper(root, &k);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function kthSmallestHelper(root, kArr) {
    if(!root) return -1;
    let left = kthSmallestHelper(root.left, kArr);
    if(left !== -1) return left;
    kArr[0]--;
    if(kArr[0] === 0) return root.val;
    return kthSmallestHelper(root.right, kArr);
}

function kthSmallest(root, k) {
    return kthSmallestHelper(root, [k]);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def kthSmallestHelper(root, k):
    if not root:
        return -1
    left = kthSmallestHelper(root.left, k)
    if left != -1:
        return left
    k[0] -= 1
    if k[0] == 0:
        return root.val
    return kthSmallestHelper(root.right, k)

def kthSmallest(root, k):
    return kthSmallestHelper(root, [k])

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
