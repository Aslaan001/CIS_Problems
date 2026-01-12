## CPP

### SOLUTION

string predictPartyVictory(string senate) {
    queue<int> a, b;
    int n = senate.size();

    for (int i = 0; i < n; i++) {
        if (senate[i] == 'A') a.push(i);
        else b.push(i);
    }

    while (!a.empty() && !b.empty()) {
        int ai = a.front(); a.pop();
        int bi = b.front(); b.pop();

        if (ai < bi) {
            a.push(ai + n);
        } else {
            b.push(bi + n);
        }
    }

    return a.empty() ? "Beta" : "Alpha";
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVA

### SOLUTION

public static String predictPartyVictory(String senate) {
    Queue<Integer> a = new LinkedList<>();
    Queue<Integer> b = new LinkedList<>();
    int n = senate.length();

    for (int i = 0; i < n; i++) {
        if (senate.charAt(i) == 'A') a.offer(i);
        else b.offer(i);
    }

    while (!a.isEmpty() && !b.isEmpty()) {
        int ai = a.poll();
        int bi = b.poll();

        if (ai < bi) {
            a.offer(ai + n);
        } else {
            b.offer(bi + n);
        }
    }

    return a.isEmpty() ? "Beta" : "Alpha";
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## C

### SOLUTION

char* predictPartyVictory(char* senate) {
    static char alpha[] = "Alpha";
    static char beta[] = "Beta";

    int n = strlen(senate);
    int a[20005], b[20005];
    int af = 0, ab = 0, bf = 0, bb = 0;

    for (int i = 0; i < n; i++) {
        if (senate[i] == 'A') a[ab++] = i;
        else b[bb++] = i;
    }

    while (af < ab && bf < bb) {
        int ai = a[af++];
        int bi = b[bf++];

        if (ai < bi) {
            a[ab++] = ai + n;
        } else {
            b[bb++] = bi + n;
        }
    }

    return (af < ab) ? alpha : beta;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVASCRIPT

### SOLUTION

function predictPartyVictory(senate) {
    const a = [], b = [];
    const n = senate.length;

    for (let i = 0; i < n; i++) {
        if (senate[i] === 'A') a.push(i);
        else b.push(i);
    }

    while (a.length && b.length) {
        const ai = a.shift();
        const bi = b.shift();

        if (ai < bi) {
            a.push(ai + n);
        } else {
            b.push(bi + n);
        }
    }

    return a.length ? "Alpha" : "Beta";
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## PYTHON

### SOLUTION

def predict_party_victory(senate):
    from collections import deque

    a = deque()
    b = deque()
    n = len(senate)

    for i, ch in enumerate(senate):
        if ch == 'A':
            a.append(i)
        else:
            b.append(i)

    while a and b:
        ai = a.popleft()
        bi = b.popleft()

        if ai < bi:
            a.append(ai + n)
        else:
            b.append(bi + n)

    return "Alpha" if a else "Beta"

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
