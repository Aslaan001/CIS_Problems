## CPP

### SOLUTION

string removeSubstring(string s, string p) {
    string res = "";
    int m = p.size();
    for (char c : s) {
        res.push_back(c);
        if (res.size() >= m && res.substr(res.size() - m, m) == p) {
            res.erase(res.size() - m, m);
        }
    }
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512


## JAVA

### SOLUTION

public static String removeSubstring(String s, String p) {
    StringBuilder res = new StringBuilder();
    int m = p.length();
    for (char c : s.toCharArray()) {
        res.append(c);
        if (res.length() >= m &&
            res.substring(res.length() - m).equals(p)) {
            res.delete(res.length() - m, res.length());
        }
    }
    return res.toString();
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

void removeSubstring(char s[], char p[], char out[]) {
    int n = strlen(s), m = strlen(p);
    char temp[2005];
    int top = 0;

    for (int i = 0; i < n; i++) {
        temp[top++] = s[i];

        if (top >= m) {
            int match = 1;
            for (int j = 0; j < m; j++) {
                if (temp[top - m + j] != p[j]) {
                    match = 0;
                    break;
                }
            }
            if (match) top -= m;
        }
    }

    temp[top] = '\0';
    strcpy(out, temp);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function removeSubstring(s, p) {
  let res = [];
  const m = p.length;

  for (let c of s) {
    res.push(c);
    if (res.length >= m) {
      let ok = true;
      for (let i = 0; i < m; i++) {
        if (res[res.length - m + i] !== p[i]) {
          ok = false;
          break;
        }
      }
      if (ok) res.length -= m;
    }
  }

  return res.join("");
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def removeSubstring(s, p):
    res = []
    m = len(p)
    for c in s:
        res.append(c)
        if len(res) >= m and "".join(res[-m:]) == p:
            del res[-m:]
    return "".join(res)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
