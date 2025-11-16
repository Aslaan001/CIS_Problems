## CPP

### SOLUTION

vector<vector<int>> zigzagTraversal(TreeNode* root) {
    vector<vector<int>> result;
    if (!root) return result;
    queue<TreeNode*> q;
    q.push(root);
    bool leftToRight = true;
    while (!q.empty()) {
        int size = q.size();
        vector<int> level(size);
        for (int i = 0; i < size; i++) {
            TreeNode* node = q.front(); q.pop();
            int index = leftToRight ? i : size - 1 - i;
            level[index] = node->val;
            if (node->left) q.push(node->left);
            if (node->right) q.push(node->right);
        }
        result.push_back(level);
        leftToRight = !leftToRight;
    }
    return result;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION

static List<List<Integer>> zigzagTraversal(TreeNode root) {
    List<List<Integer>> res = new ArrayList<>();
    if (root == null) return res;
    Queue<TreeNode> q = new LinkedList<>();
    q.add(root);
    boolean leftToRight = true;
    while (!q.isEmpty()) {
        int size = q.size();
        List<Integer> level = new ArrayList<>(Collections.nCopies(size, 0));
        for (int i = 0; i < size; i++) {
            TreeNode node = q.poll();
            int index = leftToRight ? i : size - 1 - i;
            level.set(index, node.val);
            if (node.left != null) q.add(node.left);
            if (node.right != null) q.add(node.right);
        }
        res.add(level);
        leftToRight = !leftToRight;
    }
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION

int** zigzagTraversal(struct TreeNode* root, int* returnSize, int** returnColumnSizes) {
    if (!root) {
        *returnSize = 0;
        *returnColumnSizes = NULL;
        return NULL;
    }

    int** result = (int**)malloc(2000 * sizeof(int*));
    int* colSizes = (int*)malloc(2000 * sizeof(int));
    *returnSize = 0;

    Queue q; initQueue(&q);
    push(&q, root);
    int leftToRight = 1;

    while (!isEmpty(&q)) {
        int size = q.rear - q.front;
        int* level = (int*)malloc(size * sizeof(int));
        for (int i = 0; i < size; i++) {
            struct TreeNode* node = pop(&q);
            int idx = leftToRight ? i : size - 1 - i;
            level[idx] = node->val;
            if (node->left) push(&q, node->left);
            if (node->right) push(&q, node->right);
        }
        result[*returnSize] = level;
        colSizes[*returnSize] = size;
        (*returnSize)++;
        leftToRight = !leftToRight;
    }

    *returnColumnSizes = colSizes;
    return result;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function zigzagTraversal(root) {
    if (!root) return [];
    let res = [];
    let q = [root];
    let leftToRight = true;
    while (q.length) {
        let size = q.length;
        let level = Array(size);
        for (let i = 0; i < size; i++) {
            let node = q.shift();
            let idx = leftToRight ? i : size - 1 - i;
            level[idx] = node.val;
            if (node.left) q.push(node.left);
            if (node.right) q.push(node.right);
        }
        res.push(level);
        leftToRight = !leftToRight;
    }
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def zigzagTraversal(root):
    if not root: return []
    res = []
    q = deque([root])
    leftToRight = True
    while q:
        size = len(q)
        level = [0]*size
        for i in range(size):
            node = q.popleft()
            idx = i if leftToRight else size - 1 - i
            level[idx] = node.val
            if node.left: q.append(node.left)
            if node.right: q.append(node.right)
        res.append(level)
        leftToRight = not leftToRight
    return res

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256