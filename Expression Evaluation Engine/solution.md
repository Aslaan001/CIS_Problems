## CPP

### SOLUTION

int calculate(string s) {
    long long res = 0;
    long long num = 0;
    int sign = 1;
    stack<long long> st;

    for (int i = 0; i < s.size(); i++) {
        char c = s[i];

        if (isdigit(c)) {
            num = num * 10 + (c - '0');
        } 
        else if (c == '+') {
            res += sign * num;
            num = 0;
            sign = 1;
        } 
        else if (c == '-') {
            res += sign * num;
            num = 0;
            sign = -1;
        } 
        else if (c == '(') {
            st.push(res);
            st.push(sign);
            res = 0;
            sign = 1;
        } 
        else if (c == ')') {
            res += sign * num;
            num = 0;
            res *= st.top(); st.pop();
            res += st.top(); st.pop();
        }
    }

    res += sign * num;
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int calculate(String s) {
    long res = 0;
    long num = 0;
    int sign = 1;
    Stack<Integer> st = new Stack<>();

    for (int i = 0; i < s.length(); i++) {
        char c = s.charAt(i);

        if (Character.isDigit(c)) {
            num = num * 10 + (c - '0');
        } 
        else if (c == '+') {
            res += sign * num;
            num = 0;
            sign = 1;
        } 
        else if (c == '-') {
            res += sign * num;
            num = 0;
            sign = -1;
        } 
        else if (c == '(') {
            st.push((int)res);
            st.push(sign);
            res = 0;
            sign = 1;
        } 
        else if (c == ')') {
            res += sign * num;
            num = 0;
            res *= st.pop();
            res += st.pop();
        }
    }

    res += sign * num;
    return (int)res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int calculate(char* s) {
    int stack[300000];
    int top = -1;
    long res = 0, num = 0;
    int sign = 1;

    for (int i = 0; s[i]; i++) {
        char c = s[i];

        if (isdigit(c)) {
            num = num * 10 + (c - '0');
        } 
        else if (c == '+') {
            res += sign * num;
            num = 0;
            sign = 1;
        } 
        else if (c == '-') {
            res += sign * num;
            num = 0;
            sign = -1;
        } 
        else if (c == '(') {
            stack[++top] = res;
            stack[++top] = sign;
            res = 0;
            sign = 1;
        } 
        else if (c == ')') {
            res += sign * num;
            num = 0;
            res *= stack[top--];
            res += stack[top--];
        }
    }

    res += sign * num;
    return (int)res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function calculate(s) {
  let res = 0;
  let num = 0;
  let sign = 1;
  const st = [];

  for (const c of s) {
    if (c >= '0' && c <= '9') {
      num = num * 10 + Number(c);
    } 
    else if (c === '+') {
      res += sign * num;
      num = 0;
      sign = 1;
    } 
    else if (c === '-') {
      res += sign * num;
      num = 0;
      sign = -1;
    } 
    else if (c === '(') {
      st.push(res);
      st.push(sign);
      res = 0;
      sign = 1;
    } 
    else if (c === ')') {
      res += sign * num;
      num = 0;
      res *= st.pop();
      res += st.pop();
    }
  }

  return res + sign * num;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def calculate(s):
    res = 0
    num = 0
    sign = 1
    st = []

    for c in s:
        if c.isdigit():
            num = num * 10 + int(c)
        elif c == '+':
            res += sign * num
            num = 0
            sign = 1
        elif c == '-':
            res += sign * num
            num = 0
            sign = -1
        elif c == '(':
            st.append(res)
            st.append(sign)
            res = 0
            sign = 1
        elif c == ')':
            res += sign * num
            num = 0
            res *= st.pop()
            res += st.pop()

    return res + sign * num

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
