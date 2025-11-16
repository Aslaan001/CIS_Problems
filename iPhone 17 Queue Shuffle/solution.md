## CPP

### SOLUTION


queue<int> reverseLastK(queue<int> q, int k) {
    int n = q.size();
    if (k > n) return q; 

    stack<int> st;
    queue<int> result;

    for (int i = 0; i < n - k; i++) {
        result.push(q.front());
        q.pop();
    }

    while (!q.empty()) {
        st.push(q.front());
        q.pop();
    }

    while (!st.empty()) {
        result.push(st.top());
        st.pop();
    }

    return result;
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
256


## JAVA

### SOLUTION

public static Queue<Integer> reverseLastK(Queue<Integer> q, int k) {
    int n = q.size();
    if (k > n) return q;

    Queue<Integer> result = new LinkedList<>();
    Stack<Integer> st = new Stack<>();

    for (int i = 0; i < n - k; i++) {
        result.add(q.poll());
    }

    while (!q.isEmpty()) {
        st.push(q.poll());
    }

    while (!st.isEmpty()) {
        result.add(st.pop());
    }

    return result;
}


### METADATA

**TimeLimit**
1600

**MemoryLimit**
256

## C

### SOLUTION

void reverseLastK(int q[], int n, int k) {
    if (k > n) return;
    int left = n - k, right = n - 1;
    while (left < right) {
        int temp = q[left];
        q[left] = q[right];
        q[right] = temp;
        left++;
        right--;
    }
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function reverseLastK(queue, k) {
    let n = queue.length;
    if (k > n) return queue;

    let fixedPart = queue.slice(0, n - k);
    let reversedPart = queue.slice(n - k).reverse();

    return fixedPart.concat(reversedPart);
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def reverse_last_k(q: deque, k: int) -> deque:
    n = len(q)
    if k > n:
        return q  

    result = deque()
    for _ in range(n - k):
        result.append(q.popleft())
    
    stack = []
    while q:
        stack.append(q.popleft())
    while stack:
        result.append(stack.pop())

    return result


### METADATA

**TimeLimit**
1000

**MemoryLimit**
256