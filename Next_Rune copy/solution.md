## CPP

### SOLUTION

int deepestLeavesSum(TreeNode* root) {
    if (!root) return 0;
    queue<TreeNode*> q;
    q.push(root);
    int sum = 0;

    while (!q.empty()) {
        int size = q.size();
        sum = 0;
        for (int i = 0; i < size; i++) {
            TreeNode* node = q.front();
            q.pop();
            sum += node->val;
            if (node->left) q.push(node->left);
            if (node->right) q.push(node->right);
        }
    }
    return sum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public int deepestLeavesSum(TreeNode root) {
    if (root == null) return 0;
    Queue<TreeNode> q = new LinkedList<>();
    q.offer(root);
    int sum = 0;

    while (!q.isEmpty()) {
        int size = q.size();
        sum = 0;
        for (int i = 0; i < size; i++) {
            TreeNode node = q.poll();
            sum += node.val;
            if (node.left != null) q.offer(node.left);
            if (node.right != null) q.offer(node.right);
        }
    }
    return sum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

struct TreeNode {
    int val;
    struct TreeNode* left;
    struct TreeNode* right;
};

int deepestLeavesSum(struct TreeNode* root) {
    if (!root) return 0;
    struct TreeNode* queue[10000];
    int front = 0, rear = 0, sum = 0;

    queue[rear++] = root;
    while (front < rear) {
        int size = rear - front;
        sum = 0;
        for (int i = 0; i < size; i++) {
            struct TreeNode* node = queue[front++];
            sum += node->val;
            if (node->left) queue[rear++] = node->left;
            if (node->right) queue[rear++] = node->right;
        }
    }
    return sum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

var deepestLeavesSum = function(root) {
  if (!root) return 0;
  let queue = [root];
  let sum = 0;

  while (queue.length > 0) {
    let size = queue.length;
    sum = 0;
    for (let i = 0; i < size; i++) {
      let node = queue.shift();
      sum += node.val;
      if (node.left) queue.push(node.left);
      if (node.right) queue.push(node.right);
    }
  }
  return sum;
};

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION


def deepestLeavesSum(root):
    if not root:
        return 0
    q = deque([root])
    while q:
        level_sum = 0
        for _ in range(len(q)):
            node = q.popleft()
            level_sum += node.val
            if node.left:
                q.append(node.left)
            if node.right:
                q.append(node.right)
    return level_sum

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
