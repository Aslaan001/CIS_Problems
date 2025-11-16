## CPP

### SOLUTION

const int MOD = 1e9 + 7;

int sumSubarrayMins(vector<int>& arr) {
    int n = arr.size();
    vector<int> left(n), right(n);
    stack<pair<int,int>> s1, s2;

    // Previous Less Element
    for (int i = 0; i < n; i++) {
        int cnt = 1;
        while (!s1.empty() && s1.top().first > arr[i]) {
            cnt += s1.top().second;
            s1.pop();
        }
        left[i] = cnt;
        s1.push({arr[i], cnt});
    }

    // Next Less Element
    for (int i = n-1; i >= 0; i--) {
        int cnt = 1;
        while (!s2.empty() && s2.top().first >= arr[i]) {
            cnt += s2.top().second;
            s2.pop();
        }
        right[i] = cnt;
        s2.push({arr[i], cnt});
    }

    long long ans = 0;
    for (int i = 0; i < n; i++) {
        ans = (ans + (long long)arr[i] * left[i] * right[i]) % MOD;
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION

static final int MOD = 1000000007;

public static int sumSubarrayMins(int[] arr) {
    int n = arr.length;
    int[] left = new int[n];
    int[] right = new int[n];
    Stack<int[]> s1 = new Stack<>();
    Stack<int[]> s2 = new Stack<>();

    // Previous Less
    for (int i = 0; i < n; i++) {
        int cnt = 1;
        while (!s1.isEmpty() && s1.peek()[0] > arr[i]) {
            cnt += s1.pop()[1];
        }
        left[i] = cnt;
        s1.push(new int[]{arr[i], cnt});
    }

    // Next Less
    for (int i = n-1; i >= 0; i--) {
        int cnt = 1;
        while (!s2.isEmpty() && s2.peek()[0] >= arr[i]) {
            cnt += s2.pop()[1];
        }
        right[i] = cnt;
        s2.push(new int[]{arr[i], cnt});
    }

    long ans = 0;
    for (int i = 0; i < n; i++) {
        ans = (ans + (long)arr[i] * left[i] * right[i]) % MOD;
    }
    return (int)ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION

#define MOD 1000000007

long long sumSubarrayMins(int* arr, int n) {
    int* left = (int*)malloc(n * sizeof(int));
    int* right = (int*)malloc(n * sizeof(int));
    Pair* stack1 = (Pair*)malloc(n * sizeof(Pair));
    Pair* stack2 = (Pair*)malloc(n * sizeof(Pair));
    int top1 = -1, top2 = -1;

    // Previous Less
    for (int i = 0; i < n; i++) {
        int cnt = 1;
        while (top1 >= 0 && stack1[top1].val > arr[i]) {
            cnt += stack1[top1--].count;
        }
        left[i] = cnt;
        stack1[++top1] = (Pair){arr[i], cnt};
    }

    // Next Less
    for (int i = n-1; i >= 0; i--) {
        int cnt = 1;
        while (top2 >= 0 && stack2[top2].val >= arr[i]) {
            cnt += stack2[top2--].count;
        }
        right[i] = cnt;
        stack2[++top2] = (Pair){arr[i], cnt};
    }

    long long ans = 0;
    for (int i = 0; i < n; i++) {
        ans = (ans + (long long)arr[i] * left[i] * right[i]) % MOD;
    }

    free(left); free(right); free(stack1); free(stack2);
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

const MOD = 1e9 + 7;

function sumSubarrayMins(arr) {
    const n = arr.length;
    const left = new Array(n).fill(0);
    const right = new Array(n).fill(0);

    let stack1 = [];
    for (let i = 0; i < n; i++) {
        let cnt = 1;
        while (stack1.length && stack1[stack1.length-1][0] > arr[i]) {
            cnt += stack1.pop()[1];
        }
        left[i] = cnt;
        stack1.push([arr[i], cnt]);
    }

    let stack2 = [];
    for (let i = n-1; i >= 0; i--) {
        let cnt = 1;
        while (stack2.length && stack2[stack2.length-1][0] >= arr[i]) {
            cnt += stack2.pop()[1];
        }
        right[i] = cnt;
        stack2.push([arr[i], cnt]);
    }

    let ans = 0n;
    for (let i = 0; i < n; i++) {
        ans = (ans + BigInt(arr[i]) * BigInt(left[i]) * BigInt(right[i])) % BigInt(MOD);
    }
    return Number(ans);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

MOD = 10**9 + 7

def sumSubarrayMins(arr):
    n = len(arr)
    left = [0]*n
    right = [0]*n

    stack1 = []
    for i in range(n):
        cnt = 1
        while stack1 and stack1[-1][0] > arr[i]:
            cnt += stack1.pop()[1]
        left[i] = cnt
        stack1.append((arr[i], cnt))

    stack2 = []
    for i in range(n-1, -1, -1):
        cnt = 1
        while stack2 and stack2[-1][0] >= arr[i]:
            cnt += stack2.pop()[1]
        right[i] = cnt
        stack2.append((arr[i], cnt))

    ans = 0
    for i in range(n):
        ans = (ans + arr[i] * left[i] * right[i]) % MOD
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256