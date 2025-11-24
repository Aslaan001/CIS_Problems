## CPP

### SOLUTION

int countIslands(vector<vector<char>>& grid) {
    int m = grid.size(), n = grid[0].size();
    int ans = 0;

    function<void(int,int)> dfs = [&](int r, int c) {
        if (r < 0 || c < 0 || r >= m || c >= n) return;
        if (grid[r][c] == '0') return;
        grid[r][c] = '0';
        dfs(r+1,c);
        dfs(r-1,c);
        dfs(r,c+1);
        dfs(r,c-1);
    };

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (grid[i][j] == '1') {
                ans++;
                dfs(i,j);
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

public static int countIslands(char[][] grid) {
    int m = grid.length, n = grid[0].length;
    int ans = 0;

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (grid[i][j] == '1') {
                ans++;
                dfs(grid, i, j, m, n);
            }
        }
    }
    return ans;
}

static void dfs(char[][] grid, int r, int c, int m, int n) {
    if (r < 0 || c < 0 || r >= m || c >= n) return;
    if (grid[r][c] == '0') return;
    grid[r][c] = '0';
    dfs(grid, r+1, c, m, n);
    dfs(grid, r-1, c, m, n);
    dfs(grid, r, c+1, m, n);
    dfs(grid, r, c-1, m, n);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

void dfs(int r, int c, int m, int n, char grid[m][n]) {
    if (r < 0 || c < 0 || r >= m || c >= n) return;
    if (grid[r][c] == '0') return;
    grid[r][c] = '0';
    dfs(r+1, c, m, n, grid);
    dfs(r-1, c, m, n, grid);
    dfs(r, c+1, m, n, grid);
    dfs(r, c-1, m, n, grid);
}

int countIslands(int m, int n, char grid[m][n]) {
    int ans = 0;

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (grid[i][j] == '1') {
                ans++;
                dfs(i, j, m, n, grid);
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

function countIslands(grid) {
  const m = grid.length, n = grid[0].length;
  let ans = 0;

  function dfs(r, c) {
    if (r < 0 || c < 0 || r >= m || c >= n) return;
    if (grid[r][c] === "0") return;
    grid[r][c] = "0";
    dfs(r+1, c);
    dfs(r-1, c);
    dfs(r, c+1);
    dfs(r, c-1);
  }

  for (let i = 0; i < m; i++) {
    for (let j = 0; j < n; j++) {
      if (grid[i][j] === "1") {
        ans++;
        dfs(i, j);
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

def countIslands(grid):
    m, n = len(grid), len(grid[0])
    ans = 0

    def dfs(r, c):
        if r < 0 or c < 0 or r >= m or c >= n:
            return
        if grid[r][c] == "0":
            return
        grid[r][c] = "0"
        dfs(r+1, c)
        dfs(r-1, c)
        dfs(r, c+1)
        dfs(r, c-1)

    for i in range(m):
        for j in range(n):
            if grid[i][j] == "1":
                ans += 1
                dfs(i, j)

    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
