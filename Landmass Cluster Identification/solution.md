## CPP

int numIslands(vector<vector<char>>& grid) {
    int n = grid.size();
    int m = grid[0].size();
    int cnt = 0;

    function<void(int,int)> dfs = [&](int i, int j) {
        if (i < 0 || j < 0 || i >= n || j >= m || grid[i][j] == '0')
            return;
        grid[i][j] = '0';
        dfs(i + 1, j);
        dfs(i - 1, j);
        dfs(i, j + 1);
        dfs(i, j - 1);
    };

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (grid[i][j] == '1') {
                cnt++;
                dfs(i, j);
            }
        }
    }
    return cnt;
}


## JAVA

public static int numIslands(char[][] grid) {
    int n = grid.length;
    int m = grid[0].length;
    int cnt = 0;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (grid[i][j] == '1') {
                cnt++;
                dfs(grid, i, j);
            }
        }
    }
    return cnt;
}

private static void dfs(char[][] grid, int i, int j) {
    if (i < 0 || j < 0 || i >= grid.length || j >= grid[0].length || grid[i][j] == '0')
        return;

    grid[i][j] = '0';
    dfs(grid, i + 1, j);
    dfs(grid, i - 1, j);
    dfs(grid, i, j + 1);
    dfs(grid, i, j - 1);
}


## C

void dfs(char** grid, int i, int j, int n, int m) {
    if (i < 0 || j < 0 || i >= n || j >= m || grid[i][j] == '0')
        return;

    grid[i][j] = '0';
    dfs(grid, i + 1, j, n, m);
    dfs(grid, i - 1, j, n, m);
    dfs(grid, i, j + 1, n, m);
    dfs(grid, i, j - 1, n, m);
}

int numIslands(char** grid, int n, int m) {
    int cnt = 0;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (grid[i][j] == '1') {
                cnt++;
                dfs(grid, i, j, n, m);
            }
        }
    }
    return cnt;
}


## JAVASCRIPT

function numIslands(grid) {
    const n = grid.length;
    const m = grid[0].length;
    let cnt = 0;

    function dfs(i, j) {
        if (i < 0 || j < 0 || i >= n || j >= m || grid[i][j] === '0')
            return;
        grid[i][j] = '0';
        dfs(i + 1, j);
        dfs(i - 1, j);
        dfs(i, j + 1);
        dfs(i, j - 1);
    }

    for (let i = 0; i < n; i++) {
        for (let j = 0; j < m; j++) {
            if (grid[i][j] === '1') {
                cnt++;
                dfs(i, j);
            }
        }
    }
    return cnt;
}


## PYTHON

def num_islands(grid):
    n = len(grid)
    m = len(grid[0])
    cnt = 0

    def dfs(i, j):
        if i < 0 or j < 0 or i >= n or j >= m or grid[i][j] == '0':
            return
        grid[i][j] = '0'
        dfs(i + 1, j)
        dfs(i - 1, j)
        dfs(i, j + 1)
        dfs(i, j - 1)

    for i in range(n):
        for j in range(m):
            if grid[i][j] == '1':
                cnt += 1
                dfs(i, j)

    return cnt
