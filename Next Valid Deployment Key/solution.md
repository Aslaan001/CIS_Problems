## CPP

### SOLUTION

string nextValidDeploymentKey(string s, string target) {
    int n = target.size();
    multiset<char> availableChars(s.begin(), s.end());

    int latestDiff = -1;
    for (int i = 0; i < n; i++) {
        if (*availableChars.rbegin() < target[i]) break;
        if (*availableChars.rbegin() > target[i]) latestDiff = i;
        if (availableChars.count(target[i])) {
            availableChars.erase(availableChars.find(target[i]));
        } else {
            break;
        }
    }

    if (latestDiff == -1) return "";

    multiset<char> solChars(s.begin(), s.end());
    string res(n, ' ');

    for (int i = 0; i < latestDiff; i++) {
        res[i] = target[i];
        solChars.erase(solChars.find(target[i]));
    }

    auto it = solChars.upper_bound(target[latestDiff]);
    res[latestDiff] = *it;
    solChars.erase(it);

    for (int i = latestDiff + 1; i < n; i++) {
        res[i] = *solChars.begin();
        solChars.erase(solChars.begin());
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

public static String nextValidDeploymentKey(String s, String target) {
    int n = target.length();
    TreeMap<Character, Integer> map = new TreeMap<>();

    for (char c : s.toCharArray())
        map.put(c, map.getOrDefault(c, 0) + 1);

    int latestDiff = -1;
    TreeMap<Character, Integer> temp = new TreeMap<>(map);

    for (int i = 0; i < n; i++) {
        if (temp.lastKey() < target.charAt(i)) break;
        if (temp.lastKey() > target.charAt(i)) latestDiff = i;

        char c = target.charAt(i);
        if (!temp.containsKey(c)) break;
        temp.put(c, temp.get(c) - 1);
        if (temp.get(c) == 0) temp.remove(c);
    }

    if (latestDiff == -1) return "";

    StringBuilder res = new StringBuilder();
    temp = new TreeMap<>(map);

    for (int i = 0; i < latestDiff; i++) {
        char c = target.charAt(i);
        res.append(c);
        temp.put(c, temp.get(c) - 1);
        if (temp.get(c) == 0) temp.remove(c);
    }

    char next = temp.higherKey(target.charAt(latestDiff));
    res.append(next);
    temp.put(next, temp.get(next) - 1);
    if (temp.get(next) == 0) temp.remove(next);

    for (char c : temp.keySet()) {
        for (int k = 0; k < temp.get(c); k++)
            res.append(c);
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

char* nextValidDeploymentKey(char* s, char* target) {
    static char res[305];
    int cnt[26] = {0};
    int n = strlen(target);

    for (int i = 0; s[i]; i++) cnt[s[i] - 'a']++;

    int latestDiff = -1;
    int temp[26];
    memcpy(temp, cnt, sizeof(cnt));

    for (int i = 0; i < n; i++) {
        int maxChar = -1;
        for (int c = 25; c >= 0; c--) {
            if (temp[c] > 0) {
                maxChar = c;
                break;
            }
        }
        if (maxChar < target[i] - 'a') break;
        if (maxChar > target[i] - 'a') latestDiff = i;

        int idx = target[i] - 'a';
        if (temp[idx] == 0) break;
        temp[idx]--;
    }

    if (latestDiff == -1) return "";

    memcpy(temp, cnt, sizeof(cnt));
    int pos = 0;

    for (int i = 0; i < latestDiff; i++) {
        res[pos++] = target[i];
        temp[target[i] - 'a']--;
    }

    for (int c = target[latestDiff] - 'a' + 1; c < 26; c++) {
        if (temp[c] > 0) {
            res[pos++] = (char)(c + 'a');
            temp[c]--;
            break;
        }
    }

    for (int c = 0; c < 26; c++) {
        while (temp[c]--) res[pos++] = (char)(c + 'a');
    }

    res[pos] = '\0';
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function nextValidDeploymentKey(s, target) {
  const cnt = Array(26).fill(0);
  for (const c of s) cnt[c.charCodeAt(0) - 97]++;

  const n = target.length;
  let latestDiff = -1;
  const temp = cnt.slice();

  for (let i = 0; i < n; i++) {
    let maxChar = -1;
    for (let c = 25; c >= 0; c--) if (temp[c] > 0) { maxChar = c; break; }
    if (maxChar < target.charCodeAt(i) - 97) break;
    if (maxChar > target.charCodeAt(i) - 97) latestDiff = i;
    const idx = target.charCodeAt(i) - 97;
    if (temp[idx] === 0) break;
    temp[idx]--;
  }

  if (latestDiff === -1) return "";

  let res = "";
  const cur = cnt.slice();

  for (let i = 0; i < latestDiff; i++) {
    res += target[i];
    cur[target.charCodeAt(i) - 97]--;
  }

  for (let c = target.charCodeAt(latestDiff) - 97 + 1; c < 26; c++) {
    if (cur[c] > 0) {
      res += String.fromCharCode(c + 97);
      cur[c]--;
      break;
    }
  }

  for (let c = 0; c < 26; c++) {
    while (cur[c]--) res += String.fromCharCode(c + 97);
  }

  return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def nextValidDeploymentKey(s, target):
    from collections import Counter

    cnt = Counter(s)
    n = len(target)
    latestDiff = -1
    temp = cnt.copy()

    for i in range(n):
        if max(temp) < target[i]:
            break
        if max(temp) > target[i]:
            latestDiff = i
        if temp[target[i]] == 0:
            break
        temp[target[i]] -= 1
        if temp[target[i]] == 0:
            del temp[target[i]]

    if latestDiff == -1:
        return ""

    temp = Counter(s)
    res = []

    for i in range(latestDiff):
        res.append(target[i])
        temp[target[i]] -= 1
        if temp[target[i]] == 0:
            del temp[target[i]]

    for c in sorted(temp):
        if c > target[latestDiff]:
            res.append(c)
            temp[c] -= 1
            if temp[c] == 0:
                del temp[c]
            break

    for c in sorted(temp):
        res.extend([c] * temp[c])

    return "".join(res)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
