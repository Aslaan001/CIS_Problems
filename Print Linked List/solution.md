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

void printList(Node* head) {
    Node* curr = head;
    while (curr != nullptr) {
        cout << curr->data << " ";
        curr = curr->next;
    }
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

public static void printList(Node head) {
    Node curr = head;
    while (curr != null) {
        System.out.print(curr.data + " ");
        curr = curr.next;
    }
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

void printList(struct Node* head) {
    struct Node* curr = head;
    while (curr != NULL) {
        printf("%d ", curr->data);
        curr = curr->next;
    }
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

function printList(head) {
    let curr = head;
    let res = [];
    while (curr !== null) {
        res.push(curr.data);
        curr = curr.next;
    }
    console.log(res.join(" "));
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def print_list(head):
    curr = head
    res = []
    while curr:
        res.append(curr.data)
        curr = curr.next
    print(*res)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
