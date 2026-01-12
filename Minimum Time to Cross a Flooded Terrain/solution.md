## CPP

### SOLUTION

int swimInWater(vector<vector<int>>& grid) {
    int n = grid.size();
    priority_queue<pair<int, pair<int,int>>, vector<pair<int, pair<int,int>>>, greater<>> pq;
    vector<vector<int>> vis(n, vector<int>(n, 0));

    pq.push({grid[0][0], {0, 0}});
    vis[0][0] = 1;

    int ans = 0;
    int dx[4] = {1, -1, 0, 0};
    int dy[4] = {0, 0, 1, -1};

    while (!pq.empty()) {
        auto cur = pq.top(); pq.pop();
        int t = cur.first;
        int x = cur.second.first;
        int y = cur.second.second;

        ans = max(ans, t);
        if (x == n - 1 && y == n - 1) return ans;

        for (int d = 0; d < 4; d++) {
            int nx = x + dx[d];
            int ny = y + dy[d];
            if (nx >= 0 && ny >= 0 && nx < n && ny < n && !vis[nx][ny]) {
                vis[nx][ny] = 1;
                pq.push({grid[nx][ny], {nx, ny}});
            }
        }
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVA

### SOLUTION

public static int swimInWater(int[][] grid) {
    int n = grid.length;
    boolean[][] vis = new boolean[n][n];

    PriorityQueue<int[]> pq = new PriorityQueue<>(Comparator.comparingInt(a -> a[0]));
    pq.offer(new int[]{grid[0][0], 0, 0});
    vis[0][0] = true;

    int ans = 0;
    int[] dx = {1, -1, 0, 0};
    int[] dy = {0, 0, 1, -1};

    while (!pq.isEmpty()) {
        int[] cur = pq.poll();
        int t = cur[0], x = cur[1], y = cur[2];
        ans = Math.max(ans, t);

        if (x == n - 1 && y == n - 1) return ans;

        for (int d = 0; d < 4; d++) {
            int nx = x + dx[d];
            int ny = y + dy[d];
            if (nx >= 0 && ny >= 0 && nx < n && ny < n && !vis[nx][ny]) {
                vis[nx][ny] = true;
                pq.offer(new int[]{grid[nx][ny], nx, ny});
            }
        }
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## C

### SOLUTION

int swimInWater(int grid[][50], int n) {
    int vis[50][50] = {0};
    int dx[4] = {1, -1, 0, 0};
    int dy[4] = {0, 0, 1, -1};

    int heap[2500][3];
    int size = 0;

    heap[size][0] = grid[0][0];
    heap[size][1] = 0;
    heap[size][2] = 0;
    size++;
    vis[0][0] = 1;

    int ans = 0;

    while (size > 0) {
        int idx = 0;
        for (int i = 1; i < size; i++) {
            if (heap[i][0] < heap[idx][0]) idx = i;
        }

        int t = heap[idx][0];
        int x = heap[idx][1];
        int y = heap[idx][2];
        heap[idx][0] = heap[size - 1][0];
        heap[idx][1] = heap[size - 1][1];
        heap[idx][2] = heap[size - 1][2];
        size--;

        if (t > ans) ans = t;
        if (x == n - 1 && y == n - 1) return ans;

        for (int d = 0; d < 4; d++) {
            int nx = x + dx[d];
            int ny = y + dy[d];
            if (nx >= 0 && ny >= 0 && nx < n && ny < n && !vis[nx][ny]) {
                vis[nx][ny] = 1;
                heap[size][0] = grid[nx][ny];
                heap[size][1] = nx;
                heap[size][2] = ny;
                size++;
            }
        }
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVASCRIPT

### SOLUTION

function swimInWater(grid) {
    const n = grid.length;
    const vis = Array.from({ length: n }, () => Array(n).fill(false));
    const pq = [];
    pq.push([grid[0][0], 0, 0]);
    vis[0][0] = true;

    const dx = [1, -1, 0, 0];
    const dy = [0, 0, 1, -1];
    let ans = 0;

    while (pq.length) {
        pq.sort((a, b) => a[0] - b[0]);
        const [t, x, y] = pq.shift();
        ans = Math.max(ans, t);

        if (x === n - 1 && y === n - 1) return ans;

        for (let d = 0; d < 4; d++) {
            const nx = x + dx[d];
            const ny = y + dy[d];
            if (nx >= 0 && ny >= 0 && nx < n && ny < n && !vis[nx][ny]) {
                vis[nx][ny] = true;
                pq.push([grid[nx][ny], nx, ny]);
            }
        }
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## PYTHON

### SOLUTION

import heapq

def swim_in_water(grid):
    n = len(grid)
    vis = [[False]*n for _ in range(n)]
    pq = [(grid[0][0], 0, 0)]
    vis[0][0] = True

    ans = 0
    dirs = [(1,0), (-1,0), (0,1), (0,-1)]

    while pq:
        t, x, y = heapq.heappop(pq)
        ans = max(ans, t)
        if x == n - 1 and y == n - 1:
            return ans

        for dx, dy in dirs:
            nx, ny = x + dx, y + dy
            if 0 <= nx < n and 0 <= ny < n and not vis[nx][ny]:
                vis[nx][ny] = True
                heapq.heappush(pq, (grid[nx][ny], nx, ny))

    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
