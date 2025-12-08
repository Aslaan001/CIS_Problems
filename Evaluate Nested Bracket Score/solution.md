## CPP

### SOLUTION

int scoreBrackets(const string& s) {
    stack<int> st;
    st.push(0);

    for (char c : s) {
        if (c == '(') {
            st.push(0);
        } else {
            int v = st.top(); 
            st.pop();
            int add = (v == 0 ? 1 : 2 * v);
            st.top() += add;
        }
    }

    return st.top();
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int scoreBrackets(String s) {
    Stack<Integer> st = new Stack<>();
    st.push(0);

    for (char c : s.toCharArray()) {
        if (c == '(') {
            st.push(0);
        } else {
            int v = st.pop();
            int add = (v == 0 ? 1 : 2 * v);
            st.push(st.pop() + add);
        }
    }

    return st.pop();
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int scoreBrackets(char* s) {
    int n = strlen(s);
    int st[105];
    int top = 0;
    st[top] = 0;

    for (int i = 0; i < n; i++) {
        if (s[i] == '(') {
            st[++top] = 0;
        } else {
            int v = st[top--];
            int add = (v == 0 ? 1 : 2 * v);
            st[top] += add;
        }
    }

    return st[0];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function scoreBrackets(s) {
    const st = [0];

    for (const c of s) {
        if (c === '(') {
            st.push(0);
        } else {
            const v = st.pop();
            const add = (v === 0 ? 1 : 2 * v);
            st[st.length - 1] += add;
        }
    }

    return st[0];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def score_brackets(s):
    st = [0]

    for ch in s:
        if ch == '(':
            st.append(0)
        else:
            v = st.pop()
            add = 1 if v == 0 else 2 * v
            st[-1] += add

    return st[0]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
