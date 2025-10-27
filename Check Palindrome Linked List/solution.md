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

bool isPalindrome(Node* head) {
    if (!head || !head->next) return true;

    Node* slow = head;
    Node* fast = head;

    // find middle
    while (fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
    }

    // reverse second half
    Node* prev = nullptr;
    while (slow) {
        Node* nextNode = slow->next;
        slow->next = prev;
        prev = slow;
        slow = nextNode;
    }

    // compare halves
    Node* first = head;
    Node* second = prev;
    while (second) {
        if (first->data != second->data) return false;
        first = first->next;
        second = second->next;
    }

    return true;
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

public static boolean isPalindrome(Node head) {
    if (head == null || head.next == null) return true;

    Node slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }

    // reverse second half
    Node prev = null;
    while (slow != null) {
        Node nextNode = slow.next;
        slow.next = prev;
        prev = slow;
        slow = nextNode;
    }

    Node first = head, second = prev;
    while (second != null) {
        if (first.data != second.data) return false;
        first = first.next;
        second = second.next;
    }
    return true;
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

bool isPalindrome(struct Node* head) {
    if (!head || !head->next) return true;

    struct Node *slow = head, *fast = head;
    while (fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
    }

    struct Node* prev = NULL;
    while (slow) {
        struct Node* nextNode = slow->next;
        slow->next = prev;
        prev = slow;
        slow = nextNode;
    }

    struct Node* first = head;
    struct Node* second = prev;
    while (second) {
        if (first->data != second->data) return false;
        first = first->next;
        second = second->next;
    }
    return true;
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

function isPalindrome(head) {
    if (!head || !head.next) return true;

    let slow = head, fast = head;
    while (fast && fast.next) {
        slow = slow.next;
        fast = fast.next.next;
    }

    let prev = null;
    while (slow) {
        let nextNode = slow.next;
        slow.next = prev;
        prev = slow;
        slow = nextNode;
    }

    let first = head, second = prev;
    while (second) {
        if (first.data !== second.data) return false;
        first = first.next;
        second = second.next;
    }

    return true;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def is_palindrome(head):
    if not head or not head.next:
        return True

    slow = head
    fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next

    prev = None
    while slow:
        nxt = slow.next
        slow.next = prev
        prev = slow
        slow = nxt

    first = head
    second = prev
    while second:
        if first.data != second.data:
            return False
        first = first.next
        second = second.next

    return True

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
