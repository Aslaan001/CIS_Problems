## CPP

### SOLUTION

vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
    unordered_map<int, int> nextGreater;
    stack<int> st;

    for (int i = nums2.size() - 1; i >= 0; i--) {
        while (!st.empty() && st.top() <= nums2[i]) {
            st.pop();
        }
        nextGreater[nums2[i]] = st.empty() ? -1 : st.top();
        st.push(nums2[i]);
    }

    vector<int> result;
    for (int num : nums1) {
        result.push_back(nextGreater[num]);
    }
    return result;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION

public static int[] nextGreaterElement(int[] nums1, int[] nums2) {
    Map<Integer, Integer> nextGreater = new HashMap<>();
    Stack<Integer> st = new Stack<>();

    for (int i = nums2.length - 1; i >= 0; i--) {
        while (!st.isEmpty() && st.peek() <= nums2[i]) {
            st.pop();
        }
        nextGreater.put(nums2[i], st.isEmpty() ? -1 : st.peek());
        st.push(nums2[i]);
    }

    int[] res = new int[nums1.length];
    for (int i = 0; i < nums1.length; i++) {
        res[i] = nextGreater.get(nums1[i]);
    }
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION

int* nextGreaterElement(int* nums1, int n1, int* nums2, int n2) {
    int* nextGreater = (int*)malloc(sizeof(int) * 10001); 
    for (int i = 0; i < 10001; i++) nextGreater[i] = -1;

    int stack[n2], top = -1;

    for (int i = n2 - 1; i >= 0; i--) {
        while (top >= 0 && stack[top] <= nums2[i]) {
            top--;
        }
        nextGreater[nums2[i]] = (top == -1) ? -1 : stack[top];
        stack[++top] = nums2[i];
    }

    int* result = (int*)malloc(sizeof(int) * n1);
    for (int i = 0; i < n1; i++) {
        result[i] = nextGreater[nums1[i]];
    }
    return result;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function nextGreaterElement(nums1, nums2) {
    let nextGreater = new Map();
    let stack = [];

    for (let i = nums2.length - 1; i >= 0; i--) {
        while (stack.length && stack[stack.length - 1] <= nums2[i]) {
            stack.pop();
        }
        nextGreater.set(nums2[i], stack.length ? stack[stack.length - 1] : -1);
        stack.push(nums2[i]);
    }

    return nums1.map(num => nextGreater.get(num));
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def nextGreaterElement(nums1, nums2):
    next_greater = {}
    stack = []

    for num in reversed(nums2):
        while stack and stack[-1] <= num:
            stack.pop()
        next_greater[num] = stack[-1] if stack else -1
        stack.append(num)

    return [next_greater[num] for num in nums1]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256