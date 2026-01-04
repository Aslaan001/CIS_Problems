## CPP

### SOLUTION

long long countStableSubarrays(vector<int>& nums) {
    deque<int> mx, mn;
    long long ans = 0;
    int i = 0;

    for (int j = 0; j < nums.size(); j++) {

        while (!mx.empty() && nums[mx.back()] < nums[j]) mx.pop_back();
        while (!mn.empty() && nums[mn.back()] > nums[j]) mn.pop_back();

        mx.push_back(j);
        mn.push_back(j);

        while (nums[mx.front()] - nums[mn.front()] > 2) {
            if (mx.front() == i) mx.pop_front();
            if (mn.front() == i) mn.pop_front();
            i++;
        }

        ans += (j - i + 1);
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

public static long countStableSubarrays(int[] nums) {
    Deque<Integer> mx = new ArrayDeque<>();
    Deque<Integer> mn = new ArrayDeque<>();

    long ans = 0;
    int i = 0;

    for (int j = 0; j < nums.length; j++) {

        while (!mx.isEmpty() && nums[mx.peekLast()] < nums[j]) mx.pollLast();
        while (!mn.isEmpty() && nums[mn.peekLast()] > nums[j]) mn.pollLast();

        mx.addLast(j);
        mn.addLast(j);

        while (nums[mx.peekFirst()] - nums[mn.peekFirst()] > 2) {
            if (mx.peekFirst() == i) mx.pollFirst();
            if (mn.peekFirst() == i) mn.pollFirst();
            i++;
        }

        ans += (j - i + 1);
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

long long countStableSubarrays(int* nums, int n) {
    int mx[n], mn[n];
    int mxl = 0, mxr = 0, mnl = 0, mnr = 0;

    long long ans = 0;
    int i = 0;

    for (int j = 0; j < n; j++) {

        while (mxr > mxl && nums[mx[mxr - 1]] < nums[j]) mxr--;
        while (mnr > mnl && nums[mn[mnr - 1]] > nums[j]) mnr--;

        mx[mxr++] = j;
        mn[mnr++] = j;

        while (nums[mx[mxl]] - nums[mn[mnl]] > 2) {
            if (mx[mxl] == i) mxl++;
            if (mn[mnl] == i) mnl++;
            i++;
        }

        ans += (j - i + 1);
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

function countStableSubarrays(nums) {
    let mx = [], mn = [];
    let i = 0, ans = 0;

    for (let j = 0; j < nums.length; j++) {

        while (mx.length && nums[mx[mx.length - 1]] < nums[j]) mx.pop();
        while (mn.length && nums[mn[mn.length - 1]] > nums[j]) mn.pop();

        mx.push(j);
        mn.push(j);

        while (nums[mx[0]] - nums[mn[0]] > 2) {
            if (mx[0] === i) mx.shift();
            if (mn[0] === i) mn.shift();
            i++;
        }

        ans += (j - i + 1);
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

def count_stable_subarrays(nums):
    from collections import deque

    mx = deque()
    mn = deque()
    i = 0
    ans = 0

    for j in range(len(nums)):

        while mx and nums[mx[-1]] < nums[j]:
            mx.pop()
        while mn and nums[mn[-1]] > nums[j]:
            mn.pop()

        mx.append(j)
        mn.append(j)

        while nums[mx[0]] - nums[mn[0]] > 2:
            if mx[0] == i:
                mx.popleft()
            if mn[0] == i:
                mn.popleft()
            i += 1

        ans += (j - i + 1)

    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
