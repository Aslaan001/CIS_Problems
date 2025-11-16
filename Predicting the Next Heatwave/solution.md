## CPP

### SOLUTION

vector<int> predictHeatwaveDays(vector<int>& dailyTemperatures) {
    int n = dailyTemperatures.size();
    vector<int> daysToWait(n, 0);
    stack<int> pendingDays;

    for (int i = 0; i < n; i++) {
        while (!pendingDays.empty() && dailyTemperatures[i] > dailyTemperatures[pendingDays.top()]) {
            int idx = pendingDays.top(); pendingDays.pop();
            daysToWait[idx] = i - idx;
        }
        pendingDays.push(i);
    }
    return daysToWait;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION

public static int[] predictHeatwaveDays(int[] dailyTemperatures) {
    int n = dailyTemperatures.length;
    int[] daysToWait = new int[n];
    Stack<Integer> pendingDays = new Stack<>();

    for (int i = 0; i < n; i++) {
        while (!pendingDays.isEmpty() && dailyTemperatures[i] > dailyTemperatures[pendingDays.peek()]) {
            int idx = pendingDays.pop();
            daysToWait[idx] = i - idx;
        }
        pendingDays.push(i);
    }
    return daysToWait;
}

### METADATA

**TimeLimit**
1500

**MemoryLimit**
256

## C

### SOLUTION

int* predictHeatwaveDays(int* dailyTemperatures, int n, int* returnSize) {
    int *daysToWait = (int*)calloc(n, sizeof(int));
    int *pendingDays = (int*)malloc(n * sizeof(int));
    int top = -1;

    for (int i = 0; i < n; i++) {
        while (top >= 0 && dailyTemperatures[i] > dailyTemperatures[pendingDays[top]]) {
            int idx = pendingDays[top--];
            daysToWait[idx] = i - idx;
        }
        pendingDays[++top] = i;
    }
    *returnSize = n;
    free(pendingDays);
    return daysToWait;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function predictHeatwaveDays(dailyTemperatures) {
    const n = dailyTemperatures.length;
    const daysToWait = Array(n).fill(0);
    const pendingDays = [];

    for (let i = 0; i < n; i++) {
        while (pendingDays.length && dailyTemperatures[i] > dailyTemperatures[pendingDays[pendingDays.length - 1]]) {
            const idx = pendingDays.pop();
            daysToWait[idx] = i - idx;
        }
        pendingDays.push(i);
    }
    return daysToWait;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def predictHeatwaveDays(dailyTemperatures: List[int]) -> List[int]:
    n = len(dailyTemperatures)
    daysToWait = [0] * n
    pendingDays = []

    for i, temp in enumerate(dailyTemperatures):
        while pendingDays and temp > dailyTemperatures[pendingDays[-1]]:
            idx = pendingDays.pop()
            daysToWait[idx] = i - idx
        pendingDays.append(i)
    return daysToWait

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256