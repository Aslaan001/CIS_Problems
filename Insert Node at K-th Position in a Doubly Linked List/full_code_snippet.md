## CPP

#include <bits/stdc++.h>
using namespace std;

class Node {
  public:
    int data;
    Node *next;
    Node *prev;
    Node(int x) {
        data = x;
        next = nullptr;
        prev = nullptr;
    }
};

// user code comes here


Node* createLinkedList(const vector<int>& vals) {
    if (vals.empty()) return nullptr;
    Node* head = new Node(vals[0]);
    Node* curr = head;
    for (int i = 1; i < vals.size(); i++) {
        Node* newNode = new Node(vals[i]);
        curr->next = newNode;
        newNode->prev = curr;
        curr = newNode;
    }
    return head;
}

void printList(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << "\n";
}

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        vector<int> nodes;
        if (n > 0) {
            nodes.resize(n);
            for (int i = 0; i < n; i++) cin >> nodes[i];
        }
        int data, k;
        cin >> data;
        cin >> k;

        Node* head = createLinkedList(nodes);
        head = insertAtKthPosition(head, data, k);
        printList(head);
        // evaluation completed
    }
    return 0;
}



## JAVA

import java.util.*;

class Node {
    int data;
    Node next;
    Node prev;
    Node(int x) {
        data = x;
        next = null;
        prev = null;
    }
}

public class Main {
    // user code comes here

    public static Node createLinkedList(int[] vals) {
        if (vals.length == 0) return null;
        Node head = new Node(vals[0]);
        Node curr = head;
        for (int i = 1; i < vals.length; i++) {
            Node newNode = new Node(vals[i]);
            curr.next = newNode;
            newNode.prev = curr;
            curr = newNode;
        }
        return head;
    }

    public static void printList(Node head) {
        while (head != null) {
            System.out.print(head.data + " ");
            head = head.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] nodes = new int[n];
            for (int i = 0; i < n; i++) nodes[i] = sc.nextInt();
            int data = sc.nextInt();
            int k = sc.nextInt();

            Node head = createLinkedList(nodes);
            head = insertAtKthPosition(head, data, k);
            printList(head);
            // evaluation completed
        }
        sc.close();
    }
}



## C

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    newNode->prev = NULL;
    return newNode;
}

// user code comes here


struct Node* createLinkedList(int* vals, int n) {
    if (n == 0) return NULL;
    struct Node* head = createNode(vals[0]);
    struct Node* curr = head;
    for (int i = 1; i < n; i++) {
        struct Node* newNode = createNode(vals[i]);
        curr->next = newNode;
        newNode->prev = curr;
        curr = newNode;
    }
    return head;
}

void printList(struct Node* head) {
    while (head) {
        printf("%d ", head->data);
        head = head->next;
    }
    printf("\n");
}

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        int* vals = NULL;
        if (n > 0) {
            vals = (int*)malloc(n * sizeof(int));
            for (int i = 0; i < n; i++) scanf("%d", &vals[i]);
        }
        int data, k;
        scanf("%d", &data);
        scanf("%d", &k);

        struct Node* head = createLinkedList(vals, n);
        head = insertAtKthPosition(head, data, k);
        printList(head);
        
        if (vals) free(vals);
        // evaluation completed
    }
    return 0;
}



## JAVASCRIPT

class Node {
    constructor(data) {
        this.data = data;
        this.next = null;
        this.prev = null;
    }
}

// user code comes here

function createLinkedList(vals) {
    if (vals.length === 0) return null;
    let head = new Node(vals[0]);
    let curr = head;
    for (let i = 1; i < vals.length; i++) {
        let newNode = new Node(vals[i]);
        curr.next = newNode;
        newNode.prev = curr;
        curr = newNode;
    }
    return head;
}

function printList(head) {
    let res = [];
    while (head) {
        res.push(head.data);
        head = head.next;
    }
    console.log(res.join(" "));
}

function main() {
    const fs = require("fs");
    const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);
    let idx = 0;

    const t = parseInt(input[idx++]);
    for (let tc = 0; tc < t; tc++) {
        const n = parseInt(input[idx++]);
        const vals = [];
        for (let i = 0; i < n; i++) vals.push(Number(input[idx++]));
        const data = parseInt(input[idx++]);
        const k = parseInt(input[idx++]);

        let head = createLinkedList(vals);
        head = insertAtKthPosition(head, data, k);
        printList(head);
        // evaluation completed
    }
}

main();



## PYTHON

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None

# user code comes here


def create_linked_list(vals):
    if not vals: return None
    head = Node(vals[0])
    curr = head
    for val in vals[1:]:
        new_node = Node(val)
        curr.next = new_node
        new_node.prev = curr
        curr = new_node
    return head

def print_list(head):
    res = []
    while head:
        res.append(str(head.data))
        head = head.next
    print(" ".join(res))

def main():
    t = int(input())
    for _ in range(t):
        n_str = input()
        if not n_str or int(n_str) == 0:
            n = 0
            vals = []
        else:
            n = int(n_str)
            vals = list(map(int, input().split()))
        
        data = int(input())
        k = int(input())
        
        head = create_linked_list(vals)
        head = insert_at_kth_position(head, data, k)
        print_list(head)
        # evaluation completed

if __name__ == "__main__":
    main()