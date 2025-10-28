## CPP

### SOLUTION

/*
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
*/

Node* deleteAtKthPosition(Node* head, int k) {
    if (head == nullptr) {
        return nullptr;
    }

    if (k == 1) {
        Node* nodeToDelete = head;
        Node* newHead = head->next;
        if (newHead != nullptr) {
            newHead->prev = nullptr;
        }
        delete nodeToDelete;
        return newHead;
    }

    Node* curr = head;
    for (int i = 0; i < k - 1; i++) {
        curr = curr->next;
    }

    Node* prevNode = curr->prev;
    Node* nextNode = curr->next;

    if (prevNode != nullptr) {
        prevNode->next = nextNode;
    }
    if (nextNode != nullptr) {
        nextNode->prev = prevNode;
    }

    delete curr;
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
    Node prev;
    Node(int x) {
        data = x;
        next = null;
        prev = null;
    }
}
*/

public static Node deleteAtKthPosition(Node head, int k) {
    if (head == null) {
        return null;
    }

    if (k == 1) {
        Node newHead = head.next;
        if (newHead != null) {
            newHead.prev = null;
        }
        return newHead;
    }

    Node curr = head;
    for (int i = 0; i < k - 1; i++) {
        curr = curr.next;
    }

    Node prevNode = curr.prev;
    Node nextNode = curr.next;

    if (prevNode != null) {
        prevNode.next = nextNode;
    }
    if (nextNode != null) {
        nextNode.prev = prevNode;
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
    struct Node* prev;
};
*/

struct Node* deleteAtKthPosition(struct Node* head, int k) {
    if (head == NULL) {
        return NULL;
    }

    if (k == 1) {
        struct Node* nodeToDelete = head;
        struct Node* newHead = head->next;
        if (newHead != NULL) {
            newHead->prev = NULL;
        }
        free(nodeToDelete);
        return newHead;
    }

    struct Node* curr = head;
    for (int i = 0; i < k - 1; i++) {
        curr = curr->next;
    }

    struct Node* prevNode = curr->prev;
    struct Node* nextNode = curr->next;

    if (prevNode != NULL) {
        prevNode->next = nextNode;
    }
    if (nextNode != NULL) {
        nextNode->prev = prevNode;
    }

    free(curr);
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
        this.prev = null;
    }
}
*/

function deleteAtKthPosition(head, k) {
    if (!head) {
        return null;
    }

    if (k === 1) {
        let newHead = head.next;
        if (newHead) {
            newHead.prev = null;
        }
        return newHead;
    }

    let curr = head;
    for (let i = 0; i < k - 1; i++) {
        curr = curr.next;
    }

    const prevNode = curr.prev;
    const nextNode = curr.next;

    if (prevNode) {
        prevNode.next = nextNode;
    }
    if (nextNode) {
        nextNode.prev = prevNode;
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

# class Node:
#    def __init__(self, data):
#        self.data = data
#        self.next = None
#        self.prev = None

def delete_at_kth_position(head, k):
    if head is None:
        return None

    if k == 1:
        new_head = head.next
        if new_head:
            new_head.prev = None
        return new_head

    curr = head
    for _ in range(k - 1):
        curr = curr.next

    prev_node = curr.prev
    next_node = curr.next

    if prev_node:
        prev_node.next = next_node
    if next_node:
        next_node.prev = prev_node

    return head


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512