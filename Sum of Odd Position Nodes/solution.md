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

int sumOddPositions(Node* head) {
    int pos = 1, sum = 0;
    while (head) {
        if (pos % 2 == 1) sum += head->data;
        head = head->next;
        pos++;
    }
    return sum;
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

public static int sumOddPositions(Node head) {
        int pos = 1, sum = 0;
        while (head != null) {
            if (pos % 2 == 1) sum += head.data;
            head = head.next;
            pos++;
        }
        return sum;
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

int sumOddPositions(struct Node* head) {
    int pos = 1, sum = 0;
    while (head) {
        if (pos % 2 == 1) sum += head->data;
        head = head->next;
        pos++;
    }
    return sum;
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

function sumOddPositions(head) {
    let pos = 1, sum = 0;
    while (head) {
        if (pos % 2 === 1) sum += head.data;
        head = head.next;
        pos++;
    }
    return sum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def sum_odd_positions(head):
    pos = 1
    total = 0
    while head:
        if pos % 2 == 1:
            total += head.data
        head = head.next
        pos += 1
    return total

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
