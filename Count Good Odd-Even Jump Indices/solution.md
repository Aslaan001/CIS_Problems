## CPP

### SOLUTION

int oddEvenJumps(vector<int>& a) {
    int n = a.size();
    vector<int> nextGreater(n, -1), nextSmaller(n, -1);

    vector<int> idx(n);
    iota(idx.begin(), idx.end(), 0);

    sort(idx.begin(), idx.end(), [&](int i, int j) {
        if (a[i] == a[j]) return i < j;
        return a[i] < a[j];
    });

    stack<int> st;
    for (int i : idx) {
        while (!st.empty() && st.top() < i) {
            nextGreater[st.top()] = i;
            st.pop();
        }
        st.push(i);
    }

    while (!st.empty()) st.pop();

    sort(idx.begin(), idx.end(), [&](int i, int j) {
        if (a[i] == a[j]) return i < j;
        return a[i] > a[j];
    });

    for (int i : idx) {
        while (!st.empty() && st.top() < i) {
            nextSmaller[st.top()] = i;
            st.pop();
        }
        st.push(i);
    }

    vector<vector<int>> dp(n, vector<int>(2, 0));
    dp[n - 1][0] = dp[n - 1][1] = 1;
    int ans = 1;

    for (int i = n - 2; i >= 0; i--) {
        if (nextGreater[i] != -1) dp[i][0] = dp[nextGreater[i]][1];
        if (nextSmaller[i] != -1) dp[i][1] = dp[nextSmaller[i]][0];
        if (dp[i][0]) ans++;
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

public static int oddEvenJumps(int[] a) {
    int n = a.length;
    int[] nextGreater = new int[n];
    int[] nextSmaller = new int[n];
    Arrays.fill(nextGreater, -1);
    Arrays.fill(nextSmaller, -1);

    Integer[] idx = new Integer[n];
    for (int i = 0; i < n; i++) idx[i] = i;

    Arrays.sort(idx, (i, j) -> a[i] == a[j] ? i - j : a[i] - a[j]);

    Stack<Integer> st = new Stack<>();
    for (int i : idx) {
        while (!st.isEmpty() && st.peek() < i) {
            nextGreater[st.pop()] = i;
        }
        st.push(i);
    }
    st.clear();

    Arrays.sort(idx, (i, j) -> a[i] == a[j] ? i - j : a[j] - a[i]);

    for (int i : idx) {
        while (!st.isEmpty() && st.peek() < i) {
            nextSmaller[st.pop()] = i;
        }
        st.push(i);
    }

    int[][] dp = new int[n][2];
    dp[n - 1][0] = dp[n - 1][1] = 1;
    int ans = 1;

    for (int i = n - 2; i >= 0; i--) {
        if (nextGreater[i] != -1) dp[i][0] = dp[nextGreater[i]][1];
        if (nextSmaller[i] != -1) dp[i][1] = dp[nextSmaller[i]][0];
        if (dp[i][0] == 1) ans++;
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

int oddEvenJumps(int* a, int n) {
    int nextGreater[n], nextSmaller[n];
    for (int i = 0; i < n; i++) nextGreater[i] = nextSmaller[i] = -1;

    int idx[n];
    for (int i = 0; i < n; i++) idx[i] = i;

    // sort increasing
    for (int i = 0; i < n; i++)
        for (int j = i + 1; j < n; j++)
            if (a[idx[i]] > a[idx[j]] || (a[idx[i]] == a[idx[j]] && idx[i] > idx[j])) {
                int t = idx[i]; idx[i] = idx[j]; idx[j] = t;
            }

    int st[n], top = -1;
    for (int k = 0; k < n; k++) {
        int i = idx[k];
        while (top >= 0 && st[top] < i) {
            nextGreater[st[top--]] = i;
        }
        st[++top] = i;
    }

    top = -1;

    // sort decreasing
    for (int i = 0; i < n; i++)
        for (int j = i + 1; j < n; j++)
            if (a[idx[i]] < a[idx[j]] || (a[idx[i]] == a[idx[j]] && idx[i] > idx[j])) {
                int t = idx[i]; idx[i] = idx[j]; idx[j] = t;
            }

    for (int k = 0; k < n; k++) {
        int i = idx[k];
        while (top >= 0 && st[top] < i) {
            nextSmaller[st[top--]] = i;
        }
        st[++top] = i;
    }

    int dp[n][2];
    for (int i = 0; i < n; i++) dp[i][0] = dp[i][1] = 0;
    dp[n - 1][0] = dp[n - 1][1] = 1;

    int ans = 1;
    for (int i = n - 2; i >= 0; i--) {
        if (nextGreater[i] != -1) dp[i][0] = dp[nextGreater[i]][1];
        if (nextSmaller[i] != -1) dp[i][1] = dp[nextSmaller[i]][0];
        if (dp[i][0]) ans++;
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

function oddEvenJumps(a) {
  const n = a.length;
  const nextGreater = Array(n).fill(-1);
  const nextSmaller = Array(n).fill(-1);

  const idx = Array.from({ length: n }, (_, i) => i);

  idx.sort((i, j) => a[i] === a[j] ? i - j : a[i] - a[j]);
  let st = [];
  for (let i of idx) {
    while (st.length && st[st.length - 1] < i) {
      nextGreater[st.pop()] = i;
    }
    st.push(i);
  }

  idx.sort((i, j) => a[i] === a[j] ? i - j : a[j] - a[i]);
  st = [];
  for (let i of idx) {
    while (st.length && st[st.length - 1] < i) {
      nextSmaller[st.pop()] = i;
    }
    st.push(i);
  }

  const dp = Array.from({ length: n }, () => [0, 0]);
  dp[n - 1][0] = dp[n - 1][1] = 1;

  let ans = 1;
  for (let i = n - 2; i >= 0; i--) {
    if (nextGreater[i] !== -1) dp[i][0] = dp[nextGreater[i]][1];
    if (nextSmaller[i] !== -1) dp[i][1] = dp[nextSmaller[i]][0];
    if (dp[i][0] === 1) ans++;
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

def odd_even_jumps(a):
    n = len(a)

    idx = list(range(n))
    idx.sort(key=lambda i: (a[i], i))
    nextGreater = [-1] * n
    stack = []
    for i in idx:
        while stack and stack[-1] < i:
            nextGreater[stack.pop()] = i
        stack.append(i)

    idx.sort(key=lambda i: (-a[i], i))
    nextSmaller = [-1] * n
    stack = []
    for i in idx:
        while stack and stack[-1] < i:
            nextSmaller[stack.pop()] = i
        stack.append(i)

    dp = [[0, 0] for _ in range(n)]
    dp[n - 1][0] = dp[n - 1][1] = 1

    ans = 1
    for i in range(n - 2, -1, -1):
        if nextGreater[i] != -1:
            dp[i][0] = dp[nextGreater[i]][1]
        if nextSmaller[i] != -1:
            dp[i][1] = dp[nextSmaller[i]][0]
        if dp[i][0] == 1:
            ans += 1

    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
