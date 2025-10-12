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


int main() {
    int t; cin >> t;
    while(t--) {
        int n; cin >> n;
        vector<string> arr(n);
        for(int i=0;i<n;i++) cin >> arr[i];
        int key; cin >> key;

        TreeNode* root = NULL;
        for(auto &s : arr)
            if(s != "null") root = insertBST(root, stoi(s));

        int val = kthSmallest(root, key);
        cout << val << "\n";
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


    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while(t-- > 0) {
            int n = sc.nextInt();
            String[] arr = new String[n];
            for(int i=0;i<n;i++) arr[i] = sc.next();
            int key = sc.nextInt();

            TreeNode root = null;
            for(String s : arr)
                if(!s.equals("null")) root = insertBST(root, Integer.parseInt(s));

            int val = kthSmallest(root, key);
            System.out.println(val);
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
    if(!root) return newNode(val);
    if(val < root->val) root->left = insertBST(root->left, val);
    else root->right = insertBST(root->right, val);
    return root;
}

// user code comes here


int main() {
    int t; scanf("%d",&t);
    while(t--) {
        int n; scanf("%d",&n);
        char buf[64];
        struct TreeNode* root = NULL;
        for(int i=0;i<n;i++) {
            scanf("%s", buf);
            if(strcmp(buf,"null") != 0) root = insertBST(root, atoi(buf));
        }
        int key; scanf("%d",&key);
        int val = kthSmallest(root, key);
        printf("%d\n", val);
    }
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

    root = kthSmallest(root, key);
    console.log(root);
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

    root = kthSmallest(root, key)
    print(root)
