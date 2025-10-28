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

Node* reverseBetween(Node* head, int m, int n) {
    if (!head || m == n) {
        return head;
    }

    Node* dummy = new Node(0);
    dummy->next = head;
    Node* pre = dummy;

    for (int i = 0; i < m - 1; i++) {
        pre = pre->next;
    }

    Node* start = pre->next;
    Node* then = start->next;

    for (int i = 0; i < n - m; i++) {
        start->next = then->next;
        then->next = pre->next;
        pre->next = then;
        then = start->next;
    }

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

public static Node reverseBetween(Node head, int m, int n) {
    if (head == null || m == n) {
        return head;
    }

    Node dummy = new Node(0);
    dummy.next = head;
    Node pre = dummy;

    for (int i = 0; i < m - 1; i++) {
        pre = pre.next;
    }

    Node start = pre.next;
    Node then = start.next;

    for (int i = 0; i < n - m; i++) {
        start.next = then.next;
        then.next = pre.next;
        pre.next = then;
        then = start.next;
    }

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

struct Node* reverseBetween(struct Node* head, int m, int n) {
    if (head == NULL || m == n) {
        return head;
    }

    struct Node* dummy = (struct Node*)malloc(sizeof(struct Node));
    dummy->data = 0;
    dummy->next = head;
    struct Node* pre = dummy;

    for (int i = 0; i < m - 1; i++) {
        pre = pre->next;
    }

    struct Node* start = pre->next;
    struct Node* then = start->next;

    for (int i = 0; i < n - m; i++) {
        start->next = then->next;
        then->next = pre->next;
        pre->next = then;
        then = start->next;
    }

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

function reverseBetween(head, m, n) {
    if (!head || m === n) {
        return head;
    }

    const dummy = new Node(0);
    dummy.next = head;
    let pre = dummy;

    for (let i = 0; i < m - 1; i++) {
        pre = pre.next;
    }

    let start = pre.next;
    let then = start.next;

    for (let i = 0; i < n - m; i++) {
        start.next = then.next;
        then.next = pre.next;
        pre.next = then;
        then = start.next;
    }

    return dummy.next;
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

def reverse_between(head, m, n):
    if not head or m == n:
        return head
        
    dummy = Node(0)
    dummy.next = head
    pre = dummy
    
    for _ in range(m - 1):
        pre = pre.next
        
    start = pre.next
    then = start.next
    
    for _ in range(n - m):
        start.next = then.next
        then.next = pre.next
        pre.next = then
        then = start.next
        
    return dummy.next


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512