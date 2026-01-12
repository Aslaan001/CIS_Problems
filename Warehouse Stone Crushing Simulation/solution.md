## CPP

### SOLUTION

int lastStoneWeight(vector<int>& stones) {
    priority_queue<int> pq;
    for (int x : stones) pq.push(x);

    while (pq.size() > 1) {
        int y = pq.top(); pq.pop();
        int x = pq.top(); pq.pop();
        if (y != x) pq.push(y - x);
    }

    return pq.empty() ? 0 : pq.top();
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVA

### SOLUTION

public static int lastStoneWeight(int[] stones) {
    PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());
    for (int x : stones) pq.offer(x);

    while (pq.size() > 1) {
        int y = pq.poll();
        int x = pq.poll();
        if (y != x) pq.offer(y - x);
    }

    return pq.isEmpty() ? 0 : pq.peek();
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## C

### SOLUTION

int lastStoneWeight(int stones[], int n) {
    int heap[100], size = 0;

    for (int i = 0; i < n; i++) heap[size++] = stones[i];

    while (size > 1) {
        int max1 = -1, max2 = -1, i1 = -1, i2 = -1;

        for (int i = 0; i < size; i++) {
            if (heap[i] > max1) {
                max2 = max1; i2 = i1;
                max1 = heap[i]; i1 = i;
            } else if (heap[i] > max2) {
                max2 = heap[i]; i2 = i;
            }
        }

        if (i1 > i2) {
            int t = i1; i1 = i2; i2 = t;
        }

        heap[i1] = max1 - max2;
        heap[i2] = heap[size - 1];
        size--;

        if (heap[i1] == 0) {
            heap[i1] = heap[size - 1];
            size--;
        }
    }

    return size == 0 ? 0 : heap[0];
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVASCRIPT

### SOLUTION

function lastStoneWeight(stones) {
    const pq = stones.slice();
    pq.sort((a, b) => b - a);

    while (pq.length > 1) {
        const y = pq.shift();
        const x = pq.shift();
        if (y !== x) {
            pq.push(y - x);
            pq.sort((a, b) => b - a);
        }
    }

    return pq.length ? pq[0] : 0;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## PYTHON

### SOLUTION

import heapq

def last_stone_weight(stones):
    pq = [-x for x in stones]
    heapq.heapify(pq)

    while len(pq) > 1:
        y = -heapq.heappop(pq)
        x = -heapq.heappop(pq)
        if y != x:
            heapq.heappush(pq, -(y - x))

    return -pq[0] if pq else 0

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
