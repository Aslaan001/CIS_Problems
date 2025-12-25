## CPP

### SOLUTION

string decodeString(string s) {
    stack<int> cnt;
    stack<string> st;
    string cur = "";
    int num = 0;

    for (char c : s) {
        if (isdigit(c)) {
            num = num * 10 + (c - '0');
        } else if (c == '[') {
            cnt.push(num);
            st.push(cur);
            num = 0;
            cur = "";
        } else if (c == ']') {
            int k = cnt.top(); cnt.pop();
            string prev = st.top(); st.pop();
            string temp = "";
            while (k--) temp += cur;
            cur = prev + temp;
        } else {
            cur.push_back(c);
        }
    }
    return cur;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static String decodeString(String s) {
    Stack<Integer> cnt = new Stack<>();
    Stack<String> st = new Stack<>();
    String cur = "";
    int num = 0;

    for (char c : s.toCharArray()) {
        if (Character.isDigit(c)) {
            num = num * 10 + (c - '0');
        } else if (c == '[') {
            cnt.push(num);
            st.push(cur);
            num = 0;
            cur = "";
        } else if (c == ']') {
            int k = cnt.pop();
            String prev = st.pop();
            StringBuilder sb = new StringBuilder(prev);
            while (k-- > 0) sb.append(cur);
            cur = sb.toString();
        } else {
            cur += c;
        }
    }
    return cur;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

char* decodeString(char* s) {
    int len = strlen(s);
    char* stackStr[1000];
    int stackCnt[1000];
    int top = -1;

    char* cur = (char*)calloc(100001, sizeof(char));
    int curLen = 0;
    int num = 0;

    for (int i = 0; i < len; i++) {
        if (isdigit(s[i])) {
            num = num * 10 + (s[i] - '0');
        } else if (s[i] == '[') {
            stackCnt[++top] = num;
            stackStr[top] = strdup(cur);
            curLen = 0;
            cur[0] = '\0';
            num = 0;
        } else if (s[i] == ']') {
            int k = stackCnt[top];
            char* prev = stackStr[top--];
            char temp[100001] = {0};
            for (int j = 0; j < k; j++) strcat(temp, cur);
            strcpy(cur, prev);
            strcat(cur, temp);
            free(prev);
        } else {
            cur[curLen++] = s[i];
            cur[curLen] = '\0';
        }
    }
    return cur;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function decodeString(s) {
  const cnt = [];
  const st = [];
  let cur = "";
  let num = 0;

  for (const c of s) {
    if (c >= '0' && c <= '9') {
      num = num * 10 + Number(c);
    } else if (c === '[') {
      cnt.push(num);
      st.push(cur);
      num = 0;
      cur = "";
    } else if (c === ']') {
      const k = cnt.pop();
      const prev = st.pop();
      cur = prev + cur.repeat(k);
    } else {
      cur += c;
    }
  }
  return cur;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def decode_string(s):
    cnt = []
    st = []
    cur = ""
    num = 0

    for c in s:
        if c.isdigit():
            num = num * 10 + int(c)
        elif c == '[':
            cnt.append(num)
            st.append(cur)
            num = 0
            cur = ""
        elif c == ']':
            k = cnt.pop()
            prev = st.pop()
            cur = prev + cur * k
        else:
            cur += c

    return cur

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
