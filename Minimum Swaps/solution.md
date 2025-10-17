## CPP

### SOLUTION

int minimumSwapsToSort(vector<int>& nums) {
    int n = nums.size();
    vector<pair<int,int>> arrPos(n);
    for (int i = 0; i < n; i++)
        arrPos[i] = {nums[i], i};

    sort(arrPos.begin(), arrPos.end());

    vector<bool> visited(n, false);
    int ans = 0;

    for (int i = 0; i < n; i++) {
        if (visited[i] || arrPos[i].second == i)
            continue;

        int cycle_size = 0;
        int j = i;
        while (!visited[j]) {
            visited[j] = true;
            j = arrPos[j].second;
            cycle_size++;
        }

        if (cycle_size > 1)
            ans += (cycle_size - 1);
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

public static int minimumSwapsToSort(int[] nums) {
    int n = nums.length;
    int[][] arrPos = new int[n][2];
    for (int i = 0; i < n; i++) {
        arrPos[i][0] = nums[i];
        arrPos[i][1] = i;
    }

    Arrays.sort(arrPos, Comparator.comparingInt(a -> a[0]));

    boolean[] visited = new boolean[n];
    int ans = 0;

    for (int i = 0; i < n; i++) {
        if (visited[i] || arrPos[i][1] == i)
            continue;

        int cycle_size = 0;
        int j = i;
        while (!visited[j]) {
            visited[j] = true;
            j = arrPos[j][1];
            cycle_size++;
        }

        if (cycle_size > 1)
            ans += (cycle_size - 1);
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

#include <stdlib.h>

int compare(const void *a, const void *b) {
    int *p1 = (int *)a;
    int *p2 = (int *)b;
    return p1[0] - p2[0];
}

int minimumSwapsToSort(int nums[], int n) {
    int arrPos[n][2];
    for (int i = 0; i < n; i++) {
        arrPos[i][0] = nums[i];
        arrPos[i][1] = i;
    }

    qsort(arrPos, n, sizeof(arrPos[0]), compare);

    int visited[n];
    for (int i = 0; i < n; i++) visited[i] = 0;

    int ans = 0;

    for (int i = 0; i < n; i++) {
        if (visited[i] || arrPos[i][1] == i) continue;

        int cycle_size = 0;
        int j = i;
        while (!visited[j]) {
            visited[j] = 1;
            j = arrPos[j][1];
            cycle_size++;
        }

        if (cycle_size > 1)
            ans += (cycle_size - 1);
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

function minimumSwapsToSort(nums) {
    const n = nums.length;
    const arrPos = nums.map((val, idx) => [val, idx]);
    arrPos.sort((a, b) => a[0] - b[0]);

    const visited = Array(n).fill(false);
    let ans = 0;

    for (let i = 0; i < n; i++) {
        if (visited[i] || arrPos[i][1] === i) continue;

        let cycle_size = 0;
        let j = i;
        while (!visited[j]) {
            visited[j] = true;
            j = arrPos[j][1];
            cycle_size++;
        }

        if (cycle_size > 1) ans += (cycle_size - 1);
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

def minimumSwapsToSort(nums):
    n = len(nums)
    arrPos = [(val, idx) for idx, val in enumerate(nums)]
    arrPos.sort(key=lambda x: x[0])
    visited = [False] * n
    ans = 0

    for i in range(n):
        if visited[i] or arrPos[i][1] == i:
            continue

        cycle_size = 0
        j = i
        while not visited[j]:
            visited[j] = True
            j = arrPos[j][1]
            cycle_size += 1

        if cycle_size > 1:
            ans += (cycle_size - 1)

    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
