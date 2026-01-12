## CPP

### SOLUTION

int longestSubarray(vector<int>& nums, int limit) {
    deque<int> maxdq, mindq;
    int left = 0, ans = 0;

    for (int right = 0; right < nums.size(); right++) {
        while (!maxdq.empty() && nums[maxdq.back()] < nums[right]) {
            maxdq.pop_back();
        }
        while (!mindq.empty() && nums[mindq.back()] > nums[right]) {
            mindq.pop_back();
        }

        maxdq.push_back(right);
        mindq.push_back(right);

        while (nums[maxdq.front()] - nums[mindq.front()] > limit) {
            left++;
            if (maxdq.front() < left) maxdq.pop_front();
            if (mindq.front() < left) mindq.pop_front();
        }

        ans = max(ans, right - left + 1);
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

public static int longestSubarray(int[] nums, int limit) {
    Deque<Integer> maxdq = new ArrayDeque<>();
    Deque<Integer> mindq = new ArrayDeque<>();
    int left = 0, ans = 0;

    for (int right = 0; right < nums.length; right++) {
        while (!maxdq.isEmpty() && nums[maxdq.peekLast()] < nums[right]) {
            maxdq.pollLast();
        }
        while (!mindq.isEmpty() && nums[mindq.peekLast()] > nums[right]) {
            mindq.pollLast();
        }

        maxdq.offerLast(right);
        mindq.offerLast(right);

        while (nums[maxdq.peekFirst()] - nums[mindq.peekFirst()] > limit) {
            left++;
            if (maxdq.peekFirst() < left) maxdq.pollFirst();
            if (mindq.peekFirst() < left) mindq.pollFirst();
        }

        ans = Math.max(ans, right - left + 1);
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

int longestSubarray(int nums[], int n, int limit) {
    int maxdq[100005], mindq[100005];
    int maxf = 0, maxb = 0, minf = 0, minb = 0;
    int left = 0, ans = 0;

    for (int right = 0; right < n; right++) {
        while (maxb > maxf && nums[maxdq[maxb - 1]] < nums[right]) maxb--;
        while (minb > minf && nums[mindq[minb - 1]] > nums[right]) minb--;

        maxdq[maxb++] = right;
        mindq[minb++] = right;

        while (nums[maxdq[maxf]] - nums[mindq[minf]] > limit) {
            left++;
            if (maxdq[maxf] < left) maxf++;
            if (mindq[minf] < left) minf++;
        }

        int len = right - left + 1;
        if (len > ans) ans = len;
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

function longestSubarray(nums, limit) {
    const maxdq = [];
    const mindq = [];
    let left = 0, ans = 0;

    for (let right = 0; right < nums.length; right++) {
        while (maxdq.length && nums[maxdq[maxdq.length - 1]] < nums[right]) {
            maxdq.pop();
        }
        while (mindq.length && nums[mindq[mindq.length - 1]] > nums[right]) {
            mindq.pop();
        }

        maxdq.push(right);
        mindq.push(right);

        while (nums[maxdq[0]] - nums[mindq[0]] > limit) {
            left++;
            if (maxdq[0] < left) maxdq.shift();
            if (mindq[0] < left) mindq.shift();
        }

        ans = Math.max(ans, right - left + 1);
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

from collections import deque

def longest_subarray(nums, limit):
    maxdq = deque()
    mindq = deque()
    left = 0
    ans = 0

    for right, val in enumerate(nums):
        while maxdq and nums[maxdq[-1]] < val:
            maxdq.pop()
        while mindq and nums[mindq[-1]] > val:
            mindq.pop()

        maxdq.append(right)
        mindq.append(right)

        while nums[maxdq[0]] - nums[mindq[0]] > limit:
            left += 1
            if maxdq[0] < left:
                maxdq.popleft()
            if mindq[0] < left:
                mindq.popleft()

        ans = max(ans, right - left + 1)

    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
