## CPP

### SOLUTION

int longestValidParentheses(const string& s) {
    stack<int> st;
    st.push(-1);
    int best = 0;

    for (int i = 0; i < s.size(); i++) {
        if (s[i] == '(') {
            st.push(i);
        } else {
            st.pop();
            if (st.empty()) {
                st.push(i);
            } else {
                best = max(best, i - st.top());
            }
        }
    }
    return best;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int longestValidParentheses(String s) {
    Stack<Integer> st = new Stack<>();
    st.push(-1);
    int best = 0;

    for (int i = 0; i < s.length(); i++) {
        if (s.charAt(i) == '(') {
            st.push(i);
        } else {
            st.pop();
            if (st.isEmpty()) {
                st.push(i);
            } else {
                best = Math.max(best, i - st.peek());
            }
        }
    }

    return best;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int longestValidParentheses(char* s) {
    int n = strlen(s);
    int st[n + 5];
    int top = 0;
    st[top] = -1;

    int best = 0;

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
                if (len > best) best = len;
            }
        }
    }

    return best;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function longestValidParentheses(s) {
    const st = [-1];
    let best = 0;

    for (let i = 0; i < s.length; i++) {
        if (s[i] === '(') {
            st.push(i);
        } else {
            st.pop();
            if (st.length === 0) {
                st.push(i);
            } else {
                best = Math.max(best, i - st[st.length - 1]);
            }
        }
    }

    return best;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def longest_valid_parentheses(s):
    st = [-1]
    best = 0

    for i, ch in enumerate(s):
        if ch == '(':
            st.append(i)
        else:
            st.pop()
            if not st:
                st.append(i)
            else:
                best = max(best, i - st[-1])
    
    return best

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
