## CPP

### SOLUTION
string binaryRemoval(string& s) {
    string st;
    st.reserve(s.size());
    for(char c : s){
        if(!st.empty() && st.back() == c) st.pop_back();
        else st.push_back(c);
    }
    return st;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION
public static String binaryRemoval(String s) {
    StringBuilder st = new StringBuilder();
    for (int i = 0; i < s.length(); i++) {
        char c = s.charAt(i);
        int m = st.length();
        if (m > 0 && st.charAt(m - 1) == c) st.deleteCharAt(m - 1);
        else st.append(c);
    }
    return st.toString();
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION
char* binaryRemoval(const char* s) {
    size_t n = strlen(s);
    char* st = (char*)malloc(n + 1);
    if(!st) return NULL;
    size_t top = 0; // size of stack
    for (size_t i = 0; i < n; ++i) {
        char c = s[i];
        if (top > 0 && st[top - 1] == c) {
            --top; // pop
        } else {
            st[top++] = c; // push
        }
    }
    st[top] = '\0';
    // Optionally shrink to fit
    return st;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION
function binaryRemoval(s) {
    const st = [];
    for (const c of s) {
        if (st.length && st[st.length - 1] === c) st.pop();
        else st.push(c);
    }
    return st.join('');
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION
def binaryRemoval(s: str) -> str:
    st = []
    for c in s:
        if st and st[-1] == c:
            st.pop()
        else:
            st.append(c)
    return ''.join(st)

### METADATA
**TimeLimit**
1000

**MemoryLimit**
256