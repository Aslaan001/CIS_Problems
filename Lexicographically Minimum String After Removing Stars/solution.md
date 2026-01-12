## CPP

### SOLUTION

string clearStars(string s) {
    priority_queue<char, vector<char>, greater<char>> pq;
    vector<vector<int>> indices(26);
    int n = s.size();

    for (int i = 0; i < n; i++) {
        if (s[i] == '*') {
            char ch = pq.top();
            pq.pop();

            int idx = indices[ch - 'a'].back();
            indices[ch - 'a'].pop_back();

            s[idx] = '!';
            s[i] = '!';

            if (!indices[ch - 'a'].empty()) {
                pq.push(ch);
            }
        } else {
            if (indices[s[i] - 'a'].empty()) {
                pq.push(s[i]);
            }
            indices[s[i] - 'a'].push_back(i);
        }
    }

    string res;
    for (char c : s) {
        if (c >= 'a' && c <= 'z') {
            res.push_back(c);
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

public static String clearStars(String s) {
    PriorityQueue<Character> pq = new PriorityQueue<>();
    List<List<Integer>> indices = new ArrayList<>();
    int n = s.length();

    for (int i = 0; i < 26; i++) indices.add(new ArrayList<>());

    char[] arr = s.toCharArray();

    for (int i = 0; i < n; i++) {
        if (arr[i] == '*') {
            char ch = pq.poll();
            List<Integer> list = indices.get(ch - 'a');
            int idx = list.remove(list.size() - 1);

            arr[idx] = '!';
            arr[i] = '!';

            if (!list.isEmpty()) {
                pq.add(ch);
            }
        } else {
            List<Integer> list = indices.get(arr[i] - 'a');
            if (list.isEmpty()) {
                pq.add(arr[i]);
            }
            list.add(i);
        }
    }

    StringBuilder res = new StringBuilder();
    for (char c : arr) {
        if (c >= 'a' && c <= 'z') {
            res.append(c);
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

char* clearStars(char* s) {
    int n = strlen(s);
    int removed[n];
    memset(removed, 0, sizeof(removed));

    int freq[26][100005];
    int cnt[26] = {0};

    for (int i = 0; i < n; i++) {
        if (s[i] == '*') {
            for (int c = 0; c < 26; c++) {
                if (cnt[c] > 0) {
                    int idx = freq[c][--cnt[c]];
                    removed[idx] = 1;
                    removed[i] = 1;
                    break;
                }
            }
        } else {
            freq[s[i] - 'a'][cnt[s[i] - 'a']++] = i;
        }
    }

    char* res = (char*)malloc(n + 1);
    int k = 0;
    for (int i = 0; i < n; i++) {
        if (!removed[i]) {
            res[k++] = s[i];
        }
    }
    res[k] = '\0';
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function clearStars(s) {
  const n = s.length;
  const removed = new Array(n).fill(false);
  const indices = Array.from({ length: 26 }, () => []);
  const pq = [];

  const pushPQ = (c) => {
    if (!pq.includes(c)) {
      pq.push(c);
      pq.sort();
    }
  };

  const popPQ = () => pq.shift();

  for (let i = 0; i < n; i++) {
    if (s[i] === '*') {
      const ch = popPQ();
      const idx = indices[ch.charCodeAt(0) - 97].pop();
      removed[idx] = true;
      removed[i] = true;

      if (indices[ch.charCodeAt(0) - 97].length > 0) {
        pushPQ(ch);
      }
    } else {
      const c = s[i];
      const list = indices[c.charCodeAt(0) - 97];
      if (list.length === 0) pushPQ(c);
      list.push(i);
    }
  }

  let res = "";
  for (let i = 0; i < n; i++) {
    if (!removed[i]) res += s[i];
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

def clearStars(s):
    import heapq

    n = len(s)
    removed = [False] * n
    indices = [[] for _ in range(26)]
    pq = []

    for i, c in enumerate(s):
        if c == '*':
            ch = heapq.heappop(pq)
            idx = indices[ord(ch) - 97].pop()
            removed[idx] = True
            removed[i] = True
            if indices[ord(ch) - 97]:
                heapq.heappush(pq, ch)
        else:
            if not indices[ord(c) - 97]:
                heapq.heappush(pq, c)
            indices[ord(c) - 97].append(i)

    res = []
    for i in range(n):
        if not removed[i]:
            res.append(s[i])
    return "".join(res)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
