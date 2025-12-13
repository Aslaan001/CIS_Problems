## CPP

### SOLUTION

vector<pair<int,int>> buildOperations(int n) {
    vector<pair<int,int>> ops;

    int p = 1, c = 0;
    while (2 * p <= n) {
        p *= 2;
        c++;
    }

    function<void(int,int)> C = [&](int l, int r) {
        if (l == r) return;
        int mid = (l + r) / 2;
        C(l, mid);
        C(mid + 1, r);
        int len = r - l + 1;
        for (int i = l; i <= mid; i++) {
            ops.push_back({i, i + len / 2});
        }
    };

    C(1, p);
    C(n - p + 1, n);

    return ops;
}

### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256




## JAVA

### SOLUTION

static List<int[]> buildOperations(int n) {
    List<int[]> ops = new ArrayList<>();

    int p = 1, c = 0;
    while (2 * p <= n) {
        p *= 2;
        c++;
    }

    class Helper {
        void C(int l, int r) {
            if (l == r) return;
            int mid = (l + r) / 2;
            C(l, mid);
            C(mid + 1, r);
            int len = r - l + 1;
            for (int i = l; i <= mid; i++) {
                ops.add(new int[]{i, i + len / 2});
            }
        }
    }

    Helper h = new Helper();
    h.C(1, p);
    h.C(n - p + 1, n);

    return ops;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256
