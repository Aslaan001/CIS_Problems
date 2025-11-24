## CPP

### SOLUTION

int countBattleships(vector<vector<char>>& board) {
    int m = board.size(), n = board[0].size();
    int ans = 0;

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (board[i][j] != 'X') continue;
            if (i > 0 && board[i-1][j] == 'X') continue;
            if (j > 0 && board[i][j-1] == 'X') continue;
            ans++;
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

public static int countBattleships(char[][] board) {
    int m = board.length, n = board[0].length;
    int ans = 0;

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (board[i][j] != 'X') continue;
            if (i > 0 && board[i-1][j] == 'X') continue;
            if (j > 0 && board[i][j-1] == 'X') continue;
            ans++;
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

int countBattleships(int m, int n, char board[m][n]) {
    int ans = 0;

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (board[i][j] != 'X') continue;
            if (i > 0 && board[i-1][j] == 'X') continue;
            if (j > 0 && board[i][j-1] == 'X') continue;
            ans++;
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

function countBattleships(board) {
  const m = board.length, n = board[0].length;
  let ans = 0;

  for (let i = 0; i < m; i++) {
    for (let j = 0; j < n; j++) {
      if (board[i][j] !== "X") continue;
      if (i > 0 && board[i-1][j] === "X") continue;
      if (j > 0 && board[i][j-1] === "X") continue;
      ans++;
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

def countBattleships(board):
    m, n = len(board), len(board[0])
    ans = 0

    for i in range(m):
        for j in range(n):
            if board[i][j] != "X":
                continue
            if i > 0 and board[i-1][j] == "X":
                continue
            if j > 0 and board[i][j-1] == "X":
                continue
            ans += 1

    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
