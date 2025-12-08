## CPP

### SOLUTION

int canEqualize(const string& word) {
    vector<int> freq(26, 0);
    for (char c : word) freq[c - 'a']++;

    // Try removing one letter at every position
    for (char c = 'a'; c <= 'z'; c++) {
        if (freq[c - 'a'] == 0) continue;

        freq[c - 'a']--;

        int good = -1;
        bool ok = true;
        for (int f : freq) {
            if (f == 0) continue;
            if (good == -1) good = f;
            else if (good != f) ok = false;
        }

        freq[c - 'a']++;
        if (ok) return 1;
    }

    return 0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int canEqualize(String word) {
    int[] freq = new int[26];
    for (char c : word.toCharArray()) freq[c - 'a']++;

    for (int i = 0; i < 26; i++) {
        if (freq[i] == 0) continue;

        freq[i]--;

        int good = -1;
        boolean ok = true;
        for (int f : freq) {
            if (f == 0) continue;
            if (good == -1) good = f;
            else if (good != f) ok = false;
        }

        freq[i]++;
        if (ok) return 1;
    }

    return 0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int canEqualize(char* word) {
    int freq[26] = {0};
    int n = strlen(word);

    for (int i = 0; i < n; i++) {
        freq[word[i] - 'a']++;
    }

    for (int i = 0; i < 26; i++) {
        if (freq[i] == 0) continue;

        freq[i]--;

        int good = -1;
        int ok = 1;

        for (int j = 0; j < 26; j++) {
            if (freq[j] == 0) continue;
            if (good == -1) good = freq[j];
            else if (good != freq[j]) ok = 0;
        }

        freq[i]++;
        if (ok) return 1;
    }

    return 0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function canEqualize(word) {
    let freq = Array(26).fill(0);
    for (const ch of word) freq[ch.charCodeAt(0) - 97]++;

    for (let i = 0; i < 26; i++) {
        if (freq[i] === 0) continue;

        freq[i]--;

        let good = -1;
        let ok = true;

        for (const f of freq) {
            if (f === 0) continue;
            if (good === -1) good = f;
            else if (good !== f) ok = false;
        }

        freq[i]++;
        if (ok) return 1;
    }

    return 0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def can_equalize(word):
    freq = [0] * 26
    for ch in word:
        freq[ord(ch) - 97] += 1

    for i in range(26):
        if freq[i] == 0:
            continue

        freq[i] -= 1

        good = -1
        ok = True
        for f in freq:
            if f == 0:
                continue
            if good == -1:
                good = f
            elif good != f:
                ok = False

        freq[i] += 1
        if ok:
            return 1

    return 0

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
