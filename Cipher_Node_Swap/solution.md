### SOLUTION

## CPP


/*
class Node {
  public:
    int data;
    Node *next;
    Node(int x) {
        data = x;
        next = nullptr;
    }
};
*/

Node* swap_nodes(Node* head, int k) {
    Node* first = head;
    Node* second = head;
    Node* fast = head;

    for (int i = 1; i < k; i++) {
        if (fast != nullptr) fast = fast->next;
    }
    first = fast;

    while (fast->next != nullptr) {
        fast = fast->next;
        second = second->next;
    }

    int temp = first->data;
    first->data = second->data;
    second->data = temp;

    return head;
}



### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512

## JAVA

### SOLUTION
/*
class Node {
    int data;
    Node next;
    Node(int x) {
        data = x;
        next = null;
    }
}
*/

public static Node swap_nodes(Node head, int k) {
    Node first = head;
    Node second = head;
    Node fast = head;

    for (int i = 1; i < k; i++) {
        if (fast != null) fast = fast.next;
    }
    first = fast;

    while (fast.next != null) {
        fast = fast.next;
        second = second.next;
    }

    int temp = first.data;
    first.data = second.data;
    second.data = temp;

    return head;
}



### METADATA

**TimeLimit**
1200

**MemoryLimit**
512

## C

### SOLUTION
/*
struct Node {
    int data;
    struct Node* next;
};
*/

struct Node* swap_nodes(struct Node* head, int k) {
    struct Node* first = head;
    struct Node* second = head;
    struct Node* fast = head;

    for (int i = 1; i < k; i++) {
        if (fast != NULL) fast = fast->next;
    }
    first = fast;

    while (fast->next != NULL) {
        fast = fast->next;
        second = second->next;
    }

    int temp = first->data;
    first->data = second->data;
    second->data = temp;

    return head;
}



### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION
/*
class Node {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
}
*/

function swap_nodes(head, k) {
    let first = head;
    let second = head;
    let fast = head;

    for (let i = 1; i < k; i++) {
        if (fast !== null) fast = fast.next;
    }
    first = fast;

    while (fast.next !== null) {
        fast = fast.next;
        second = second.next;
    }

    let temp = first.data;
    first.data = second.data;
    second.data = temp;

    return head;
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION


def swap_nodes(head, k):
    first = head
    second = head
    fast = head

    
    for _ in range(k - 1):
        if fast is not None:
            fast = fast.next
    first = fast

    
    while fast.next is not None:
        fast = fast.next
        second = second.next

    first.data, second.data = second.data, first.data

    return head


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512