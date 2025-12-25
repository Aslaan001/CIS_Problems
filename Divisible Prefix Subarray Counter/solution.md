## CPP

long long countSubarraysWithSumK(vector<int>& nums, int k) {
    unordered_map<int, long long> freq;
    freq[0] = 1;

    long long sum = 0;
    long long ans = 0;

    for (int x : nums) {
        sum += x;
        int mod = ((sum % k) + k) % k;
        ans += freq[mod];
        freq[mod]++;
    }
    return ans;
}


## JAVA

public static long countSubarraysWithSumK(int[] nums, int k) {
    HashMap<Integer, Long> freq = new HashMap<>();
    freq.put(0, 1L);

    long sum = 0;
    long ans = 0;

    for (int x : nums) {
        sum += x;
        int mod = (int)((sum % k + k) % k);
        ans += freq.getOrDefault(mod, 0L);
        freq.put(mod, freq.getOrDefault(mod, 0L) + 1);
    }
    return ans;
}


## C

long long countSubarraysWithSumK(int* nums, int n, int k) {
    long long freq[k];
    for (int i = 0; i < k; i++) freq[i] = 0;

    freq[0] = 1;
    long long sum = 0;
    long long ans = 0;

    for (int i = 0; i < n; i++) {
        sum += nums[i];
        int mod = ((sum % k) + k) % k;
        ans += freq[mod];
        freq[mod]++;
    }
    return ans;
}


## JAVASCRIPT

function countSubarraysWithSumK(nums, k) {
    const freq = new Map();
    freq.set(0, 1);

    let sum = 0;
    let ans = 0;

    for (const x of nums) {
        sum += x;
        const mod = ((sum % k) + k) % k;
        ans += freq.get(mod) || 0;
        freq.set(mod, (freq.get(mod) || 0) + 1);
    }
    return ans;
}


## PYTHON

def count_subarrays_with_sum_k(nums, k):
    freq = {0: 1}
    s = 0
    ans = 0

    for x in nums:
        s += x
        mod = (s % k + k) % k
        ans += freq.get(mod, 0)
        freq[mod] = freq.get(mod, 0) + 1

    return ans
