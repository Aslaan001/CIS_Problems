## CPP

#include <bits/stdc++.h>
using namespace std;

struct TreeNode {
    int val;
    TreeNode *left, *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

TreeNode* buildTree(vector<string>& nodes) {
    if (nodes.empty() || nodes[0] == "null") return NULL;
    TreeNode* root = new TreeNode(stoi(nodes[0]));
    queue<TreeNode*> q;
    q.push(root);
    int i = 1;
    while (!q.empty() && i < nodes.size()) {
        TreeNode* curr = q.front(); q.pop();
        if (i < nodes.size() && nodes[i] != "null") {
            curr->left = new TreeNode(stoi(nodes[i]));
            q.push(curr->left);
        }
        i++;
        if (i < nodes.size() && nodes[i] != "null") {
            curr->right = new TreeNode(stoi(nodes[i]));
            q.push(curr->right);
        }
        i++;
    }
    return root;
}

// user code comes here

void printVectorOfVector(const vector<vector<int>>& res) {
    cout << "[";
    for (int i = 0; i < res.size(); i++) {
        cout << "[";
        for (int j = 0; j < res[i].size(); j++) {
            cout << res[i][j];
            if (j < res[i].size() - 1) cout << ",";
        }
        cout << "]";
        if (i < res.size() - 1) cout << ",";
    }
    cout << "]\n";
}

int main() {
    int t;
    cin >> t;
    cin.ignore();
    while (t--) {
        string input;
        getline(cin, input);
        stringstream ss(input);
        vector<string> nodes;
        while (ss.good()) {
            string temp; getline(ss, temp, ',');
            nodes.push_back(temp);
        }
        TreeNode* root = buildTree(nodes);
        auto ans = zigzagTraversal(root);
        printVectorOfVector(ans);
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
    static TreeNode buildTree(String[] nodes) {
        if (nodes.length == 0 || nodes[0].equals("null")) return null;
        TreeNode root = new TreeNode(Integer.parseInt(nodes[0]));
        Queue<TreeNode> q = new LinkedList<>();
        q.add(root);
        int i = 1;
        while (!q.isEmpty() && i < nodes.length) {
            TreeNode curr = q.poll();
            if (i < nodes.length && !nodes[i].equals("null")) {
                curr.left = new TreeNode(Integer.parseInt(nodes[i]));
                q.add(curr.left);
            }
            i++;
            if (i < nodes.length && !nodes[i].equals("null")) {
                curr.right = new TreeNode(Integer.parseInt(nodes[i]));
                q.add(curr.right);
            }
            i++;
        }
        return root;
    }

    // user code comes here

    static void printListOfList(List<List<Integer>> res) {
        System.out.print("[");
        for (int i = 0; i < res.size(); i++) {
            System.out.print("[");
            for (int j = 0; j < res.get(i).size(); j++) {
                System.out.print(res.get(i).get(j));
                if (j < res.get(i).size() - 1) System.out.print(",");
            }
            System.out.print("]");
            if (i < res.size() - 1) System.out.print(",");
        }
        System.out.println("]");
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        sc.nextLine();
        while (t-- > 0) {
            String input = sc.nextLine();
            String[] nodes = input.split(",");
            TreeNode root = buildTree(nodes);
            List<List<Integer>> ans = zigzagTraversal(root);
            printListOfList(ans);
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

typedef struct {
    struct TreeNode* arr[2005];
    int front, rear;
} Queue;

void initQueue(Queue* q) { q->front = q->rear = 0; }
int isEmpty(Queue* q) { return q->front == q->rear; }
void push(Queue* q, struct TreeNode* node) { q->arr[q->rear++] = node; }
struct TreeNode* pop(Queue* q) { return q->arr[q->front++]; }

// user code comes here

void printResult(int** res, int returnSize, int* returnColumnSizes) {
    printf("[");
    for (int i = 0; i < returnSize; i++) {
        printf("[");
        for (int j = 0; j < returnColumnSizes[i]; j++) {
            printf("%d", res[i][j]);
            if (j < returnColumnSizes[i]-1) printf(",");
        }
        printf("]");
        if (i < returnSize-1) printf(",");
    }
    printf("]\n");
}

struct TreeNode* buildTree(char arr[][10], int n) {
    if (n == 0 || strcmp(arr[0], "null") == 0) return NULL;
    struct TreeNode* root = malloc(sizeof(struct TreeNode));
    root->val = atoi(arr[0]);
    root->left = root->right = NULL;

    Queue q; initQueue(&q);
    push(&q, root);
    int i = 1;

    while (!isEmpty(&q) && i < n) {
        struct TreeNode* curr = pop(&q);
        if (i < n && strcmp(arr[i], "null") != 0) {
            struct TreeNode* leftNode = malloc(sizeof(struct TreeNode));
            leftNode->val = atoi(arr[i]); leftNode->left = leftNode->right = NULL;
            curr->left = leftNode; push(&q, leftNode);
        }
        i++;
        if (i < n && strcmp(arr[i], "null") != 0) {
            struct TreeNode* rightNode = malloc(sizeof(struct TreeNode));
            rightNode->val = atoi(arr[i]); rightNode->left = rightNode->right = NULL;
            curr->right = rightNode; push(&q, rightNode);
        }
        i++;
    }
    return root;
}

int main() {
    int t;
    scanf("%d", &t);
    getchar();
    while (t--) {
        char input[1000];
        fgets(input, sizeof(input), stdin);
        char arr[2005][10];
        int n = 0;
        char* token = strtok(input, ",\n");
        while (token) { strcpy(arr[n++], token); token = strtok(NULL, ",\n"); }

        struct TreeNode* root = buildTree(arr, n);
        int returnSize;
        int* returnColumnSizes;
        int** ans = zigzagTraversal(root, &returnSize, &returnColumnSizes);
        printResult(ans, returnSize, returnColumnSizes);
    }
}


## JAVASCRIPT

class TreeNode {
    constructor(val) {
        this.val = val;
        this.left = this.right = null;
    }
}

function buildTree(nodes) {
    if (nodes.length === 0 || nodes[0] === "null") return null;
    let root = new TreeNode(parseInt(nodes[0]));
    let q = [root];
    let i = 1;
    while (q.length && i < nodes.length) {
        let curr = q.shift();
        if (i < nodes.length && nodes[i] !== "null") {
            curr.left = new TreeNode(parseInt(nodes[i]));
            q.push(curr.left);
        }
        i++;
        if (i < nodes.length && nodes[i] !== "null") {
            curr.right = new TreeNode(parseInt(nodes[i]));
            q.push(curr.right);
        }
        i++;
    }
    return root;
}

// user code comes here

function printResult(res) {
    let out = "[";
    for (let i = 0; i < res.length; i++) {
        out += "[" + res[i].join(",") + "]";
        if (i < res.length - 1) out += ",";
    }
    out += "]";
    console.log(out);
}

const fs = require("fs");
const input = fs.readFileSync(0, "utf-8").trim().split("\n");
let t = parseInt(input[0]);
let idx = 1;
while (t--) {
    const nodes = input[idx++].split(",");
    const root = buildTree(nodes);
    const ans = zigzagTraversal(root);
    printResult(ans);
}



## PYTHON

from collections import deque

class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left = None
        self.right = None

def buildTree(nodes):
    if not nodes or nodes[0] == "null":
        return None
    root = TreeNode(int(nodes[0]))
    q = deque([root])
    i = 1
    while q and i < len(nodes):
        curr = q.popleft()
        if i < len(nodes) and nodes[i] != "null":
            curr.left = TreeNode(int(nodes[i]))
            q.append(curr.left)
        i += 1
        if i < len(nodes) and nodes[i] != "null":
            curr.right = TreeNode(int(nodes[i]))
            q.append(curr.right)
        i += 1
    return root

# user code comes here

def print_result(res):
    print("[", end="")
    for i in range(len(res)):
        print("[", end="")
        for j in range(len(res[i])):
            print(res[i][j], end="")
            if j < len(res[i]) - 1:
                print(",", end="")
        print("]", end="")
        if i < len(res) - 1:
            print(",", end="")
    print("]")

t = int(input())
for _ in range(t):
    nodes = input().split(",")
    root = buildTree(nodes)
    ans = zigzagTraversal(root)
    print_result(ans)
