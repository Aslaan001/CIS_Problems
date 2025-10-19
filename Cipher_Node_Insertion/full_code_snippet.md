## CPP

#include <bits/stdc++.h>
using namespace std;

class Node {
  public:
    int data;
    Node *next;
    Node(int x) {
        data = x;
        next = nullptr;
    }
};

// user code comes here

Node* createLinkedList(const vector<int>& vals) {
    if (vals.empty()) return nullptr;
    Node* head = new Node(vals[0]);
    Node* curr = head;
    for (int i = 1; i < vals.size(); i++) {
        curr->next = new Node(vals[i]);
        curr = curr->next;
    }
    return head;
}

void printLinkedList(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
}

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        vector<int> nodes(n);
        for (int i = 0; i < n; i++) cin >> nodes[i];
        int data, position;
        cin >> data >> position;

        Node* head = createLinkedList(nodes);
        head = insertNode(head, data, position);
        printLinkedList(head);
        cout << "\n";
        // evaluation completed
    }
    return 0;
}


## JAVA

import java.util.*;

class Node {
    int data;
    Node next;
    Node(int x) {
        data = x;
        next = null;
    }
}

public class Main {
    // user code comes here

    public static Node createLinkedList(int[] vals) {
        if (vals.length == 0) return null;
        Node head = new Node(vals[0]);
        Node curr = head;
        for (int i = 1; i < vals.length; i++) {
            curr.next = new Node(vals[i]);
            curr = curr.next;
        }
        return head;
    }

    public static void printLinkedList(Node head) {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
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
            int position = sc.nextInt();

            Node head = createLinkedList(nodes);
            head = insertNode(head, data, position);
            printLinkedList(head);
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
};

// user code comes here

struct Node* createLinkedList(int* vals, int n) {
    if (n == 0) return NULL;
    struct Node* head = (struct Node*)malloc(sizeof(struct Node));
    head->data = vals[0];
    head->next = NULL;
    struct Node* curr = head;
    for (int i = 1; i < n; i++) {
        struct Node* node = (struct Node*)malloc(sizeof(struct Node));
        node->data = vals[i];
        node->next = NULL;
        curr->next = node;
        curr = node;
    }
    return head;
}

void printLinkedList(struct Node* head) {
    while (head != NULL) {
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
        int vals[n];
        for (int i = 0; i < n; i++) scanf("%d", &vals[i]);
        int data, position;
        scanf("%d %d", &data, &position);

        struct Node* head = createLinkedList(vals, n);
        head = insertNode(head, data, position);
        printLinkedList(head);
        // evaluation completed
    }
    return 0;
}


## JAVASCRIPT

class Node {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
}

// user code comes here

function createLinkedList(vals) {
    if (vals.length === 0) return null;
    let head = new Node(vals[0]);
    let curr = head;
    for (let i = 1; i < vals.length; i++) {
        curr.next = new Node(vals[i]);
        curr = curr.next;
    }
    return head;
}

function printLinkedList(head) {
    let res = [];
    let curr = head;
    while (curr !== null) {
        res.push(curr.data);
        curr = curr.next;
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
        const position = parseInt(input[idx++]);

        let head = createLinkedList(vals);
        head = insertNode(head, data, position);
        printLinkedList(head);
        // evaluation completed
    }
}

main();


## PYTHON

import collections

# user code comes here

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def create_linked_list(vals):
    if not vals: return None
    head = Node(vals[0])
    curr = head
    for val in vals[1:]:
        curr.next = Node(val)
        curr = curr.next
    return head

def print_linked_list(head):
    res = []
    curr = head
    while curr:
        res.append(curr.data)
        curr = curr.next
    print(*res)

def main():
    t = int(input())
    for _ in range(t):
        n = int(input())
        vals = list(map(int, input().split()))

        inputs = []
        while len(inputs) < 2:
            inputs += list(map(int, input().split()))

        data, position = inputs[0], inputs[1]

        head = create_linked_list(vals)
        head = insert_node(head, data, position)
        print_linked_list(head)
        # evaluation completed

if __name__ == "__main__":
    main()
