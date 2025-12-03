## CPP

#include <bits/stdc++.h>
using namespace std;

struct Node {
    int data;
    Node *left, *right;
    Node(int val) { data = val; left = right = NULL; }
};

Node* buildTree(vector<string>& arr) {
    if (arr.empty() || arr[0] == "N") return NULL;
    Node* root = new Node(stoi(arr[0]));
    queue<Node*> q; q.push(root);
    int i = 1;
    while (!q.empty() && i < arr.size()) {
        Node* curr = q.front(); q.pop();
        if (arr[i] != "N") {
            curr->left = new Node(stoi(arr[i]));
            q.push(curr->left);
        }
        i++;
        if (i >= arr.size()) break;
        if (arr[i] != "N") {
            curr->right = new Node(stoi(arr[i]));
            q.push(curr->right);
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
        for (int i=0;i<n;i++) cin >> arr[i];
        Node* root = buildTree(arr);
        vector<int> res = topView(root);
        for (int x:res) cout << x << " ";
        cout << "\n";
        // evalulation Completed
    }
    return 0;
}


## JAVA

import java.util.*;

class Node {
    int data; Node left, right;
    Node(int val){ data=val; }
}
class Pair {
    Node node; int hd;
    Pair(Node n, int h){ node=n; hd=h; }
}

public class Main {
    public static Node buildTree(String[] arr) {
        if (arr.length==0 || arr[0].equals("N")) return null;
        Node root = new Node(Integer.parseInt(arr[0]));
        Queue<Node> q=new LinkedList<>(); q.add(root);
        int i=1;
        while(!q.isEmpty() && i<arr.length){
            Node curr=q.poll();
            if(!arr[i].equals("N")){
                curr.left=new Node(Integer.parseInt(arr[i]));
                q.add(curr.left);
            }
            i++; if(i>=arr.length) break;
            if(!arr[i].equals("N")){
                curr.right=new Node(Integer.parseInt(arr[i]));
                q.add(curr.right);
            }
            i++;
        }
        return root;
    }

    // user code comes here

    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        int t=sc.nextInt();
        while(t-- > 0){
            int n=sc.nextInt(); sc.nextLine();
            String[] arr=sc.nextLine().split(" ");
            Node root=buildTree(arr);
            List<Integer> res=topView(root);
            for(int x:res) System.out.print(x+" ");
            System.out.println();
            // evalulation Completed
        }
    }
}



## C

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Node { 
    int data; 
    struct Node *left,*right; 
};
struct Node* newNode(int val){
    struct Node* node=malloc(sizeof(struct Node));
    node->data=val; node->left=node->right=NULL;
    return node;
}

struct Node* queue[100005]; int front=0,rear=0;
void push(struct Node* x){ queue[rear++]=x; }
struct Node* pop(){ return queue[front++]; }
int empty(){ return front==rear; }

struct Node* buildTree(char arr[][20], int n){
    if(n==0 || strcmp(arr[0],"N")==0) return NULL;
    front=rear=0;
    struct Node* root=newNode(atoi(arr[0])); push(root);
    int i=1;
    while(!empty() && i<n){
        struct Node* curr=pop();
        if(strcmp(arr[i],"N")!=0){ 
            curr->left=newNode(atoi(arr[i])); 
            push(curr->left); 
        }
        i++; if(i>=n) break;
        if(strcmp(arr[i],"N")!=0){ 
            curr->right=newNode(atoi(arr[i])); 
            push(curr->right); 
        }
        i++;
    }
    return root;
}

struct Pair{ struct Node* node; int hd; };
struct Pair q2[100005]; int f=0,r=0;

int seen[2005],val[2005]; 
int OFFSET=1000;

// user code comes here

int main(){
    int t; scanf("%d",&t);
    while(t--){
        int n; scanf("%d",&n);
        char arr[n][20];
        for(int i=0;i<n;i++) scanf("%s",arr[i]);
        struct Node* root=buildTree(arr,n);

        int size;
        int *ans = topView(root,&size);

        for(int i=0;i<size;i++) printf("%d ",ans[i]);
        printf("\n");
        free(ans);
        // evalulation Completed
    }
    return 0;
}



## JAVASCRIPT

class Node {
    constructor(val) {
        this.data = val;
        this.left = this.right = null;
    }
}

function buildTree(arr) {
    if (arr.length===0 || arr[0]==="N") return null;
    let root=new Node(parseInt(arr[0]));
    let q=[root]; let i=1;
    while(q.length && i<arr.length){
        let curr=q.shift();
        if(arr[i]!=="N"){ curr.left=new Node(parseInt(arr[i])); q.push(curr.left); }
        i++; if(i>=arr.length) break;
        if(arr[i]!=="N"){ curr.right=new Node(parseInt(arr[i])); q.push(curr.right); }
        i++;
    }
    return root;
}

// user code comes here

const fs=require("fs");
const input=fs.readFileSync(0,"utf-8").trim().split(/\s+/);
let idx=0;
let t=parseInt(input[idx++]);
while(t--){
    let n=parseInt(input[idx++]);
    let arr=input.slice(idx, idx+n); idx+=n;
    let root=buildTree(arr);
    console.log(topView(root).join(" "));
    // evalulation Completed
}



## PYTHON

from collections import deque

class Node:
    def __init__(self, val):
        self.data = val
        self.left = None
        self.right = None

def buildTree(arr):
    if not arr or arr[0] == "N":
        return None
    root = Node(int(arr[0]))
    q = deque([root])
    i = 1
    while q and i < len(arr):
        curr = q.popleft()
        if arr[i] != "N":
            curr.left = Node(int(arr[i]))
            q.append(curr.left)
        i += 1
        if i >= len(arr): break
        if arr[i] != "N":
            curr.right = Node(int(arr[i]))
            q.append(curr.right)
        i += 1
    return root

# user code comes here

t = int(input())
for _ in range(t):
    n = int(input())
    arr = input().split()
    root = buildTree(arr)
    print(*topView(root))
    # evalulation Completed
