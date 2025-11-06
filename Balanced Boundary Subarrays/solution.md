## CPP

### SOLUTION

long long countBalancedSubarrays(vector<int>& nums) {
    vector<long long> pre;
    long long s = 0;
    map<long long, map<long long, long long>> m1;
    long long ans = 0;
    for (int i = 0; i < nums.size(); i++) {
        s += nums[i];
        pre.push_back(s);
    }
    for (int i = 2; i < nums.size(); i++) {
        long long kk = nums[i];
        long long ll = pre[i - 1];
        long long r = ll - kk;
        m1[pre[i - 2]][nums[i - 2]]++;
        if (m1.find(r) != m1.end() && m1[r].find(nums[i]) != m1[r].end()) {
            ans += m1[r][nums[i]];
        }
    }
    return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION


public static long countBalancedSubarrays(int[] nums) {
    long[] pre = new long[nums.length];
    long s = 0;
    Map<Long, Map<Long, Long>> m1 = new HashMap<>();
    long ans = 0;
    for (int i = 0; i < nums.length; i++) {
        s += nums[i];
        pre[i] = s;
    }
    for (int i = 2; i < nums.length; i++) {
        long kk = nums[i];
        long ll = pre[i - 1];
        long r = ll - kk;
        m1.putIfAbsent(pre[i - 2], new HashMap<>());
        m1.get(pre[i - 2]).put((long) nums[i - 2],
            m1.get(pre[i - 2]).getOrDefault((long) nums[i - 2], 0L) + 1);
        if (m1.containsKey(r) && m1.get(r).containsKey((long) nums[i])) {
            ans += m1.get(r).get((long) nums[i]);
        }
    }
    return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

typedef struct Node {
    long long key1;
    long long key2;
    long long count;
    struct Node* next;
} Node;

Node* add(Node* head, long long k1, long long k2) {
    Node* temp = head;
    while (temp) {
        if (temp->key1 == k1 && temp->key2 == k2) {
            temp->count++;
            return head;
        }
        temp = temp->next;
    }
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->key1 = k1;
    newNode->key2 = k2;
    newNode->count = 1;
    newNode->next = head;
    return newNode;
}

long long findCount(Node* head, long long k1, long long k2) {
    while (head) {
        if (head->key1 == k1 && head->key2 == k2) return head->count;
        head = head->next;
    }
    return 0;
}

long long countBalancedSubarrays(int* nums, int n) {
    long long* pre = (long long*)malloc(n * sizeof(long long));
    long long s = 0, ans = 0;
    Node* head = NULL;
    for (int i = 0; i < n; i++) {
        s += nums[i];
        pre[i] = s;
    }
    for (int i = 2; i < n; i++) {
        long long kk = nums[i];
        long long ll = pre[i - 1];
        long long r = ll - kk;
        head = add(head, pre[i - 2], nums[i - 2]);
        ans += findCount(head, r, nums[i]);
    }
    free(pre);
    return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function countBalancedSubarrays(nums) {
  const pre = [];
  let s = 0n;
  const m1 = new Map();
  let ans = 0n;
  for (let i = 0; i < nums.length; i++) {
    s += BigInt(nums[i]);
    pre.push(s);
  }
  for (let i = 2; i < nums.length; i++) {
    const kk = BigInt(nums[i]);
    const ll = pre[i - 1];
    const r = ll - kk;
    if (!m1.has(pre[i - 2])) m1.set(pre[i - 2], new Map());
    const inner = m1.get(pre[i - 2]);
    inner.set(BigInt(nums[i - 2]), (inner.get(BigInt(nums[i - 2])) || 0n) + 1n);
    if (m1.has(r) && m1.get(r).has(BigInt(nums[i]))) {
      ans += m1.get(r).get(BigInt(nums[i]));
    }
  }
  return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def count_balanced_subarrays(nums):
    pre = []
    s = 0
    m1 = defaultdict(lambda: defaultdict(int))
    ans = 0
    for x in nums:
        s += x
        pre.append(s)
    for i in range(2, len(nums)):
        kk = nums[i]
        ll = pre[i - 1]
        r = ll - kk
        m1[pre[i - 2]][nums[i - 2]] += 1
        if r in m1 and nums[i] in m1[r]:
            ans += m1[r][nums[i]]
    return ans

### METADATA

TimeLimit
1000

MemoryLimit
512
