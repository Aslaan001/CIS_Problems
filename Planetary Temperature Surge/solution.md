## CPP

### SOLUTION

vector<int> nextHigherTemperatures(vector<int>& temperatures) {
    int n = temperatures.size();
    vector<int> result(n, -1);
    stack<int> st;

    for (int i = 2 * n - 1; i >= 0; --i) {
        while (!st.empty() && st.top() <= temperatures[i % n])
            st.pop();
        if (i < n && !st.empty())
            result[i] = st.top();
        st.push(temperatures[i % n]);
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

public static int[] nextHigherTemperatures(int[] temperatures) {
    int n = temperatures.length;
    int[] result = new int[n];
    Arrays.fill(result, -1);
    Stack<Integer> st = new Stack<>();

    for (int i = 2 * n - 1; i >= 0; i--) {
        while (!st.isEmpty() && st.peek() <= temperatures[i % n])
            st.pop();
        if (i < n && !st.isEmpty())
            result[i] = st.peek();
        st.push(temperatures[i % n]);
    }
    return result;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION

int* nextHigherTemperatures(int* temperatures, int n, int* returnSize) {
    int* result = (int*)malloc(n * sizeof(int));
    for (int i = 0; i < n; i++) result[i] = -1;
    int* stack = (int*)malloc(2 * n * sizeof(int));
    int top = -1;

    for (int i = 2 * n - 1; i >= 0; i--) {
        int curr = temperatures[i % n];
        while (top >= 0 && stack[top] <= curr)
            top--;
        if (i < n && top >= 0)
            result[i] = stack[top];
        stack[++top] = curr;
    }

    *returnSize = n;
    free(stack);
    return result;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function nextHigherTemperatures(temperatures) {
  const n = temperatures.length;
  const result = new Array(n).fill(-1);
  const st = []; 

  for (let i = 2 * n - 1; i >= 0; --i) {
    const curr = temperatures[i % n];
    while (st.length && st[st.length - 1] <= curr) st.pop();
    if (i < n && st.length) result[i] = st[st.length - 1];
    st.push(curr);
  }
  return result;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def nextHigherTemperatures(temperatures):
    n = len(temperatures)
    result = [-1] * n
    stack = []  # store values

    for i in range(2 * n - 1, -1, -1):
        curr = temperatures[i % n]
        while stack and stack[-1] <= curr:
            stack.pop()
        if i < n and stack:
            result[i] = stack[-1]
        stack.append(curr)
    return result

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256