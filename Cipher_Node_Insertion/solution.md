## CPP

### SOLUTION

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

Node* insertNode(Node* head, int data, int position) {
    Node* newNode = new Node(data);
    if (position == 0) {
        newNode->next = head;
        return newNode;
    }
    Node* curr = head;
    for (int i = 0; i < position - 1 && curr != nullptr; i++) {
        curr = curr->next;
    }
    if (curr != nullptr) {
        newNode->next = curr->next;
        curr->next = newNode;
    }
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

public static Node insertNode(Node head, int data, int position) {
    Node newNode = new Node(data);
    if (position == 0) {
        newNode.next = head;
        return newNode;
    }
    Node curr = head;
    for (int i = 0; i < position - 1 && curr != null; i++) {
        curr = curr.next;
    }
    if (curr != null) {
        newNode.next = curr.next;
        curr.next = newNode;
    }
    return head;
}

### METADATA

**TimeLimit**
1000

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

struct Node* insertNode(struct Node* head, int data, int position) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;

    if (position == 0) {
        newNode->next = head;
        return newNode;
    }

    struct Node* curr = head;
    for (int i = 0; i < position - 1 && curr != NULL; i++) {
        curr = curr->next;
    }

    if (curr != NULL) {
        newNode->next = curr->next;
        curr->next = newNode;
    }

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

function insertNode(head, data, position) {
    const newNode = new Node(data);
    if (position === 0) {
        newNode.next = head;
        return newNode;
    }
    let curr = head;
    for (let i = 0; i < position - 1 && curr !== null; i++) {
        curr = curr.next;
    }
    if (curr !== null) {
        newNode.next = curr.next;
        curr.next = newNode;
    }
    return head;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION


def insert_node(head, data, position):
    new_node = Node(data)
    if position == 0:
        new_node.next = head
        return new_node
    curr = head
    for _ in range(position - 1):
        if curr is not None:
            curr = curr.next
    if curr is not None:
        new_node.next = curr.next
        curr.next = new_node
    return head


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512