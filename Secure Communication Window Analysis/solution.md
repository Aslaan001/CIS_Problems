## CPP

### SOLUTION

long long countSecureWindows(string s) {
    int n = s.size();
    long long ans = 0;
    int i = 0;
    unordered_map<char, int> freq;

    for (int j = 0; j < n; j++) {
        freq[s[j]]++;

        while (freq.size() == 3) {
            ans += (n - j);
            freq[s[i]]--;
            if (freq[s[i]] == 0) freq.erase(s[i]);
            i++;
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

public static long countSecureWindows(String s) {
    int n = s.length();
    long ans = 0;
    int i = 0;
    HashMap<Character, Integer> freq = new HashMap<>();

    for (int j = 0; j < n; j++) {
        char c = s.charAt(j);
        freq.put(c, freq.getOrDefault(c, 0) + 1);

        while (freq.size() == 3) {
            ans += (n - j);
            char left = s.charAt(i);
            freq.put(left, freq.get(left) - 1);
            if (freq.get(left) == 0) freq.remove(left);
            i++;
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

long long countSecureWindows(char s[]) {
    int freq[256] = {0};
    int distinct = 0;
    int i = 0;
    long long ans = 0;
    int n = strlen(s);

    for (int j = 0; j < n; j++) {
        if (freq[s[j]] == 0) distinct++;
        freq[s[j]]++;

        while (distinct == 3) {
            ans += (n - j);
            freq[s[i]]--;
            if (freq[s[i]] == 0) distinct--;
            i++;
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

function countSecureWindows(s) {
  let freq = new Map();
  let i = 0;
  let ans = 0;
  const n = s.length;

  for (let j = 0; j < n; j++) {
    freq.set(s[j], (freq.get(s[j]) || 0) + 1);

    while (freq.size === 3) {
      ans += (n - j);
      freq.set(s[i], freq.get(s[i]) - 1);
      if (freq.get(s[i]) === 0) freq.delete(s[i]);
      i++;
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

def countSecureWindows(s):
    freq = {}
    i = 0
    ans = 0
    n = len(s)

    for j in range(n):
        freq[s[j]] = freq.get(s[j], 0) + 1

        while len(freq) == 3:
            ans += (n - j)
            freq[s[i]] -= 1
            if freq[s[i]] == 0:
                del freq[s[i]]
            i += 1

    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
