## CPP

### SOLUTION

int primePortalPath(vector<int>& nums) {
    auto factor = [&](int x) {
        vector<int> res;
        for (int d = 2; d * d <= x; d++) {
            if (x % d == 0) {
                res.push_back(d);
                while (x % d == 0) x /= d;
            }
        }
        if (x > 1) res.push_back(x);
        return res;
    };

    int n = nums.size();
    unordered_map<int, vector<int>> adj;
    for (int i = 0; i < n; i++) {
        vector<int> temp = factor(nums[i]);
        for (int p : temp) adj[p].push_back(i);
    }

    vector<int> dist(n, INT_MAX);
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> q;
    dist[0] = 0;
    q.push({0, 0});

    while (!q.empty()) {
        auto [dis, node] = q.top();
        q.pop();

        if (node + 1 < n && dist[node + 1] > dis + 1) {
            dist[node + 1] = dis + 1;
            q.push({dist[node + 1], node + 1});
        }
        if (node - 1 >= 0 && dist[node - 1] > dis + 1) {
            dist[node - 1] = dis + 1;
            q.push({dist[node - 1], node - 1});
        }

        for (int nxt : adj[nums[node]]) {
            if (dist[nxt] > dis + 1) {
                dist[nxt] = dis + 1;
                q.push({dist[nxt], nxt});
            }
        }
        adj[nums[node]].clear();
    }

    return dist[n - 1];
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

public static int primePortalPath(int[] nums) {
    int n = nums.length;
    Map<Integer, List<Integer>> adj = new HashMap<>();

    for (int i = 0; i < n; i++) {
        for (int p : factor(nums[i])) {
            adj.computeIfAbsent(p, k -> new ArrayList<>()).add(i);
        }
    }

    int[] dist = new int[n];
    Arrays.fill(dist, Integer.MAX_VALUE);
    PriorityQueue<int[]> pq = new PriorityQueue<>(Comparator.comparingInt(a -> a[0]));
    dist[0] = 0;
    pq.add(new int[]{0, 0});

    while (!pq.isEmpty()) {
        int[] curr = pq.poll();
        int dis = curr[0], node = curr[1];

        if (node + 1 < n && dist[node + 1] > dis + 1) {
            dist[node + 1] = dis + 1;
            pq.add(new int[]{dist[node + 1], node + 1});
        }
        if (node - 1 >= 0 && dist[node - 1] > dis + 1) {
            dist[node - 1] = dis + 1;
            pq.add(new int[]{dist[node - 1], node - 1});
        }

        if (adj.containsKey(nums[node])) {
            for (int nxt : adj.get(nums[node])) {
                if (dist[nxt] > dis + 1) {
                    dist[nxt] = dis + 1;
                    pq.add(new int[]{dist[nxt], nxt});
                }
            }
            adj.get(nums[node]).clear();
        }
    }

    return dist[n - 1];
}

private static List<Integer> factor(int x) {
    List<Integer> res = new ArrayList<>();
    for (int d = 2; d * d <= x; d++) {
        if (x % d == 0) {
            res.add(d);
            while (x % d == 0) x /= d;
        }
    }
    if (x > 1) res.add(x);
    return res;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

#include <limits.h>
#include <stdlib.h>
#include <stdbool.h>

long long primePortalPath(int* nums, int n) {
    int* dist = (int*)malloc(n * sizeof(int));
    for (int i = 0; i < n; i++) dist[i] = INT_MAX;
    dist[0] = 0;
    for (int i = 0; i < n - 1; i++) {
        if (dist[i + 1] > dist[i] + 1) dist[i + 1] = dist[i] + 1;
    }
    long long ans = dist[n - 1];
    free(dist);
    return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function primePortalPath(nums) {
    const factor = (x) => {
        const res = [];
        for (let d = 2; d * d <= x; d++) {
            if (x % d === 0) {
                res.push(d);
                while (x % d === 0) x /= d;
            }
        }
        if (x > 1) res.push(x);
        return res;
    };

    const n = nums.length;
    const adj = new Map();
    for (let i = 0; i < n; i++) {
        for (const p of factor(nums[i])) {
            if (!adj.has(p)) adj.set(p, []);
            adj.get(p).push(i);
        }
    }

    const dist = Array(n).fill(Infinity);
    const q = [[0, 0]];
    dist[0] = 0;

    while (q.length) {
        const [dis, node] = q.shift();
        if (node + 1 < n && dist[node + 1] > dis + 1) {
            dist[node + 1] = dis + 1;
            q.push([dist[node + 1], node + 1]);
        }
        if (node - 1 >= 0 && dist[node - 1] > dis + 1) {
            dist[node - 1] = dis + 1;
            q.push([dist[node - 1], node - 1]);
        }
        if (adj.has(nums[node])) {
            for (const nxt of adj.get(nums[node])) {
                if (dist[nxt] > dis + 1) {
                    dist[nxt] = dis + 1;
                    q.push([dist[nxt], nxt]);
                }
            }
            adj.delete(nums[node]);
        }
    }
    return dist[n - 1];
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def prime_portal_path(nums):
    def factors(x):
        res = []
        d = 2
        while d * d <= x:
            if x % d == 0:
                res.append(d)
                while x % d == 0:
                    x //= d
            d += 1
        if x > 1:
            res.append(x)
        return res

    n = len(nums)
    adj = {}
    for i in range(n):
        for p in factors(nums[i]):
            if p not in adj:
                adj[p] = []
            adj[p].append(i)

    dist = [float('inf')] * n
    dist[0] = 0
    from collections import deque
    q = deque([0])

    while q:
        node = q.popleft()
        dis = dist[node]
        if node + 1 < n and dist[node + 1] > dis + 1:
            dist[node + 1] = dis + 1
            q.append(node + 1)
        if node - 1 >= 0 and dist[node - 1] > dis + 1:
            dist[node - 1] = dis + 1
            q.append(node - 1)
        if nums[node] in adj:
            for nxt in adj[nums[node]]:
                if dist[nxt] > dis + 1:
                    dist[nxt] = dis + 1
                    q.append(nxt)
            del adj[nums[node]]
    return dist[-1]

### METADATA

TimeLimit
1000

MemoryLimit
512
