## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int kIndex(vector<int>& citations) {
    int n = citations.size();
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        int k = n - mid;
        if (citations[mid] == k) return k;
        else if (citations[mid] < k) low = mid + 1;
        else high = mid - 1;
    }
    return n - low;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  


## JAVA

### SOLUTION

public static int kIndex(int[] citations) {
    int n = citations.length;
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        int k = n - mid;
        if (citations[mid] == k) return k;
        else if (citations[mid] < k) low = mid + 1;
        else high = mid - 1;
    }
    return n - low;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  


## C

### SOLUTION

#include <stdio.h>

int kIndex(int* nums, int n) {
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        int k = n - mid;
        if (nums[mid] == k) return k;
        else if (nums[mid] < k) low = mid + 1;
        else high = mid - 1;
    }
    return n - low;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  


## JAVASCRIPT

### SOLUTION

function kIndex(nums) {
  let n = nums.length;
  let low = 0, high = n - 1;
  while (low <= high) {
    let mid = Math.floor((low + high) / 2);
    let k = n - mid;
    if (nums[mid] === k) return k;
    else if (nums[mid] < k) low = mid + 1;
    else high = mid - 1;
  }
  return n - low;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  


## PYTHON

### SOLUTION

def k_index(nums):
    n = len(nums)
    low, high = 0, n - 1
    while low <= high:
        mid = (low + high) // 2
        k = n - mid
        if nums[mid] == k:
            return k
        elif nums[mid] < k:
            low = mid + 1
        else:
            high = mid - 1
    return n - low

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  
