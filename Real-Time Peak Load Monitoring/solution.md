## CPP

### SOLUTION

vector<int> slidingWindowMaximum(vector<int>& nums, int k) {
    deque<int> dq;
    vector<int> ans;

    for (int i = 0; i < k; i++) {
        while (!dq.empty() && nums[i] >= nums[dq.back()]) {
            dq.pop_back();
        }
        dq.push_back(i);
    }

    ans.push_back(nums[dq.front()]);

    for (int i = k; i < nums.size(); i++) {
        while (!dq.empty() && nums[i] >= nums[dq.back()]) {
            dq.pop_back();
        }
        dq.push_back(i);

        if (dq.front() == i - k) {
            dq.pop_front();
        }

        ans.push_back(nums[dq.front()]);
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

public static int[] slidingWindowMaximum(int[] nums, int k) {
    Deque<Integer> dq = new ArrayDeque<>();
    int n = nums.length;
    int[] ans = new int[n - k + 1];
    int idx = 0;

    for (int i = 0; i < k; i++) {
        while (!dq.isEmpty() && nums[i] >= nums[dq.peekLast()]) {
            dq.pollLast();
        }
        dq.offerLast(i);
    }

    ans[idx++] = nums[dq.peekFirst()];

    for (int i = k; i < n; i++) {
        while (!dq.isEmpty() && nums[i] >= nums[dq.peekLast()]) {
            dq.pollLast();
        }
        dq.offerLast(i);

        if (dq.peekFirst() == i - k) {
            dq.pollFirst();
        }

        ans[idx++] = nums[dq.peekFirst()];
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

void slidingWindowMaximum(int* nums, int n, int k, int* result) {
    int dq[n];
    int front = 0, back = -1;
    int idx = 0;

    for (int i = 0; i < k; i++) {
        while (front <= back && nums[i] >= nums[dq[back]]) {
            back--;
        }
        dq[++back] = i;
    }

    result[idx++] = nums[dq[front]];

    for (int i = k; i < n; i++) {
        while (front <= back && nums[i] >= nums[dq[back]]) {
            back--;
        }
        dq[++back] = i;

        if (dq[front] == i - k) {
            front++;
        }

        result[idx++] = nums[dq[front]];
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function slidingWindowMaximum(nums, k) {
  const dq = [];
  const ans = [];

  for (let i = 0; i < k; i++) {
    while (dq.length && nums[i] >= nums[dq[dq.length - 1]]) {
      dq.pop();
    }
    dq.push(i);
  }

  ans.push(nums[dq[0]]);

  for (let i = k; i < nums.length; i++) {
    while (dq.length && nums[i] >= nums[dq[dq.length - 1]]) {
      dq.pop();
    }
    dq.push(i);

    if (dq[0] === i - k) {
      dq.shift();
    }

    ans.push(nums[dq[0]]);
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

def sliding_window_maximum(nums, k):
    dq = deque()
    ans = []

    for i in range(k):
        while dq and nums[i] >= nums[dq[-1]]:
            dq.pop()
        dq.append(i)

    ans.append(nums[dq[0]])

    for i in range(k, len(nums)):
        while dq and nums[i] >= nums[dq[-1]]:
            dq.pop()
        dq.append(i)

        if dq[0] == i - k:
            dq.popleft()

        ans.append(nums[dq[0]])

    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
