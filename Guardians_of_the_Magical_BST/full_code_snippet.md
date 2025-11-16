## CPP

#include <bits/stdc++.h>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

TreeNode* insertBST(TreeNode* root, int val) {
    if (!root) return new TreeNode(val);
    if (val < root->val) root->left = insertBST(root->left, val);
    else root->right = insertBST(root->right, val);
    return root;
}

// user code comes here

void levelOrder(TreeNode* root) {
    if (!root) return;
    queue<TreeNode*> q;
    q.push(root);
    vector<string> res;
    while (!q.empty()) {
        TreeNode* node = q.front(); q.pop();
        if (node) {
            res.push_back(to_string(node->val));
            q.push(node->left);
            q.push(node->right);
        } else {
            res.push_back("null");
        }
    }
    while (!res.empty() && res.back() == "null") res.pop_back();
    for (int i = 0; i < res.size(); i++) {
        if (i) cout << " ";
        cout << res[i];
    }
    cout << "\n";
}

int main() {
    int t; 
    cin >> t;
    while (t--) {
        int n; cin >> n;
        vector<string> arr(n);
        for (int i = 0; i < n; i++) cin >> arr[i];
        int key; cin >> key;

        TreeNode* root = NULL;
        for (auto &s : arr) {
            if (s != "null") root = insertBST(root, stoi(s));
        }

        root = deleteNode(root, key);
        levelOrder(root);
        // evaluation completed
    }
}


## JAVA

import java.util.*;

class TreeNode {
    int val;
    TreeNode left, right;
    TreeNode(int x) { val = x; }
}

public class Main {
    static TreeNode insertBST(TreeNode root, int val) {
        if (root == null) return new TreeNode(val);
        if (val < root.val) root.left = insertBST(root.left, val);
        else root.right = insertBST(root.right, val);
        return root;
    }

    // user code comes here

    static void levelOrder(TreeNode root) {
        if (root == null) {
            System.out.println();
            return;
        }
        Queue<TreeNode> q = new LinkedList<>();
        q.add(root);
        ArrayList<String> res = new ArrayList<>();
        while (!q.isEmpty()) {
            TreeNode node = q.poll();
            if (node != null) {
                res.add(String.valueOf(node.val));
                q.add(node.left);
                q.add(node.right);
            } else res.add("null");
        }
        while (!res.isEmpty() && res.get(res.size()-1).equals("null")) res.remove(res.size()-1);
        for (int i = 0; i < res.size(); i++) {
            if (i > 0) System.out.print(" ");
            System.out.print(res.get(i));
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            String[] arr = new String[n];
            for (int i = 0; i < n; i++) arr[i] = sc.next();
            int key = sc.nextInt();

            TreeNode root = null;
            for (String s : arr)
                if (!s.equals("null")) root = insertBST(root, Integer.parseInt(s));

            root = deleteNode(root, key);
            levelOrder(root);
            // evaluation completed
        }
    }
}



## C


#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct TreeNode {
    int val;
    struct TreeNode* left;
    struct TreeNode* right;
};

struct TreeNode* newNode(int val) {
    struct TreeNode* node = (struct TreeNode*)malloc(sizeof(struct TreeNode));
    node->val = val;
    node->left = node->right = NULL;
    return node;
}

struct TreeNode* insertBST(struct TreeNode* root, int val) {
    if (!root) return newNode(val);
    if (val < root->val) root->left = insertBST(root->left, val);
    else root->right = insertBST(root->right, val);
    return root;
}

// user code comes here

void printLevelOrder(struct TreeNode* root) {
    if (!root) { printf("\n"); return; }
    const int QCAP = 100000;
    struct TreeNode** q = malloc(sizeof(struct TreeNode*) * QCAP);
    int front = 0, rear = 0;
    q[rear++] = root;

    char **res = malloc(sizeof(char*) * QCAP);
    int resCnt = 0;

    while (front < rear) {
        struct TreeNode* node = q[front++];
        if (node) {
            char *buf = malloc(32);
            sprintf(buf, "%d", node->val);
            res[resCnt++] = buf;
            q[rear++] = node->left;
            q[rear++] = node->right;
        } else {
            char *buf = malloc(6);
            strcpy(buf, "null");
            res[resCnt++] = buf;
        }
    }

    while (resCnt > 0 && strcmp(res[resCnt - 1], "null") == 0)
        free(res[--resCnt]);

    for (int i = 0; i < resCnt; ++i) {
        if (i) printf(" ");
        printf("%s", res[i]);
        free(res[i]);
    }
    printf("\n");

    free(res);
    free(q);
}

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        char **arr = malloc(sizeof(char*) * n);
        char buf[64];
        for (int i = 0; i < n; i++) {
            scanf("%s", buf);
            arr[i] = strdup(buf);
        }
        int key; scanf("%d", &key);

        struct TreeNode* root = NULL;
        for (int i = 0; i < n; i++) {
            if (strcmp(arr[i], "null") != 0)
                root = insertBST(root, atoi(arr[i]));
            free(arr[i]);
        }
        free(arr);

        root = deleteNode(root, key);
        printLevelOrder(root);
        // evaluation completed
    }
    return 0;
}



## JAVASCRIPT


class TreeNode {
    constructor(val, left = null, right = null) {
        this.val = val;
        this.left = left;
        this.right = right;
    }
}

function insertBST(root, val) {
    if (!root) return new TreeNode(val);
    if (val < root.val) root.left = insertBST(root.left, val);
    else root.right = insertBST(root.right, val);
    return root;
}

// user code comes here

function levelOrder(root) {
    if (!root) return [];
    const res = [], q = [root];
    while (q.length) {
        const node = q.shift();
        if (node) {
            res.push(String(node.val));
            q.push(node.left);
            q.push(node.right);
        } else res.push("null");
    }
    while (res.length && res[res.length - 1] === "null") res.pop();
    return res;
}

const fs = require("fs");
const data = fs.readFileSync(0, "utf8").trim().split(/\s+/);
let idx = 0, t = parseInt(data[idx++], 10);
while (t--) {
    const n = parseInt(data[idx++], 10);
    const arr = data.slice(idx, idx + n); idx += n;
    const key = parseInt(data[idx++], 10);

    let root = null;
    for (const s of arr) if (s !== "null") root = insertBST(root, +s);

    root = deleteNode(root, key);
    const out = levelOrder(root);
    console.log(out.length ? out.join(" ") : "");
    // evaluation completed
}



## PYTHON

from collections import deque

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def insertBST(root, val):
    if not root:
        return TreeNode(val)
    if val < root.val:
        root.left = insertBST(root.left, val)
    else:
        root.right = insertBST(root.right, val)
    return root

# user code comes here

def levelOrder(root):
    if not root: return []
    res, q = [], deque([root])
    while q:
        node = q.popleft()
        if node:
            res.append(str(node.val))
            q.append(node.left)
            q.append(node.right)
        else:
            res.append("null")
    while res and res[-1] == "null":
        res.pop()
    return res

t = int(input().strip())
for _ in range(t):
    n = int(input().strip())
    arr = input().strip().split()
    key = int(input().strip())

    root = None
    for s in arr:
        if s != "null":
            root = insertBST(root, int(s))

    root = deleteNode(root, key)
    ans = levelOrder(root)
    print(" ".join(ans))
    # evaluation completed
