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

Node* removeNthFromEnd(Node* head, int n) {
    Node* dummy = new Node(0);
    dummy->next = head;
    Node* fast = dummy;
    Node* slow = dummy;

    for (int i = 0; i <= n; i++) {
        fast = fast->next;
    }

    while (fast) {
        fast = fast->next;
        slow = slow->next;
    }

    Node* toDelete = slow->next;
    slow->next = slow->next->next;
    delete toDelete;

    Node* newHead = dummy->next;
    delete dummy;
    return newHead;
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

public static Node removeNthFromEnd(Node head, int n) {
    Node dummy = new Node(0);
    dummy.next = head;
    Node fast = dummy;
    Node slow = dummy;

    for (int i = 0; i <= n; i++) {
        fast = fast.next;
    }

    while (fast != null) {
        fast = fast.next;
        slow = slow.next;
    }

    slow.next = slow.next.next;
    return dummy.next;
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

struct Node* removeNthFromEnd(struct Node* head, int n) {
    struct Node* dummy = (struct Node*)malloc(sizeof(struct Node));
    dummy->data = 0;
    dummy->next = head;

    struct Node *fast = dummy, *slow = dummy;

    for (int i = 0; i <= n; i++) {
        fast = fast->next;
    }

    while (fast) {
        fast = fast->next;
        slow = slow->next;
    }

    struct Node* toDelete = slow->next;
    slow->next = slow->next->next;
    free(toDelete);

    struct Node* newHead = dummy->next;
    free(dummy);
    return newHead;
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

function removeNthFromEnd(head, n) {
    const dummy = new Node(0);
    dummy.next = head;

    let fast = dummy;
    let slow = dummy;

    for (let i = 0; i <= n; i++) {
        fast = fast.next;
    }

    while (fast) {
        fast = fast.next;
        slow = slow.next;
    }

    slow.next = slow.next.next;
    return dummy.next;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def remove_nth_from_end(head, n):
    dummy = Node(0)
    dummy.next = head
    fast = dummy
    slow = dummy

    for _ in range(n + 1):
        fast = fast.next

    while fast:
        fast = fast.next
        slow = slow.next

    slow.next = slow.next.next
    return dummy.next

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
