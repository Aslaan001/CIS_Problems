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

Node* merge(Node* left, Node* right) {
    Node* dummy = new Node(0);
    Node* curr = dummy;

    while (left && right) {
        if (left->data < right->data) {
            curr->next = left;
            left = left->next;
        } else {
            curr->next = right;
            right = right->next;
        }
        curr = curr->next;
    }

    if (left) curr->next = left;
    if (right) curr->next = right;

    Node* head = dummy->next;
    delete dummy;
    return head;
}

Node* getMid(Node* head) {
    Node* slow = head;
    Node* fast = head->next;
    
    while (fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
    }
    return slow;
}

Node* sortList(Node* head) {
    if (!head || !head->next) {
        return head;
    }
    
    Node* mid = getMid(head);
    Node* rightHead = mid->next;
    mid->next = nullptr;
    
    Node* left = sortList(head);
    Node* right = sortList(rightHead);
    
    return merge(left, right);
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

public static Node merge(Node left, Node right) {
    Node dummy = new Node(0);
    Node curr = dummy;

    while (left != null && right != null) {
        if (left.data < right.data) {
            curr.next = left;
            left = left.next;
        } else {
            curr.next = right;
            right = right.next;
        }
        curr = curr.next;
    }

    if (left != null) curr.next = left;
    if (right != null) curr.next = right;

    return dummy.next;
}

public static Node getMid(Node head) {
    Node slow = head;
    Node fast = head.next;
    
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }
    return slow;
}

public static Node sortList(Node head) {
    if (head == null || head.next == null) {
        return head;
    }
    
    Node mid = getMid(head);
    Node rightHead = mid.next;
    mid.next = null;
    
    Node left = sortList(head);
    Node right = sortList(rightHead);
    
    return merge(left, right);
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

struct Node* merge(struct Node* left, struct Node* right) {
    struct Node* dummy = (struct Node*)malloc(sizeof(struct Node));
    dummy->data = 0;
    dummy->next = NULL;
    struct Node* curr = dummy;

    while (left && right) {
        if (left->data < right->data) {
            curr->next = left;
            left = left->next;
        } else {
            curr->next = right;
            right = right->next;
        }
        curr = curr->next;
    }

    if (left) curr->next = left;
    if (right) curr->next = right;

    struct Node* head = dummy->next;
    free(dummy);
    return head;
}

struct Node* getMid(struct Node* head) {
    struct Node* slow = head;
    struct Node* fast = head->next;
    
    while (fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
    }
    return slow;
}

struct Node* sortList(struct Node* head) {
    if (!head || !head->next) {
        return head;
    }
    
    struct Node* mid = getMid(head);
    struct Node* rightHead = mid->next;
    mid->next = NULL;
    
    struct Node* left = sortList(head);
    struct Node* right = sortList(rightHead);
    
    return merge(left, right);
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

function merge(left, right) {
    let dummy = new Node(0);
    let curr = dummy;

    while (left && right) {
        if (left.data < right.data) {
            curr.next = left;
            left = left.next;
        } else {
            curr.next = right;
            right = right.next;
        }
        curr = curr.next;
    }

    if (left) curr.next = left;
    if (right) curr.next = right;

    return dummy.next;
}

function getMid(head) {
    let slow = head;
    let fast = head.next;
    
    while (fast && fast.next) {
        slow = slow.next;
        fast = fast.next.next;
    }
    return slow;
}

function sortList(head) {
    if (!head || !head.next) {
        return head;
    }
    
    let mid = getMid(head);
    let rightHead = mid.next;
    mid.next = null;
    
    let left = sortList(head);
    let right = sortList(rightHead);
    
    return merge(left, right);
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

def merge(left, right):
    dummy = Node(0)
    curr = dummy
    
    while left and right:
        if left.data < right.data:
            curr.next = left
            left = left.next
        else:
            curr.next = right
            right = right.next
        curr = curr.next
        
    if left:
        curr.next = left
    if right:
        curr.next = right
        
    return dummy.next

def get_mid(head):
    slow = head
    fast = head.next
    
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow

def sort_list(head):
    if not head or not head.next:
        return head
        
    mid = get_mid(head)
    right_head = mid.next
    mid.next = None
    
    left = sort_list(head)
    right = sort_list(right_head)
    
    return merge(left, right)


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512