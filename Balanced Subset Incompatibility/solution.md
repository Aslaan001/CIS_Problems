## CPP

### SOLUTION

int minTotalIncompatibility(vector<int>& nums, int k) {
    int n = nums.size();
    int m = n / k;

    // Pre-generate all valid subsets of size m with no duplicates
    vector<pair<int,int>> bmap; 
    for (int b = 0; b < (1 << n); b++) {
        if (__builtin_popcount(b) != m) continue;

        int mask = 0;
        int mx = 0, mn = 20;
        bool ok = true;
        for (int i = 0; i < n; i++) {
            if (b & (1 << i)) {
                if (mask & (1 << nums[i])) { ok = false; break; }
                mask |= (1 << nums[i]);
                mx = max(mx, nums[i]);
                mn = min(mn, nums[i]);
            }
        }
        if (ok) bmap.push_back({b, mx - mn});
    }

    sort(bmap.begin(), bmap.end());

    vector<int> dp(1 << n, -1);
    dp[0] = 0;

    for (int b = 0; b < (1 << n); b++) {
        if (dp[b] == -1) continue;
        if (__builtin_popcount(b) % m != 0) continue;

        for (auto &p : bmap) {
            int tb = p.first;
            if ((b & tb) != 0) continue;  
            int nb = b | tb;
            int val = dp[b] + p.second;
            if (dp[nb] == -1 || dp[nb] > val)
                dp[nb] = val;
        }
    }

    return dp[(1 << n) - 1];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int minTotalIncompatibility(int[] nums, int k) {
    int n = nums.length;
    int m = n / k;

    ArrayList<int[]> subs = new ArrayList<>();

    // generate subsets of size m
    int total = 1 << n;
    for (int b = 0; b < total; b++) {
        if (Integer.bitCount(b) != m) continue;

        boolean ok = true;
        int seen = 0, mx = 0, mn = 100;
        for (int i = 0; i < n; i++) {
            if ((b & (1 << i)) != 0) {
                int v = nums[i];
                if ((seen & (1 << v)) != 0) { ok = false; break; }
                seen |= (1 << v);
                mx = Math.max(mx, v);
                mn = Math.min(mn, v);
            }
        }
        if (ok) subs.add(new int[]{b, mx - mn});
    }

    int[] dp = new int[total];
    Arrays.fill(dp, -1);
    dp[0] = 0;

    for (int mask = 0; mask < total; mask++) {
        if (dp[mask] == -1) continue;
        if (Integer.bitCount(mask) % m != 0) continue;

        for (int[] sb : subs) {
            int b = sb[0];
            if ((mask & b) != 0) continue;
            int nm = mask | b;
            int v = dp[mask] + sb[1];
            if (dp[nm] == -1 || dp[nm] > v) dp[nm] = v;
        }
    }

    return dp[total - 1];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

long long minTotalIncompatibility(int nums[], int n, int k) {
    int m = n / k;
    int total = 1 << n;

    // collect valid subsets
    int *subs = malloc(total * sizeof(int));
    int *vals = malloc(total * sizeof(int));
    int sc = 0;

    for (int b = 0; b < total; b++) {
        if (__builtin_popcount(b) != m) continue;
        int seen = 0, mx = 0, mn = 100, ok = 1;

        for (int i = 0; i < n; i++) {
            if (b & (1 << i)) {
                int v = nums[i];
                if (seen & (1 << v)) { ok = 0; break; }
                seen |= (1 << v);
                if (v > mx) mx = v;
                if (v < mn) mn = v;
            }
        }
        if (ok) {
            subs[sc] = b;
            vals[sc] = mx - mn;
            sc++;
        }
    }

    long long *dp = malloc((total) * sizeof(long long));
    for (int i = 0; i < total; i++) dp[i] = -1;
    dp[0] = 0;

    for (int mask = 0; mask < total; mask++) {
        if (dp[mask] < 0) continue;
        if (__builtin_popcount(mask) % m != 0) continue;

        for (int i = 0; i < sc; i++) {
            int b = subs[i];
            if (mask & b) continue;
            int nm = mask | b;
            long long v = dp[mask] + vals[i];
            if (dp[nm] == -1 || dp[nm] > v) dp[nm] = v;
        }
    }

    long long ans = dp[total - 1];
    free(subs); free(vals); free(dp);
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function minTotalIncompatibility(nums, k) {
  const n = nums.length;
  const m = n / k;
  const total = 1 << n;

  const subs = [];
  for (let b = 0; b < total; b++) {
    if (bitCount(b) !== m) continue;

    let seen = 0, mx = 0, mn = 999, ok = true;
    for (let i = 0; i < n; i++) {
      if (b & (1 << i)) {
        const v = nums[i];
        if (seen & (1 << v)) { ok = false; break; }
        seen |= (1 << v);
        mx = Math.max(mx, v);
        mn = Math.min(mn, v);
      }
    }
    if (ok) subs.push([b, mx - mn]);
  }

  const dp = Array(total).fill(-1);
  dp[0] = 0;

  for (let mask = 0; mask < total; mask++) {
    if (dp[mask] === -1) continue;
    if (bitCount(mask) % m !== 0) continue;

    for (let [b, v] of subs) {
      if (mask & b) continue;
      const nm = mask | b;
      const val = dp[mask] + v;
      if (dp[nm] === -1 || dp[nm] > val) dp[nm] = val;
    }
  }

  return dp[total - 1];
}

function bitCount(x) {
  return x.toString(2).split('0').join('').length;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def minTotalIncompatibility(nums, k):
    n = len(nums)
    m = n // k
    total = 1 << n

    subs = []
    for b in range(total):
        if bin(b).count("1") != m:
            continue

        seen = set()
        mx = 0
        mn = 10**9
        ok = True

        for i in range(n):
            if b & (1 << i):
                v = nums[i]
                if v in seen:
                    ok = False
                    break
                seen.add(v)
                mx = max(mx, v)
                mn = min(mn, v)

        if ok:
            subs.append((b, mx - mn))

    dp = [-1] * total
    dp[0] = 0

    for mask in range(total):
        if dp[mask] == -1:
            continue
        if bin(mask).count("1") % m != 0:
            continue

        for b, val in subs:
            if mask & b:
                continue
            nm = mask | b
            newv = dp[mask] + val
            if dp[nm] == -1 or dp[nm] > newv:
                dp[nm] = newv

    return dp[-1]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
