## CPP

### SOLUTION

string minimizeNumber(string s, int k) {
    vector<char> st;
    for (char c : s) {
        while (!st.empty() && k > 0 && st.back() > c) {
            st.pop_back();
            k--;
        }
        st.push_back(c);
    }
    while (k > 0 && !st.empty()) {
        st.pop_back();
        k--;
    }
    string res = "";
    for (char c : st) res.push_back(c);

    int idx = 0;
    while (idx < res.size() && res[idx] == '0') idx++;

    res = res.substr(idx);
    if (res == "") return "0";
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static String minimizeNumber(String s, int k) {
    Deque<Character> st = new ArrayDeque<>();

    for (char c : s.toCharArray()) {
        while (!st.isEmpty() && k > 0 && st.peekLast() > c) {
            st.pollLast();
            k--;
        }
        st.addLast(c);
    }

    while (k > 0 && !st.isEmpty()) {
        st.pollLast();
        k--;
    }

    StringBuilder res = new StringBuilder();
    while (!st.isEmpty()) res.append(st.pollFirst());

    int idx = 0;
    while (idx < res.length() && res.charAt(idx) == '0') idx++;

    String out = res.substring(idx);
    return out.length() == 0 ? "0" : out;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

void minimizeNumber(char s[], int k, char out[]) {
    int n = strlen(s);
    char st[n];
    int top = -1;

    for (int i = 0; i < n; i++) {
        while (top >= 0 && k > 0 && st[top] > s[i]) {
            top--;
            k--;
        }
        st[++top] = s[i];
    }

    while (k > 0 && top >= 0) {
        top--;
        k--;
    }

    int len = top + 1;
    int idx = 0;
    while (idx < len && st[idx] == '0') idx++;

    int pos = 0;
    for (int i = idx; i < len; i++) out[pos++] = st[i];

    if (pos == 0) {
        out[0] = '0';
        out[1] = '\0';
    } else {
        out[pos] = '\0';
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function minimizeNumber(s, k) {
  const st = [];

  for (const c of s) {
    while (st.length && k > 0 && st[st.length - 1] > c) {
      st.pop();
      k--;
    }
    st.push(c);
  }

  while (k > 0 && st.length) {
    st.pop();
    k--;
  }

  let res = st.join("").replace(/^0+/, "");
  return res.length ? res : "0";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def minimizeNumber(s, k):
    st = []
    for c in s:
        while st and k > 0 and st[-1] > c:
            st.pop()
            k -= 1
        st.append(c)

    while k > 0 and st:
        st.pop()
        k -= 1

    res = "".join(st).lstrip("0")
    return res if res else "0"

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
