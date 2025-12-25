## CPP

### SOLUTION

string addBinary(string a, string b) {
    int i = a.size() - 1, j = b.size() - 1;
    int carry = 0;
    string res;

    while (i >= 0 || j >= 0 || carry) {
        int sum = carry;
        if (i >= 0) sum += a[i--] - '0';
        if (j >= 0) sum += b[j--] - '0';
        res.push_back(char('0' + (sum & 1)));
        carry = sum >> 1;
    }

    reverse(res.begin(), res.end());
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static String addBinary(String a, String b) {
    int i = a.length() - 1, j = b.length() - 1;
    int carry = 0;
    StringBuilder sb = new StringBuilder();

    while (i >= 0 || j >= 0 || carry != 0) {
        int sum = carry;
        if (i >= 0) sum += a.charAt(i--) - '0';
        if (j >= 0) sum += b.charAt(j--) - '0';
        sb.append(sum & 1);
        carry = sum >> 1;
    }

    return sb.reverse().toString();
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

char* addBinary(char a[], char b[]) {
    int n = strlen(a), m = strlen(b);
    int i = n - 1, j = m - 1, carry = 0;

    int maxLen = (n > m ? n : m) + 2;
    char* res = (char*)malloc(maxLen);
    int idx = 0;

    while (i >= 0 || j >= 0 || carry) {
        int sum = carry;
        if (i >= 0) sum += a[i--] - '0';
        if (j >= 0) sum += b[j--] - '0';
        res[idx++] = (sum & 1) + '0';
        carry = sum >> 1;
    }

    res[idx] = '\0';

    for (int l = 0, r = idx - 1; l < r; l++, r--) {
        char tmp = res[l];
        res[l] = res[r];
        res[r] = tmp;
    }

    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function addBinary(a, b) {
  let i = a.length - 1, j = b.length - 1;
  let carry = 0;
  let res = [];

  while (i >= 0 || j >= 0 || carry) {
    let sum = carry;
    if (i >= 0) sum += a[i--] === '1' ? 1 : 0;
    if (j >= 0) sum += b[j--] === '1' ? 1 : 0;
    res.push(sum & 1);
    carry = sum >> 1;
  }

  return res.reverse().join("");
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def add_binary(a, b):
    i, j = len(a) - 1, len(b) - 1
    carry = 0
    res = []

    while i >= 0 or j >= 0 or carry:
        s = carry
        if i >= 0:
            s += ord(a[i]) - ord('0')
            i -= 1
        if j >= 0:
            s += ord(b[j]) - ord('0')
            j -= 1
        res.append(str(s & 1))
        carry = s >> 1

    return "".join(reversed(res))

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
