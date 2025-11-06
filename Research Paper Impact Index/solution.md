## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int hIndex(vector<int>& citations) {
    sort(citations.begin(), citations.end(), greater<int>());
    int h = 0;
    for (int i = 0; i < citations.size(); i++) {
        if (citations[i] >= i + 1) h = i + 1;
        else break;
    }
    return h;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION


public static int hIndex(int[] citations) {
        Arrays.sort(citations);
        int n = citations.length;
        int h = 0;
        for (int i = 0; i < n; i++) {
            int papers = n - i;
            if (citations[i] >= papers) {
                h = papers;
                break;
            }
        }
        return h;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

#include <stdio.h>
#include <stdlib.h>

int cmpdesc(const void* a, const void* b) {
    return (*(int*)b - *(int*)a);
}

int hIndex(int* citations, int n) {
    qsort(citations, n, sizeof(int), cmpdesc);
    int h = 0;
    for (int i = 0; i < n; ++i) {
        if (citations[i] >= i + 1) h = i + 1;
        else break;
    }
    return h;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function hIndex(citations) {
  citations.sort((a, b) => b - a);
  let h = 0;
  for (let i = 0; i < citations.length; i++) {
    if (citations[i] >= i + 1) h = i + 1;
    else break;
  }
  return h;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def h_index(citations):
    citations.sort(reverse=True)
    h = 0
    for i, c in enumerate(citations):
        if c >= i + 1:
            h = i + 1
        else:
            break
    return h

### METADATA

TimeLimit
1000

MemoryLimit
512
