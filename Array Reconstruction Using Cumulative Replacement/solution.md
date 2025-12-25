## CPP

### SOLUTION

bool isPossible(vector<long long>& target) {
    priority_queue<long long> pq;
    long long sum = 0;

    for (long long x : target) {
        pq.push(x);
        sum += x;
    }

    while (pq.top() != 1) {
        long long mx = pq.top();
        pq.pop();
        long long rest = sum - mx;

        if (rest <= 0 || rest >= mx) return false;

        long long prev = mx % rest;
        if (prev == 0 && rest != 1) return false;

        pq.push(prev);
        sum = rest + prev;
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

public static boolean isPossible(long[] target) {
    PriorityQueue<Long> pq = new PriorityQueue<>(Collections.reverseOrder());
    long sum = 0;

    for (long x : target) {
        pq.offer(x);
        sum += x;
    }

    while (pq.peek() != 1) {
        long mx = pq.poll();
        long rest = sum - mx;

        if (rest <= 0 || rest >= mx) return false;

        long prev = mx % rest;
        if (prev == 0 && rest != 1) return false;

        pq.offer(prev);
        sum = rest + prev;
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

int isPossible(long long* target, int n) {
    long long sum = 0;
    for (int i = 0; i < n; i++) sum += target[i];

    while (1) {
        int idx = 0;
        for (int i = 1; i < n; i++) {
            if (target[i] > target[idx]) idx = i;
        }

        if (target[idx] == 1) return 1;

        long long rest = sum - target[idx];
        if (rest <= 0 || rest >= target[idx]) return 0;

        long long prev = target[idx] % rest;
        if (prev == 0 && rest != 1) return 0;

        sum = rest + prev;
        target[idx] = prev;
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function isPossible(target) {
  const pq = [];
  let sum = 0n;

  for (let x of target) {
    pq.push(BigInt(x));
    sum += BigInt(x);
  }

  pq.sort((a, b) => (a > b ? -1 : 1));

  while (pq[0] !== 1n) {
    const mx = pq.shift();
    const rest = sum - mx;

    if (rest <= 0n || rest >= mx) return false;

    const prev = mx % rest;
    if (prev === 0n && rest !== 1n) return false;

    pq.push(prev);
    sum = rest + prev;
    pq.sort((a, b) => (a > b ? -1 : 1));
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

import heapq

def is_possible(target):
    heap = [-x for x in target]
    heapq.heapify(heap)
    total = sum(target)

    while -heap[0] != 1:
        mx = -heapq.heappop(heap)
        rest = total - mx

        if rest <= 0 or rest >= mx:
            return False

        prev = mx % rest
        if prev == 0 and rest != 1:
            return False

        total = rest + prev
        heapq.heappush(heap, -prev)

    return True

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
