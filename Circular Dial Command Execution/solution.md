## CPP

### SOLUTION

int minStepsFreedomTrail(string ring, string key) {
    int r = ring.size(), k = key.size();
    vector<int> pos[26];

    for (int i = 0; i < r; i++) {
        pos[ring[i] - 'a'].push_back(i);
    }

    const int INF = 1e9;
    vector<int> prev(r, INF), cur(r, INF);

    for (int p : pos[key[0] - 'a']) {
        prev[p] = min(p, r - p) + 1;
    }

    for (int i = 1; i < k; i++) {
        fill(cur.begin(), cur.end(), INF);
        for (int j : pos[key[i - 1] - 'a']) {
            if (prev[j] == INF) continue;
            for (int p : pos[key[i] - 'a']) {
                int step = abs(p - j);
                step = min(step, r - step);
                cur[p] = min(cur[p], prev[j] + step + 1);
            }
        }
        prev.swap(cur);
    }

    return *min_element(prev.begin(), prev.end());
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int minStepsFreedomTrail(String ring, String key) {
    int r = ring.length(), k = key.length();
    ArrayList<Integer>[] pos = new ArrayList[26];
    for (int i = 0; i < 26; i++) pos[i] = new ArrayList<>();

    for (int i = 0; i < r; i++) {
        pos[ring.charAt(i) - 'a'].add(i);
    }

    int INF = 1_000_000_000;
    int[] prev = new int[r];
    int[] cur = new int[r];
    Arrays.fill(prev, INF);

    for (int p : pos[key.charAt(0) - 'a']) {
        prev[p] = Math.min(p, r - p) + 1;
    }

    for (int i = 1; i < k; i++) {
        Arrays.fill(cur, INF);
        for (int j : pos[key.charAt(i - 1) - 'a']) {
            if (prev[j] == INF) continue;
            for (int p : pos[key.charAt(i) - 'a']) {
                int step = Math.abs(p - j);
                step = Math.min(step, r - step);
                cur[p] = Math.min(cur[p], prev[j] + step + 1);
            }
        }
        int[] tmp = prev;
        prev = cur;
        cur = tmp;
    }

    int ans = INF;
    for (int x : prev) ans = Math.min(ans, x);
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int minStepsFreedomTrail(char ring[], char key[]) {
    int r = strlen(ring);
    int k = strlen(key);

    int pos[26][105], cnt[26] = {0};
    for (int i = 0; i < r; i++) {
        int c = ring[i] - 'a';
        pos[c][cnt[c]++] = i;
    }

    const int INF = 1000000000;
    int prev[105], cur[105];
    for (int i = 0; i < r; i++) prev[i] = INF;

    for (int i = 0; i < cnt[key[0] - 'a']; i++) {
        int p = pos[key[0] - 'a'][i];
        prev[p] = (p < r - p ? p : r - p) + 1;
    }

    for (int i = 1; i < k; i++) {
        for (int j = 0; j < r; j++) cur[j] = INF;
        for (int a = 0; a < cnt[key[i - 1] - 'a']; a++) {
            int j = pos[key[i - 1] - 'a'][a];
            if (prev[j] == INF) continue;
            for (int b = 0; b < cnt[key[i] - 'a']; b++) {
                int p = pos[key[i] - 'a'][b];
                int step = abs(p - j);
                if (step > r - step) step = r - step;
                if (cur[p] > prev[j] + step + 1)
                    cur[p] = prev[j] + step + 1;
            }
        }
        for (int j = 0; j < r; j++) prev[j] = cur[j];
    }

    int ans = INF;
    for (int i = 0; i < r; i++) {
        if (prev[i] < ans) ans = prev[i];
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

function minStepsFreedomTrail(ring, key) {
  const r = ring.length;
  const pos = Array.from({ length: 26 }, () => []);

  for (let i = 0; i < r; i++) {
    pos[ring.charCodeAt(i) - 97].push(i);
  }

  const INF = 1e9;
  let prev = Array(r).fill(INF);
  let cur = Array(r).fill(INF);

  for (const p of pos[key.charCodeAt(0) - 97]) {
    prev[p] = Math.min(p, r - p) + 1;
  }

  for (let i = 1; i < key.length; i++) {
    cur.fill(INF);
    for (const j of pos[key.charCodeAt(i - 1) - 97]) {
      if (prev[j] === INF) continue;
      for (const p of pos[key.charCodeAt(i) - 97]) {
        let step = Math.abs(p - j);
        step = Math.min(step, r - step);
        cur[p] = Math.min(cur[p], prev[j] + step + 1);
      }
    }
    [prev, cur] = [cur, prev];
  }

  return Math.min(...prev);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def minStepsFreedomTrail(ring, key):
    r = len(ring)
    pos = [[] for _ in range(26)]

    for i, ch in enumerate(ring):
        pos[ord(ch) - 97].append(i)

    INF = 10**9
    prev = [INF] * r

    for p in pos[ord(key[0]) - 97]:
        prev[p] = min(p, r - p) + 1

    for i in range(1, len(key)):
        cur = [INF] * r
        for j in pos[ord(key[i - 1]) - 97]:
            if prev[j] == INF:
                continue
            for p in pos[ord(key[i]) - 97]:
                step = abs(p - j)
                step = min(step, r - step)
                cur[p] = min(cur[p], prev[j] + step + 1)
        prev = cur

    return min(prev)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
