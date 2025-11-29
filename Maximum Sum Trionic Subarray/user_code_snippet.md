## CPP

### SOLUTION

long long maxTrionicSubarray(vector<int>& nums) {
    using ll = long long;
    ll n = nums.size();
    ll ans = -100000000000000000LL;

    vector<ll> pref(n, 0);
    pref[0] = nums[0];
    for (int i = 1; i < n; i++) pref[i] = pref[i - 1] + nums[i];

    vector<ll> inc(n, 1), dec(n, 1);

    ll ct1 = 1, ct2 = 1;
    for (int i = n - 2; i >= 0; i--) {
        if (nums[i] < nums[i + 1]) {
            ct1++;
            ct2 = 1;
        } else if (nums[i] > nums[i + 1]) {
            ct1 = 1;
            ct2++;
        } else {
            ct1 = ct2 = 1;
        }
        inc[i] = ct1;
        dec[i] = ct2;
    }

    for (int l = 0; l < n - 3; l++) {
        if (inc[l] > 1) {
            int p = l + inc[l] - 1;
            if (p + 1 < n && dec[p] > 1) {
                int q = p + dec[p] - 1;
                if (q + 1 < n && inc[q] > 1) {
                    int r1 = q + 1;
                    int r2 = q + inc[q] - 1;
                    if (r1 < n)
                        ans = max(ans, pref[r1] - pref[l] + nums[l]);
                    if (r2 < n)
                        ans = max(ans, pref[r2] - pref[l] + nums[l]);
                }
            }
        }
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

public static long maxTrionicSubarray(int[] nums) {
    int n = nums.length;
    long ans = -100000000000000000L;

    long[] pref = new long[n];
    pref[0] = nums[0];
    for (int i = 1; i < n; i++) pref[i] = pref[i - 1] + nums[i];

    long[] inc = new long[n];
    long[] dec = new long[n];
    Arrays.fill(inc, 1);
    Arrays.fill(dec, 1);

    long ct1 = 1, ct2 = 1;
    for (int i = n - 2; i >= 0; i--) {
        if (nums[i] < nums[i + 1]) {
            ct1++;
            ct2 = 1;
        } else if (nums[i] > nums[i + 1]) {
            ct1 = 1;
            ct2++;
        } else {
            ct1 = ct2 = 1;
        }
        inc[i] = ct1;
        dec[i] = ct2;
    }

    for (int l = 0; l < n - 3; l++) {
        if (inc[l] > 1) {
            int p = l + (int)inc[l] - 1;
            if (p + 1 < n && dec[p] > 1) {
                int q = p + (int)dec[p] - 1;
                if (q + 1 < n && inc[q] > 1) {
                    int r1 = q + 1;
                    int r2 = q + (int)inc[q] - 1;
                    if (r1 < n)
                        ans = Math.max(ans, pref[r1] - pref[l] + nums[l]);
                    if (r2 < n)
                        ans = Math.max(ans, pref[r2] - pref[l] + nums[l]);
                }
            }
        }
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

long long maxTrionicSubarray(long long* nums, int n) {
    long long ans = -100000000000000000LL;

    long long pref[n];
    pref[0] = nums[0];
    for (int i = 1; i < n; i++) pref[i] = pref[i - 1] + nums[i];

    long long inc[n], dec[n];
    for (int i = 0; i < n; i++) inc[i] = dec[i] = 1;

    long long ct1 = 1, ct2 = 1;
    for (int i = n - 2; i >= 0; i--) {
        if (nums[i] < nums[i + 1]) {
            ct1++;
            ct2 = 1;
        } else if (nums[i] > nums[i + 1]) {
            ct1 = 1;
            ct2++;
        } else {
            ct1 = ct2 = 1;
        }
        inc[i] = ct1;
        dec[i] = ct2;
    }

    for (int l = 0; l < n - 3; l++) {
        if (inc[l] > 1) {
            int p = l + inc[l] - 1;
            if (p + 1 < n && dec[p] > 1) {
                int q = p + dec[p] - 1;
                if (q + 1 < n && inc[q] > 1) {
                    int r1 = q + 1;
                    int r2 = q + inc[q] - 1;
                    long long s1 = pref[r1] - pref[l] + nums[l];
                    long long s2 = pref[r2] - pref[l] + nums[l];
                    if (r1 < n && s1 > ans) ans = s1;
                    if (r2 < n && s2 > ans) ans = s2;
                }
            }
        }
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

function maxTrionicSubarray(nums) {
  const n = nums.length;
  let ans = -100000000000000000n;

  let pref = Array(n).fill(0n);
  pref[0] = BigInt(nums[0]);
  for (let i = 1; i < n; i++) pref[i] = pref[i - 1] + BigInt(nums[i]);

  let inc = Array(n).fill(1n);
  let dec = Array(n).fill(1n);

  let ct1 = 1n, ct2 = 1n;
  for (let i = n - 2; i >= 0; i--) {
    if (nums[i] < nums[i + 1]) {
      ct1++;
      ct2 = 1n;
    } else if (nums[i] > nums[i + 1]) {
      ct1 = 1n;
      ct2++;
    } else {
      ct1 = 1n;
      ct2 = 1n;
    }
    inc[i] = ct1;
    dec[i] = ct2;
  }

  for (let l = 0; l < n - 3; l++) {
    if (inc[l] > 1n) {
      let p = l + Number(inc[l]) - 1;
      if (p + 1 < n && dec[p] > 1n) {
        let q = p + Number(dec[p]) - 1;
        if (q + 1 < n && inc[q] > 1n) {
          let r1 = q + 1;
          let r2 = q + Number(inc[q]) - 1;

          if (r1 < n) {
            let v = pref[r1] - pref[l] + BigInt(nums[l]);
            if (v > ans) ans = v;
          }
          if (r2 < n) {
            let v = pref[r2] - pref[l] + BigInt(nums[l]);
            if (v > ans) ans = v;
          }
        }
      }
    }
  }

  return Number(ans);
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## PYTHON

### SOLUTION

def max_trionic_subarray(nums):
    n = len(nums)
    ans = -10**17

    pref = [0] * n
    pref[0] = nums[0]
    for i in range(1, n):
        pref[i] = pref[i - 1] + nums[i]

    inc = [1] * n
    dec = [1] * n

    ct1 = 1
    ct2 = 1
    for i in range(n - 2, -1, -1):
        if nums[i] < nums[i + 1]:
            ct1 += 1
            ct2 = 1
        elif nums[i] > nums[i + 1]:
            ct1 = 1
            ct2 += 1
        else:
            ct1 = 1
            ct2 = 1
        inc[i] = ct1
        dec[i] = ct2

    for l in range(0, n - 3):
        if inc[l] > 1:
            p = l + inc[l] - 1
            if p + 1 < n and dec[p] > 1:
                q = p + dec[p] - 1
                if q + 1 < n and inc[q] > 1:
                    r1 = q + 1
                    r2 = q + inc[q] - 1
                    if r1 < n:
                        ans = max(ans, pref[r1] - pref[l] + nums[l])
                    if r2 < n:
                        ans = max(ans, pref[r2] - pref[l] + nums[l])

    return ans

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
