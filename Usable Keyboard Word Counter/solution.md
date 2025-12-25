## CPP

### SOLUTION

int countTypeableWords(string text, string brokenLetters) {
    vector<int> broken(26, 0);
    for (char c : brokenLetters) broken[c - 'a'] = 1;

    int ans = 0;
    string word;

    for (int i = 0; i <= text.size(); i++) {
        if (i == text.size() || text[i] == ' ') {
            bool ok = true;
            for (char c : word) {
                if (broken[c - 'a']) { ok = false; break; }
            }
            if (ok) ans++;
            word.clear();
        } else {
            word.push_back(text[i]);
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

public static int countTypeableWords(String text, String brokenLetters) {
    boolean[] broken = new boolean[26];
    for (char c : brokenLetters.toCharArray()) broken[c - 'a'] = true;

    int ans = 0;
    String[] words = text.split(" ");

    for (String word : words) {
        boolean ok = true;
        for (char c : word.toCharArray()) {
            if (broken[c - 'a']) { ok = false; break; }
        }
        if (ok) ans++;
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

int countTypeableWords(char text[], char brokenLetters[]) {
    int broken[26] = {0};
    for (int i = 0; brokenLetters[i]; i++)
        broken[brokenLetters[i] - 'a'] = 1;

    int ans = 0, ok = 1;

    for (int i = 0; ; i++) {
        if (text[i] == ' ' || text[i] == '\0') {
            if (ok) ans++;
            ok = 1;
            if (text[i] == '\0') break;
        } else {
            if (broken[text[i] - 'a']) ok = 0;
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

function countTypeableWords(text, brokenLetters) {
  const broken = new Set(brokenLetters);
  let ans = 0;

  for (const word of text.split(" ")) {
    let ok = true;
    for (const c of word) {
      if (broken.has(c)) { ok = false; break; }
    }
    if (ok) ans++;
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

def count_typeable_words(text, brokenLetters):
    broken = set(brokenLetters)
    ans = 0
    for word in text.split():
        ok = True
        for c in word:
            if c in broken:
                ok = False
                break
        if ok:
            ans += 1
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
