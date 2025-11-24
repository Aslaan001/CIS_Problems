## CPP

### SOLUTION

int longestBalanced(string s) {
    stack<int> st;
    st.push(-1);
    int ans = 0;

    for (int i = 0; i < s.size(); i++) {
        if (s[i] == '(') {
            st.push(i);
        } else {
            st.pop();
            if (st.empty()) {
                st.push(i);
            } else {
                ans = max(ans, i - st.top());
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

public static int longestBalanced(String s) {
    Stack<Integer> st = new Stack<>();
    st.push(-1);
    int ans = 0;

    for (int i = 0; i < s.length(); i++) {
        if (s.charAt(i) == '(') {
            st.push(i);
        } else {
            st.pop();
            if (st.isEmpty()) {
                st.push(i);
            } else {
                ans = Math.max(ans, i - st.peek());
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

int longestBalanced(char s[]) {
    int n = strlen(s);
    int st[n + 5];
    int top = -1;
    st[++top] = -1;

    int ans = 0;

    for (int i = 0; i < n; i++) {
        if (s[i] == '(') {
            st[++top] = i;
        } else {
            top--;
            if (top < 0) {
                top = 0;
                st[top] = i;
            } else {
                int len = i - st[top];
                if (len > ans) ans = len;
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

function longestBalanced(s) {
  const st = [-1];
  let ans = 0;

  for (let i = 0; i < s.length; i++) {
    if (s[i] === "(") {
      st.push(i);
    } else {
      st.pop();
      if (st.length === 0) {
        st.push(i);
      } else {
        ans = Math.max(ans, i - st[st.length - 1]);
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


## PYTHON

### SOLUTION

def longestBalanced(s):
    st = [-1]
    ans = 0

    for i, ch in enumerate(s):
        if ch == '(':
            st.append(i)
        else:
            st.pop()
            if not st:
                st.append(i)
            else:
                ans = max(ans, i - st[-1])
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
