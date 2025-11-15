## CPP

### SOLUTION

int solve(const vector<int>& nums) {
    vector<int> expected = nums;
    sort(expected.begin(), expected.end());

    int count = 0;
    for (int i = 0; i < nums.size(); i++) {
        if (nums[i] != expected[i]) count++;
    }
    return count;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION

public static int solve(int[] nums) {
    int[] expected = nums.clone();
    Arrays.sort(expected);

    int count = 0;
    for (int i = 0; i < nums.length; i++) {
        if (nums[i] != expected[i]) {
            count++;
        }
    }
    return count;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION

int compareInts(const void* a, const void* b) {
    int x = *(int*)a;
    int y = *(int*)b;
    return (x - y);
}

int solve(int* nums, int n) {
    int* expected = (int*)malloc(n * sizeof(int));
    for (int i = 0; i < n; i++) expected[i] = nums[i];

    qsort(expected, n, sizeof(int), compareInts);

    int count = 0;
    for (int i = 0; i < n; i++) {
        if (nums[i] != expected[i]) count++;
    }

    free(expected);
    return count;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION

function solve(nums) {
  const expected = [...nums].sort((a, b) => a - b);

  let count = 0;
  for (let i = 0; i < nums.length; i++) {
    if (nums[i] !== expected[i]) {
      count++;
    }
  }
  return count;
}

### METADATA

**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION

def solve(nums):
    expected = sorted(nums)
    count = 0
    for a, b in zip(nums, expected):
        if a != b:
            count += 1
    return count

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128
