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

Node* insertAtKthPosition(Node* head, int data, int k) {
    Node* newNode = new Node(data);

    if (k == 1) {
        newNode->next = head;
        if (head != nullptr) {
            head->prev = newNode;
        }
        head = newNode;
        return head;
    }

    Node* curr = head;
    for (int i = 0; i < k - 2; i++) {
        if (curr == nullptr) { 
            delete newNode;
            return head; 
        }
        curr = curr->next;
    }

    if (curr == nullptr) {
        delete newNode;
        return head;
    }
    
    Node* nextNode = curr->next;

    curr->next = newNode;
    newNode->prev = curr;
    newNode->next = nextNode;

    if (nextNode != nullptr) {
        nextNode->prev = newNode;
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
    Node prev;
    Node(int x) {
        data = x;
        next = null;
        prev = null;
    }
}
*/

public static Node insertAtKthPosition(Node head, int data, int k) {
    Node newNode = new Node(data);

    if (k == 1) {
        newNode.next = head;
        if (head != null) {
            head.prev = newNode;
        }
        head = newNode;
        return head;
    }

    Node curr = head;
    for (int i = 0; i < k - 2; i++) {
        if (curr == null) {
            return head;
        }
        curr = curr.next;
    }
    
    if (curr == null) {
       return head;
    }

    Node nextNode = curr.next;

    curr.next = newNode;
    newNode.prev = curr;
    newNode.next = nextNode;

    if (nextNode != null) {
        nextNode.prev = newNode;
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

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    newNode->prev = NULL;
    return newNode;
}
*/

struct Node* insertAtKthPosition(struct Node* head, int data, int k) {
    struct Node* newNode = createNode(data);

    if (k == 1) {
        newNode->next = head;
        if (head != NULL) {
            head->prev = newNode;
        }
        head = newNode;
        return head;
    }

    struct Node* curr = head;
    for (int i = 0; i < k - 2; i++) {
         if (curr == NULL) {
            free(newNode);
            return head;
        }
        curr = curr->next;
    }

    if (curr == NULL) {
       free(newNode);
       return head;
    }
    
    struct Node* nextNode = curr->next;

    curr->next = newNode;
    newNode->prev = curr;
    newNode->next = nextNode;

    if (nextNode != NULL) {
        nextNode->prev = newNode;
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
        this.prev = null;
    }
}
*/

function insertAtKthPosition(head, data, k) {
    const newNode = new Node(data);

    if (k === 1) {
        newNode.next = head;
        if (head) {
            head.prev = newNode;
        }
        head = newNode;
        return head;
    }

    let curr = head;
    for (let i = 0; i < k - 2; i++) {
        if (!curr) {
            return head;
        }
        curr = curr.next;
    }

    if (!curr) {
       return head;
    }
    
    const nextNode = curr.next;

    curr.next = newNode;
    newNode.prev = curr;
    newNode.next = nextNode;

    if (nextNode) {
        nextNode.prev = newNode;
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

def insert_at_kth_position(head, data, k):
    new_node = Node(data)

    if k == 1:
        new_node.next = head
        if head:
            head.prev = new_node
        head = new_node
        return head

    curr = head
    for _ in range(k - 2):
        if curr is None:
            return head
        curr = curr.next

    if curr is None:
       return head
       
    next_node = curr.next

    curr.next = new_node
    new_node.prev = curr
    new_node.next = next_node

    if next_node:
        next_node.prev = new_node

    return head


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512