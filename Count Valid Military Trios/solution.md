## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int countValidMilitaryTrios(vector<int>& vals) {
    int n = vals.size();
    int total = 0;
    for (int j = 0; j < n; j++) {
        int lessLeft = 0, greaterLeft = 0, lessRight = 0, greaterRight = 0;
        for (int i = 0; i < j; i++) {
            if (vals[i] < vals[j]) lessLeft++;
            else if (vals[i] > vals[j]) greaterLeft++;
        }
        for (int k = j + 1; k < n; k++) {
            if (vals[k] < vals[j]) lessRight++;
            else if (vals[k] > vals[j]) greaterRight++;
        }
        total += lessLeft * greaterRight + greaterLeft * lessRight;
    }
    return total;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int countValidMilitaryTrios(int[] vals) {
    int n = vals.length;
    int total = 0;
    for (int j = 0; j < n; j++) {
        int lessLeft = 0, greaterLeft = 0, lessRight = 0, greaterRight = 0;
        for (int i = 0; i < j; i++) {
            if (vals[i] < vals[j]) lessLeft++;
            else if (vals[i] > vals[j]) greaterLeft++;
        }
        for (int k = j + 1; k < n; k++) {
            if (vals[k] < vals[j]) lessRight++;
            else if (vals[k] > vals[j]) greaterRight++;
        }
        total += lessLeft * greaterRight + greaterLeft * lessRight;
    }
    return total;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

#include <stdio.h>

int countValidMilitaryTrios(int* vals, int n) {
    int total = 0;
    for (int j = 0; j < n; j++) {
        int lessLeft = 0, greaterLeft = 0, lessRight = 0, greaterRight = 0;
        for (int i = 0; i < j; i++) {
            if (vals[i] < vals[j]) lessLeft++;
            else if (vals[i] > vals[j]) greaterLeft++;
        }
        for (int k = j + 1; k < n; k++) {
            if (vals[k] < vals[j]) lessRight++;
            else if (vals[k] > vals[j]) greaterRight++;
        }
        total += lessLeft * greaterRight + greaterLeft * lessRight;
    }
    return total;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function countValidMilitaryTrios(vals) {
  const n = vals.length;
  let total = 0;
  for (let j = 0; j < n; j++) {
    let lessLeft = 0, greaterLeft = 0, lessRight = 0, greaterRight = 0;
    for (let i = 0; i < j; i++) {
      if (vals[i] < vals[j]) lessLeft++;
      else if (vals[i] > vals[j]) greaterLeft++;
    }
    for (let k = j + 1; k < n; k++) {
      if (vals[k] < vals[j]) lessRight++;
      else if (vals[k] > vals[j]) greaterRight++;
    }
    total += lessLeft * greaterRight + greaterLeft * lessRight;
  }
  return total;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def count_valid_military_trios(vals):
    n = len(vals)
    total = 0
    for j in range(n):
        less_left = greater_left = less_right = greater_right = 0
        for i in range(j):
            if vals[i] < vals[j]:
                less_left += 1
            elif vals[i] > vals[j]:
                greater_left += 1
        for k in range(j + 1, n):
            if vals[k] < vals[j]:
                less_right += 1
            elif vals[k] > vals[j]:
                greater_right += 1
        total += less_left * greater_right + greater_left * less_right
    return total

### METADATA

TimeLimit  
1000

MemoryLimit  
512
