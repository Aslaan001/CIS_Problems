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
Node* swapNodes(Node* head, int k) {
    if (!head) return nullptr;
    Node *first = nullptr, *second = nullptr, *curr = head;
    int n = 0;
    while (curr) {
        n++;
        curr = curr->next;
    }
    curr = head;
    for (int i = 1; i <= n; i++) {
        if (i == k) first = curr;
        if (i == n - k + 1) second = curr;
        curr = curr->next;
    }
    if (first && second) swap(first->data, second->data);
    return head;
}

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
    int n;
    cin >> n;
    vector<int> nodes(n);
    for (int i = 0; i < n; i++) cin >> nodes[i];
    int k;
    cin >> k;
    Node* head = createLinkedList(nodes);
    head = swap_nodes(head, k);
    printLinkedList(head);
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
    public static Node swapNodes(Node head, int k) {
        if (head == null) return null;
        Node first = null, second = null, curr = head;
        int n = 0;
        while (curr != null) {
            n++;
            curr = curr.next;
        }
        curr = head;
        for (int i = 1; i <= n; i++) {
            if (i == k) first = curr;
            if (i == n - k + 1) second = curr;
            curr = curr.next;
        }
        if (first != null && second != null) {
            int temp = first.data;
            first.data = second.data;
            second.data = temp;
        }
        return head;
    }

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
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nodes = new int[n];
        for (int i = 0; i < n; i++) nodes[i] = sc.nextInt();
        int k = sc.nextInt();

        Node head = createLinkedList(nodes);
        head = swap_nodes(head, k);
        printLinkedList(head);
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

struct Node* swapNodes(struct Node* head, int k) {
    if (!head) return NULL;
    struct Node *first = NULL, *second = NULL, *curr = head;
    int n = 0;
    while (curr) {
        n++;
        curr = curr->next;
    }
    curr = head;
    for (int i = 1; i <= n; i++) {
        if (i == k) first = curr;
        if (i == n - k + 1) second = curr;
        curr = curr->next;
    }
    if (first && second) {
        int temp = first->data;
        first->data = second->data;
        second->data = temp;
    }
    return head;
}

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
}

int main() {
    int n;
    scanf("%d", &n);
    int vals[n];
    for (int i = 0; i < n; i++) scanf("%d", &vals[i]);
    int k;
    scanf("%d", &k);

    struct Node* head = createLinkedList(vals, n);
    head = swap_nodes(head, k);
    printLinkedList(head);
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


function swapNodes(head, k) {
    if (!head) return null;
    let curr = head, first = null, second = null, n = 0;
    while (curr) {
        n++;
        curr = curr.next;
    }
    curr = head;
    for (let i = 1; i <= n; i++) {
        if (i === k) first = curr;
        if (i === n - k + 1) second = curr;
        curr = curr.next;
    }
    if (first && second) {
        [first.data, second.data] = [second.data, first.data];
    }
    return head;
}

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
    while (curr) {
        res.push(curr.data);
        curr = curr.next;
    }
    console.log(res.join(" "));
}

function main() {
    const fs = require("fs");
    const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);

    const n = parseInt(input[0]);
    const vals = input.slice(1, n + 1).map(Number);
    const k = parseInt(input[n + 1]);

    let head = createLinkedList(vals);
    head = swap_nodes(head, k);
    printLinkedList(head);
}

main();


## PYTHON

import collections


class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# user code comes here
def swap_nodes(head, k):
    if not head:
        return None
    curr = head
    n = 0
    while curr:
        n += 1
        curr = curr.next
    first = second = head
    curr = head
    for i in range(1, n + 1):
        if i == k:
            first = curr
        if i == n - k + 1:
            second = curr
        curr = curr.next
    first.data, second.data = second.data, first.data
    return head

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
    n = int(input())
    vals = list(map(int, input().split()))
    k = int(input())
    head = create_linked_list(vals)
    head = swap_nodes(head, k)
    print_linked_list(head)

if __name__ == "__main__":
    main()
