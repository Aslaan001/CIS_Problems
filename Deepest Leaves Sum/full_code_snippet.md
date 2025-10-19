## CPP

#include <bits/stdc++.h>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

// Build tree from level order input (null -> missing node)
TreeNode* buildTree(vector<string>& arr) {
    if (arr.empty() || arr[0] == "null") return NULL;
    TreeNode* root = new TreeNode(stoi(arr[0]));
    queue<TreeNode*> q;
    q.push(root);
    int i = 1;
    while (!q.empty() && i < arr.size()) {
        TreeNode* node = q.front();
        q.pop();
        if (i < arr.size() && arr[i] != "null") {
            node->left = new TreeNode(stoi(arr[i]));
            q.push(node->left);
        }
        i++;
        if (i < arr.size() && arr[i] != "null") {
            node->right = new TreeNode(stoi(arr[i]));
            q.push(node->right);
        }
        i++;
    }
    return root;
}

// user code comes here


int main() {
    int t; cin >> t;
    while (t--) {
        int n; cin >> n;
        vector<string> arr(n);
        for (int i = 0; i < n; i++) cin >> arr[i];
        TreeNode* root = buildTree(arr);
        cout << deepestLeavesSum(root) << "\n";
        // evaluation completed
    }
}

---

## JAVA

import java.util.*;

class TreeNode {
    int val;
    TreeNode left, right;
    TreeNode(int x) { val = x; }
}

public class Main {

    static TreeNode buildTree(String[] arr) {
        if (arr.length == 0 || arr[0].equals("null")) return null;
        TreeNode root = new TreeNode(Integer.parseInt(arr[0]));
        Queue<TreeNode> q = new LinkedList<>();
        q.offer(root);
        int i = 1;
        while (!q.isEmpty() && i < arr.length) {
            TreeNode node = q.poll();
            if (i < arr.length && !arr[i].equals("null")) {
                node.left = new TreeNode(Integer.parseInt(arr[i]));
                q.offer(node.left);
            }
            i++;
            if (i < arr.length && !arr[i].equals("null")) {
                node.right = new TreeNode(Integer.parseInt(arr[i]));
                q.offer(node.right);
            }
            i++;
        }
        return root;
    }

    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            String[] arr = new String[n];
            for (int i = 0; i < n; i++) arr[i] = sc.next();
            TreeNode root = buildTree(arr);
            System.out.println(deepestLeavesSum(root));
            // evaluation completed
        }
    }
}

---

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
    struct TreeNode* node = malloc(sizeof(struct TreeNode));
    node->val = val;
    node->left = node->right = NULL;
    return node;
}

struct TreeNode* buildTree(char arr[][64], int n) {
    if (n == 0 || strcmp(arr[0], "null") == 0) return NULL;
    struct TreeNode** queue = malloc(n * sizeof(struct TreeNode*));
    int front = 0, rear = 0, i = 1;
    struct TreeNode* root = newNode(atoi(arr[0]));
    queue[rear++] = root;
    while (front < rear && i < n) {
        struct TreeNode* node = queue[front++];
        if (i < n && strcmp(arr[i], "null") != 0) {
            node->left = newNode(atoi(arr[i]));
            queue[rear++] = node->left;
        }
        i++;
        if (i < n && strcmp(arr[i], "null") != 0) {
            node->right = newNode(atoi(arr[i]));
            queue[rear++] = node->right;
        }
        i++;
    }
    free(queue);
    return root;
}

// user code comes here


int main() {
    int t; scanf("%d", &t);
    while (t--) {
        int n; scanf("%d", &n);
        char arr[n][64];
        for (int i = 0; i < n; i++) scanf("%s", arr[i]);
        struct TreeNode* root = buildTree(arr, n);
        printf("%d\n", deepestLeavesSum(root));
        // evaluation completed
    }
}

---

## JAVASCRIPT

class TreeNode {
  constructor(val, left = null, right = null) {
    this.val = val;
    this.left = left;
    this.right = right;
  }
}

function buildTree(arr) {
  if (!arr.length || arr[0] === "null") return null;
  let root = new TreeNode(+arr[0]);
  let q = [root];
  let i = 1;
  while (q.length && i < arr.length) {
    let node = q.shift();
    if (i < arr.length && arr[i] !== "null") {
      node.left = new TreeNode(+arr[i]);
      q.push(node.left);
    }
    i++;
    if (i < arr.length && arr[i] !== "null") {
      node.right = new TreeNode(+arr[i]);
      q.push(node.right);
    }
    i++;
  }
  return root;
}

// user code comes here


const fs = require("fs");
const data = fs.readFileSync(0, "utf8").trim().split(/\s+/);
let idx = 0, t = +data[idx++];
while (t--) {
  const n = +data[idx++];
  const arr = data.slice(idx, idx + n); idx += n;
  const root = buildTree(arr);
  console.log(deepestLeavesSum(root));
  // evaluation completed
}

---

## PYTHON

from collections import deque

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def buildTree(arr):
    if not arr or arr[0] == "null":
        return None
    root = TreeNode(int(arr[0]))
    q = deque([root])
    i = 1
    while q and i < len(arr):
        node = q.popleft()
        if i < len(arr) and arr[i] != "null":
            node.left = TreeNode(int(arr[i]))
            q.append(node.left)
        i += 1
        if i < len(arr) and arr[i] != "null":
            node.right = TreeNode(int(arr[i]))
            q.append(node.right)
        i += 1
    return root

# user code comes here


t = int(input().strip())
for _ in range(t):
    n = int(input().strip())
    arr = input().strip().split()
    root = buildTree(arr)
    print(deepestLeavesSum(root))
    # evaluation completed
