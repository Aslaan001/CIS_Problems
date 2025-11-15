## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int minimumRemovalsToFormMountainSequence(vector<int>& vals) {
    int n = vals.size();
    vector<int> left(n, 1), right(n, 1);

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (vals[j] < vals[i])
                left[i] = max(left[i], left[j] + 1);
        }
    }

    for (int i = n - 1; i >= 0; i--) {
        for (int j = n - 1; j > i; j--) {
            if (vals[j] < vals[i])
                right[i] = max(right[i], right[j] + 1);
        }
    }

    int maxMountain = 0;
    for (int i = 1; i < n - 1; i++) {
        if (left[i] > 1 && right[i] > 1)
            maxMountain = max(maxMountain, left[i] + right[i] - 1);
    }

    return n - maxMountain;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int minimumRemovalsToFormMountainSequence(int[] vals) {
    int n = vals.length;
    int[] left = new int[n];
    int[] right = new int[n];
    Arrays.fill(left, 1);
    Arrays.fill(right, 1);

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (vals[j] < vals[i]) {
                left[i] = Math.max(left[i], left[j] + 1);
            }
        }
    }

    for (int i = n - 1; i >= 0; i--) {
        for (int j = n - 1; j > i; j--) {
            if (vals[j] < vals[i]) {
                right[i] = Math.max(right[i], right[j] + 1);
            }
        }
    }

    int maxMountain = 0;
    for (int i = 1; i < n - 1; i++) {
        if (left[i] > 1 && right[i] > 1) {
            maxMountain = Math.max(maxMountain, left[i] + right[i] - 1);
        }
    }

    return n - maxMountain;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

#include <stdio.h>

int minimumRemovalsToFormMountainSequence(int* vals, int n) {
    int left[n], right[n];
    for (int i = 0; i < n; i++) left[i] = right[i] = 1;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (vals[j] < vals[i] && left[j] + 1 > left[i])
                left[i] = left[j] + 1;
        }
    }

    for (int i = n - 1; i >= 0; i--) {
        for (int j = n - 1; j > i; j--) {
            if (vals[j] < vals[i] && right[j] + 1 > right[i])
                right[i] = right[j] + 1;
        }
    }

    int maxMountain = 0;
    for (int i = 1; i < n - 1; i++) {
        if (left[i] > 1 && right[i] > 1) {
            int total = left[i] + right[i] - 1;
            if (total > maxMountain) maxMountain = total;
        }
    }

    return n - maxMountain;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function minimumRemovalsToFormMountainSequence(vals) {
  const n = vals.length;
  const left = Array(n).fill(1);
  const right = Array(n).fill(1);

  for (let i = 0; i < n; i++) {
    for (let j = 0; j < i; j++) {
      if (vals[j] < vals[i]) left[i] = Math.max(left[i], left[j] + 1);
    }
  }

  for (let i = n - 1; i >= 0; i--) {
    for (let j = n - 1; j > i; j--) {
      if (vals[j] < vals[i]) right[i] = Math.max(right[i], right[j] + 1);
    }
  }

  let maxMountain = 0;
  for (let i = 1; i < n - 1; i++) {
    if (left[i] > 1 && right[i] > 1)
      maxMountain = Math.max(maxMountain, left[i] + right[i] - 1);
  }

  return n - maxMountain;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def minimum_removals_to_form_mountain_sequence(vals):
    n = len(vals)
    left = [1] * n
    right = [1] * n

    for i in range(n):
        for j in range(i):
            if vals[j] < vals[i]:
                left[i] = max(left[i], left[j] + 1)

    for i in range(n - 1, -1, -1):
        for j in range(n - 1, i, -1):
            if vals[j] < vals[i]:
                right[i] = max(right[i], right[j] + 1)

    max_mountain = 0
    for i in range(1, n - 1):
        if left[i] > 1 and right[i] > 1:
            max_mountain = max(max_mountain, left[i] + right[i] - 1)

    return n - max_mountain

### METADATA

TimeLimit  
1000

MemoryLimit  
512
