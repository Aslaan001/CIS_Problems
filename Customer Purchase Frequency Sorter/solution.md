## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

vector<int> sortbyFreq(vector<int>& nums) {
    unordered_map<int, int> freq;
    for (int x : nums) freq[x]++;
    sort(nums.begin(), nums.end(), [&](int a, int b) {
        if (freq[a] == freq[b]) return a > b;
        return freq[a] < freq[b];
    });
    return nums;
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
    public int[] sortbyFreq(int[] nums) {
        Map<Integer, Integer> freq = new HashMap<>();
        for (int x : nums) freq.put(x, freq.getOrDefault(x, 0) + 1);
        Integer[] arr = Arrays.stream(nums).boxed().toArray(Integer[]::new);
        Arrays.sort(arr, (a, b) -> {
            if (freq.get(a).equals(freq.get(b))) return b - a;
            return freq.get(a) - freq.get(b);
        });
        return Arrays.stream(arr).mapToInt(Integer::intValue).toArray();
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

typedef struct {
    int val;
    int freq;
} Item;

int cmp(const void* a, const void* b) {
    Item* x = (Item*)a;
    Item* y = (Item*)b;
    if (x->freq == y->freq) return y->val - x->val;
    return x->freq - y->freq;
}

void sortbyFreq(int nums[], int n) {
    int freq[201] = {0};
    for (int i = 0; i < n; i++) freq[nums[i] + 100]++;

    Item arr[n];
    for (int i = 0; i < n; i++) {
        arr[i].val = nums[i];
        arr[i].freq = freq[nums[i] + 100];
    }

    qsort(arr, n, sizeof(Item), cmp);

    for (int i = 0; i < n; i++) {
        nums[i] = arr[i].val;
    }
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function sortbyFreq(nums) {
  const freq = {};
  for (const num of nums) freq[num] = (freq[num] || 0) + 1;
  nums.sort((a, b) => (freq[a] === freq[b] ? b - a : freq[a] - freq[b]));
  return nums;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

from collections import Counter

def sort_by_freq(nums):
    freq = Counter(nums)
    nums.sort(key=lambda x: (freq[x], -x))
    return nums

### METADATA

TimeLimit
1000

MemoryLimit
512
