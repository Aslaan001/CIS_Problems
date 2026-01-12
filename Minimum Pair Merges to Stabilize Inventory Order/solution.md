## CPP

### SOLUTION

int minimumPairRemoval(vector<int>& nums) {
    int ops = 0;

    auto isSorted = [&](const vector<int>& a) {
        for (int i = 1; i < a.size(); i++) {
            if (a[i] < a[i - 1]) return false;
        }
        return true;
    };

    while (!isSorted(nums)) {
        int idx = 0;
        int minSum = nums[0] + nums[1];

        for (int i = 1; i + 1 < nums.size(); i++) {
            int s = nums[i] + nums[i + 1];
            if (s < minSum) {
                minSum = s;
                idx = i;
            }
        }

        nums[idx] = nums[idx] + nums[idx + 1];
        nums.erase(nums.begin() + idx + 1);
        ops++;
    }

    return ops;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int minimumPairRemoval(int[] nums) {
    List<Integer> list = new ArrayList<>();
    for (int x : nums) list.add(x);

    int ops = 0;

    while (true) {
        boolean sorted = true;
        for (int i = 1; i < list.size(); i++) {
            if (list.get(i) < list.get(i - 1)) {
                sorted = false;
                break;
            }
        }
        if (sorted) break;

        int idx = 0;
        int minSum = list.get(0) + list.get(1);

        for (int i = 1; i + 1 < list.size(); i++) {
            int s = list.get(i) + list.get(i + 1);
            if (s < minSum) {
                minSum = s;
                idx = i;
            }
        }

        int merged = list.get(idx) + list.get(idx + 1);
        list.set(idx, merged);
        list.remove(idx + 1);
        ops++;
    }

    return ops;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int minimumPairRemoval(int nums[], int n) {
    int ops = 0;

    while (1) {
        int sorted = 1;
        for (int i = 1; i < n; i++) {
            if (nums[i] < nums[i - 1]) {
                sorted = 0;
                break;
            }
        }
        if (sorted) break;

        int idx = 0;
        int minSum = nums[0] + nums[1];

        for (int i = 1; i + 1 < n; i++) {
            int s = nums[i] + nums[i + 1];
            if (s < minSum) {
                minSum = s;
                idx = i;
            }
        }

        nums[idx] = nums[idx] + nums[idx + 1];
        for (int i = idx + 1; i + 1 < n; i++) {
            nums[i] = nums[i + 1];
        }
        n--;
        ops++;
    }

    return ops;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function minimumPairRemoval(nums) {
    let ops = 0;

    const isSorted = (a) => {
        for (let i = 1; i < a.length; i++) {
            if (a[i] < a[i - 1]) return false;
        }
        return true;
    };

    while (!isSorted(nums)) {
        let idx = 0;
        let minSum = nums[0] + nums[1];

        for (let i = 1; i + 1 < nums.length; i++) {
            const s = nums[i] + nums[i + 1];
            if (s < minSum) {
                minSum = s;
                idx = i;
            }
        }

        nums[idx] = nums[idx] + nums[idx + 1];
        nums.splice(idx + 1, 1);
        ops++;
    }

    return ops;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def minimum_pair_removal(nums):
    ops = 0

    def is_sorted(a):
        return all(a[i] >= a[i - 1] for i in range(1, len(a)))

    while not is_sorted(nums):
        idx = 0
        min_sum = nums[0] + nums[1]

        for i in range(1, len(nums) - 1):
            s = nums[i] + nums[i + 1]
            if s < min_sum:
                min_sum = s
                idx = i

        nums[idx] = nums[idx] + nums[idx + 1]
        nums.pop(idx + 1)
        ops += 1

    return ops

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
