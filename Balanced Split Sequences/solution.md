## CPP

### SOLUTION

long long countBalancedSplits(vector<int>& nums) {
    int mod = 1e9 + 7;
    int n = nums.size();
    int maximum = *max_element(nums.begin(), nums.end());
    vector<long long> dp(maximum + 1, 0);

    for (int j = 0; j <= maximum; j++) {
        dp[j] = 1;
        if (j <= nums[0]) {
            if (j > 0) dp[j] = (dp[j] + dp[j - 1]) % mod;
        } else {
            if (j > 0) dp[j] = (dp[j] + dp[j - 1] - 1 + mod) % mod;
        }
    }

    auto bs = [&](int j, int upper, int lower, int lastNum) {
        int l = 0, r = j;
        long long ans = -1;
        while (l <= r) {
            int mid = (l + r) / 2;
            int one = mid;
            int two = lastNum - mid;
            if (one <= upper && two >= lower) {
                ans = dp[mid];
                l = mid + 1;
            } else r = mid - 1;
        }
        return ans;
    };

    for (int i = 1; i < n; i++) {
        vector<long long> curr(maximum + 1, 0);
        for (int j = 0; j <= maximum; j++) {
            if (j > nums[i]) {
                if (j > 0) curr[j] = curr[j - 1];
                continue;
            }
            int upper = j;
            int lower = nums[i] - j;
            long long val = bs(j, upper, lower, nums[i - 1]);
            if (val != -1) curr[j] = val;
            if (j > 0) curr[j] = (curr[j] + curr[j - 1]) % mod;
        }
        dp = curr;
    }

    return dp[maximum];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static long countBalancedSplits(int[] nums) {
    int mod = 1000000007;
    int n = nums.length;
    int maximum = 0;
    for (int x : nums) maximum = Math.max(maximum, x);

    long[] dp = new long[maximum + 1];

    for (int j = 0; j <= maximum; j++) {
        dp[j] = 1;
        if (j <= nums[0]) {
            if (j > 0) dp[j] = (dp[j] + dp[j - 1]) % mod;
        } else {
            if (j > 0) dp[j] = (dp[j] + dp[j - 1] - 1 + mod) % mod;
        }
    }

    for (int i = 1; i < n; i++) {
        long[] curr = new long[maximum + 1];
        for (int j = 0; j <= maximum; j++) {
            if (j > nums[i]) {
                if (j > 0) curr[j] = curr[j - 1];
                continue;
            }
            int upper = j;
            int lower = nums[i] - j;

            long val = -1;
            int l = 0, r = j;
            while (l <= r) {
                int mid = (l + r) / 2;
                int one = mid;
                int two = nums[i - 1] - mid;
                if (one <= upper && two >= lower) {
                    val = dp[mid];
                    l = mid + 1;
                } else r = mid - 1;
            }

            if (val != -1) curr[j] = val;
            if (j > 0) curr[j] = (curr[j] + curr[j - 1]) % mod;
        }
        dp = curr;
    }

    return dp[maximum];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

long long countBalancedSplits(int nums[], int n) {
    int mod = 1000000007;
    int maximum = 0;
    for (int i = 0; i < n; i++)
        if (nums[i] > maximum) maximum = nums[i];

    long long dp[maximum + 1];

    for (int j = 0; j <= maximum; j++) {
        dp[j] = 1;
        if (j <= nums[0]) {
            if (j > 0) dp[j] = (dp[j] + dp[j - 1]) % mod;
        } else {
            if (j > 0) dp[j] = (dp[j] + dp[j - 1] - 1 + mod) % mod;
        }
    }

    for (int i = 1; i < n; i++) {
        long long curr[maximum + 1];
        for (int j = 0; j <= maximum; j++) {
            if (j > nums[i]) {
                if (j > 0) curr[j] = curr[j - 1];
                continue;
            }
            int upper = j;
            int lower = nums[i] - j;

            long long val = -1;
            int l = 0, r = j;
            while (l <= r) {
                int mid = (l + r) / 2;
                int one = mid;
                int two = nums[i - 1] - mid;
                if (one <= upper && two >= lower) {
                    val = dp[mid];
                    l = mid + 1;
                } else r = mid - 1;
            }

            curr[j] = (val != -1 ? val : 0);
            if (j > 0) curr[j] = (curr[j] + curr[j - 1]) % mod;
        }
        memcpy(dp, curr, sizeof(dp));
    }

    return dp[maximum];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function countBalancedSplits(nums) {
  const mod = 1e9 + 7;
  const n = nums.length;
  const maximum = Math.max(...nums);

  let dp = new Array(maximum + 1).fill(0);

  for (let j = 0; j <= maximum; j++) {
    dp[j] = 1;
    if (j <= nums[0]) {
      if (j > 0) dp[j] = (dp[j] + dp[j - 1]) % mod;
    } else {
      if (j > 0) dp[j] = (dp[j] + dp[j - 1] - 1 + mod) % mod;
    }
  }

  for (let i = 1; i < n; i++) {
    let curr = new Array(maximum + 1).fill(0);

    for (let j = 0; j <= maximum; j++) {
      if (j > nums[i]) {
        if (j > 0) curr[j] = curr[j - 1];
        continue;
      }

      const upper = j;
      const lower = nums[i] - j;

      let val = -1;
      let l = 0, r = j;
      while (l <= r) {
        let mid = (l + r) >> 1;
        let one = mid;
        let two = nums[i - 1] - mid;
        if (one <= upper && two >= lower) {
          val = dp[mid];
          l = mid + 1;
        } else r = mid - 1;
      }

      curr[j] = val !== -1 ? val : 0;
      if (j > 0) curr[j] = (curr[j] + curr[j - 1]) % mod;
    }

    dp = curr;
  }

  return dp[maximum];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def countBalancedSplits(nums):
    mod = 10**9 + 7
    n = len(nums)
    maximum = max(nums)

    dp = [0] * (maximum + 1)

    for j in range(maximum + 1):
        dp[j] = 1
        if j <= nums[0]:
            if j > 0:
                dp[j] = (dp[j] + dp[j - 1]) % mod
        else:
            if j > 0:
                dp[j] = (dp[j] + dp[j - 1] - 1) % mod

    for i in range(1, n):
        curr = [0] * (maximum + 1)

        for j in range(maximum + 1):
            if j > nums[i]:
                if j > 0:
                    curr[j] = curr[j - 1]
                continue

            upper = j
            lower = nums[i] - j

            val = -1
            l, r = 0, j
            while l <= r:
                mid = (l + r) // 2
                one = mid
                two = nums[i - 1] - mid
                if one <= upper and two >= lower:
                    val = dp[mid]
                    l = mid + 1
                else:
                    r = mid - 1

            curr[j] = val if val != -1 else 0

            if j > 0:
                curr[j] = (curr[j] + curr[j - 1]) % mod

        dp = curr

    return dp[maximum]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
