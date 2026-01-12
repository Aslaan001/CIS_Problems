## CPP

### SOLUTION

int furthestBuilding(vector<int>& heights, int bricks, int ladders) {
    priority_queue<int> pq;

    for (int i = 0; i < heights.size() - 1; i++) {
        int diff = heights[i + 1] - heights[i];
        if (diff > 0) {
            pq.push(diff);
            bricks -= diff;

            if (bricks < 0) {
                if (ladders == 0) return i;
                bricks += pq.top();
                pq.pop();
                ladders--;
            }
        }
    }
    return heights.size() - 1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int furthestBuilding(int[] heights, int bricks, int ladders) {
    PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());

    for (int i = 0; i < heights.length - 1; i++) {
        int diff = heights[i + 1] - heights[i];
        if (diff > 0) {
            pq.offer(diff);
            bricks -= diff;

            if (bricks < 0) {
                if (ladders == 0) return i;
                bricks += pq.poll();
                ladders--;
            }
        }
    }
    return heights.length - 1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int furthestBuilding(int heights[], int n, int bricks, int ladders) {
    int heap[100005], size = 0;

    for (int i = 0; i < n - 1; i++) {
        int diff = heights[i + 1] - heights[i];
        if (diff > 0) {
            heap[size++] = diff;
            bricks -= diff;

            if (bricks < 0) {
                if (ladders == 0) return i;

                int maxIdx = 0;
                for (int j = 1; j < size; j++) {
                    if (heap[j] > heap[maxIdx]) maxIdx = j;
                }
                bricks += heap[maxIdx];
                heap[maxIdx] = heap[size - 1];
                size--;
                ladders--;
            }
        }
    }
    return n - 1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function furthestBuilding(heights, bricks, ladders) {
    const pq = [];

    for (let i = 0; i < heights.length - 1; i++) {
        const diff = heights[i + 1] - heights[i];
        if (diff > 0) {
            pq.push(diff);
            bricks -= diff;
            pq.sort((a, b) => b - a);

            if (bricks < 0) {
                if (ladders === 0) return i;
                bricks += pq.shift();
                ladders--;
            }
        }
    }
    return heights.length - 1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

import heapq

def furthest_building(heights, bricks, ladders):
    pq = []

    for i in range(len(heights) - 1):
        diff = heights[i + 1] - heights[i]
        if diff > 0:
            heapq.heappush(pq, -diff)
            bricks -= diff

            if bricks < 0:
                if ladders == 0:
                    return i
                bricks += -heapq.heappop(pq)
                ladders -= 1

    return len(heights) - 1

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
