## CPP

### SOLUTION

int solve(const vector<int>& nums) {
    if (nums.empty()) return 0;
    int maxv = *max_element(nums.begin(), nums.end());
    vector<int> sum(maxv+1,0);
    for(int x: nums) sum[x] += x;

    vector<int> dp(maxv+1,0);
    dp[0] = 0;
    dp[1] = sum[1];
    for(int i=2;i<=maxv;i++){
        dp[i] = max(dp[i-1], dp[i-2] + sum[i]);
    }
    return dp[maxv];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION

    static int solve(int[] nums){
        int maxv=0;
        for(int x: nums) maxv=Math.max(maxv,x);

        int[] sum=new int[maxv+1];
        for(int x: nums) sum[x]+=x;

        int[] dp=new int[maxv+1];
        dp[0]=0;
        if(maxv>=1) dp[1]=sum[1];

        for(int i=2;i<=maxv;i++){
            dp[i]=Math.max(dp[i-1], dp[i-2]+sum[i]);
        }
        return dp[maxv];
    }

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION

int solve(int* nums, int n){
    int maxv=0;
    for(int i=0;i<n;i++) if(nums[i]>maxv) maxv=nums[i];

    int* sum=calloc(maxv+1,sizeof(int));
    for(int i=0;i<n;i++) sum[nums[i]]+=nums[i];

    int* dp=calloc(maxv+1,sizeof(int));
    dp[0]=0;
    if(maxv>=1) dp[1]=sum[1];

    for(int i=2;i<=maxv;i++){
        dp[i]= dp[i-1] > (dp[i-2]+sum[i]) ? dp[i-1] : dp[i-2]+sum[i];
    }

    int ans=dp[maxv];
    free(sum);
    free(dp);
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION

function solve(nums){
    let maxv=Math.max(...nums);
    let sum=new Array(maxv+1).fill(0);
    for(let x of nums) sum[x]+=x;

    let dp=new Array(maxv+1).fill(0);
    if(maxv>=1) dp[1]=sum[1];

    for(let i=2;i<=maxv;i++){
        dp[i]=Math.max(dp[i-1], dp[i-2]+sum[i]);
    }
    return dp[maxv];
}

### METADATA

**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION

def solve(nums):
    if not nums: return 0
    maxv=max(nums)
    sumv=[0]*(maxv+1)
    for x in nums:
        sumv[x]+=x
    dp=[0]*(maxv+1)
    if maxv>=1:
        dp[1]=sumv[1]
    for i in range(2,maxv+1):
        dp[i]=max(dp[i-1], dp[i-2]+sumv[i])
    return dp[maxv]


### METADATA

**TimeLimit**
1000

**MemoryLimit**
128
