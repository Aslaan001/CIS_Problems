### SOLUTION

## CPP

#define fr first
#define sc second
typedef pair<int,int> pa;
const int N = 200000 + 7;

set<pa> dp[15];
pa a[N];

int computeMaxDry(int n, int m, int k, const vector<pair<int,int>>& storms) {

    for (int i = 0; i <= k; i++) dp[i].clear();

    for (int i = 1; i <= m; i++) {
        a[i].sc = storms[i-1].first;
        a[i].fr = storms[i-1].second;
    }

    sort(a + 1, a + m + 1);

    dp[0].emplace(n + 1, 0);

    for (int i = m; i >= 1; i--) {
        for (int j = k; j >= 0; j--) {

            int mx = -1;

            while (!dp[j].empty() && a[i].sc < prev(dp[j].end())->fr) {
                auto it = prev(dp[j].end());
                mx = max(mx, max(it->fr - a[i].fr - 1, 0) + it->sc);
                dp[j+1].insert(*it);
                dp[j].erase(it);
            }

            if (mx >= 0)
                dp[j].emplace(a[i].sc, mx);
        }
    }

    int ans = 0;
    for (auto &x : dp[k])
        ans = max(ans, x.fr + x.sc - 1);

    return ans;
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

 static class Pair implements Comparable<Pair> {
        int fr, sc;
        Pair(int f, int s) { fr = f; sc = s; }

        public int compareTo(Pair o) {
            if (fr != o.fr) return fr - o.fr;
            return sc - o.sc;
        }
    }

    @SuppressWarnings("unchecked")
    static TreeSet<Pair>[] dp = new TreeSet[15];
    static Pair[] a = new Pair[200000 + 7];

    static int computeMaxDry(int n, int m, int k, int[][] storms) {

        // FIX: initialize all slots, NOT only 0..k
        for (int i = 0; i < 15; i++)
            dp[i] = new TreeSet<>();

        for (int i = 1; i <= m; i++)
            a[i] = new Pair(storms[i-1][1], storms[i-1][0]);

        Arrays.sort(a, 1, m+1, Comparator.comparingInt(o -> o.fr));

        dp[0].add(new Pair(n + 1, 0));

        for (int i = m; i >= 1; i--) {
            for (int j = k; j >= 0; j--) {

                int mx = -1;

                while (!dp[j].isEmpty()) {
                    Pair last = dp[j].last();
                    if (a[i].sc >= last.fr) break;

                    mx = Math.max(mx, Math.max(last.fr - a[i].fr - 1, 0) + last.sc);
                    dp[j+1].add(last);
                    dp[j].remove(last);
                }

                if (mx >= 0)
                    dp[j].add(new Pair(a[i].sc, mx));
            }
        }

        int ans = 0;
        for (Pair x : dp[k])
            ans = Math.max(ans, x.fr + x.sc - 1);

        return ans;
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



