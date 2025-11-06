## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int findKthLargest(vector<int>& nums, int k) {
    priority_queue<int, vector<int>, greater<int>> pq;
    for (int num : nums) {
        pq.push(num);
        if (pq.size() > k) pq.pop();
    }
    return pq.top();
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

import java.util.*;

class Solution {
    public static int findKthLargest(int[] nums, int k) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        for (int num : nums) {
            pq.offer(num);
            if (pq.size() > k) pq.poll();
        }
        return pq.peek();
    }
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

int cmpDesc(const void* a, const void* b) {
    return (*(int*)b - *(int*)a);
}

int findKthLargest(int* nums, int n, int k) {
    qsort(nums, n, sizeof(int), cmpDesc);
    return nums[k - 1];
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function findKthLargest(nums, k) {
  nums.sort((a, b) => b - a);
  return nums[k - 1];
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

import heapq

def find_kth_largest(nums, k):
    return heapq.nlargest(k, nums)[-1]

### METADATA

TimeLimit
1000

MemoryLimit
512
