## CPP

### SOLUTION

double expectedArea(int n, long long r, const vector<pair<long long,long long>>& pts) {
    const long double pi = acosl(-1);
    vector<pair<long double,long double>> p(n+1);
    for (int i = 1; i <= n; i++) {
        p[i].first = pts[i-1].first;
        p[i].second = pts[i-1].second;
    }
    auto sub = [&](int A, int B){
        return make_pair(p[A].first - p[B].first, p[A].second - p[B].second);
    };
    auto cross = [&](pair<long double,long double> A, pair<long double,long double> B){
        return A.first * B.second - A.second * B.first;
    };
    auto len = [&](pair<long double,long double> A){
        return sqrtl(A.first*A.first + A.second*A.second);
    };

    for (int i = 2; i <= n; i++) {
        if (p[i].second < p[1].second || 
           (p[i].second == p[1].second && p[i].first < p[1].first)) 
            swap(p[i], p[1]);
    }

    vector<int> idx(n-1);
    for (int i = 2; i <= n; i++) idx[i-2] = i;

    sort(idx.begin(), idx.end(), [&](int A, int B){
        auto c = cross(sub(A,1), sub(B,1));
        if (fabsl(c) > 0) return c > 0;
        return p[A].second > p[B].second;
    });

    vector<int> stk;
    stk.push_back(1);
    for (int x : idx) {
        while (stk.size() > 1) {
            auto A = sub(stk.back(), stk[stk.size()-2]);
            auto B = sub(x, stk.back());
            if (cross(A, B) < 0) stk.pop_back();
            else break;
        }
        stk.push_back(x);
    }

    long double d = r;

    for (int i = 0; i < (int)stk.size(); i++) {
        int A = stk[i];
        int B = stk[(i+1) % stk.size()];
        auto e = sub(B, A);

        auto S = cross(e, make_pair(-p[A].first, -p[A].second));
        if (S <= 0) {
            long double res = pi * r * r / 2.0;
            return (double)res;
        }

        long double L = len(e);
        d = min(d, S / L);
    }

    long double ang = acosl(d / r);
    long double ans = ang * r * r - d * sqrtl(r*r - d*d);
    return (double)ans;
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static double expectedArea(int n, long r, long[][] pts) {
    double pi = Math.acos(-1.0);
    double[][] p = new double[n + 1][2];
    for (int i = 1; i <= n; i++) {
        p[i][0] = pts[i - 1][0];
        p[i][1] = pts[i - 1][1];
    }

    java.util.function.BiFunction<Integer, Integer, double[]> sub = (A, B) -> {
        return new double[]{p[A][0] - p[B][0], p[A][1] - p[B][1]};
    };

    java.util.function.BiFunction<double[], double[], Double> cross = (A, B) -> {
        return A[0] * B[1] - A[1] * B[0];
    };

    java.util.function.Function<double[], Double> len = (A) -> {
        return Math.sqrt(A[0] * A[0] + A[1] * A[1]);
    };

    for (int i = 2; i <= n; i++) {
        if (p[i][1] < p[1][1] || (p[i][1] == p[1][1] && p[i][0] < p[1][0])) {
            double t0 = p[i][0], t1 = p[i][1];
            p[i][0] = p[1][0]; p[i][1] = p[1][1];
            p[1][0] = t0; p[1][1] = t1;
        }
    }

    Integer[] idx = new Integer[n - 1];
    for (int i = 2; i <= n; i++) idx[i - 2] = i;

    java.util.Arrays.sort(idx, (A, B) -> {
        double[] sA = sub.apply(A, 1);
        double[] sB = sub.apply(B, 1);
        double c = cross.apply(sA, sB);
        if (Math.abs(c) > 0) return c > 0 ? -1 : 1;
        return Double.compare(p[B][1], p[A][1]);
    });

    java.util.ArrayList<Integer> stk = new java.util.ArrayList<>();
    stk.add(1);

    for (int x : idx) {
        while (stk.size() > 1) {
            int sz = stk.size();
            double[] A1 = sub.apply(stk.get(sz - 1), stk.get(sz - 2));
            double[] B1 = sub.apply(x, stk.get(sz - 1));
            if (cross.apply(A1, B1) < 0) stk.remove(sz - 1);
            else break;
        }
        stk.add(x);
    }

    double d = r;

    for (int i = 0; i < stk.size(); i++) {
        int A = stk.get(i);
        int B = stk.get((i + 1) % stk.size());
        double[] e = sub.apply(B, A);
        double S = cross.apply(e, new double[]{-p[A][0], -p[A][1]});
        if (S <= 0) {
            double res = pi * r * r / 2.0;
            return res;
        }
        double L = len.apply(e);
        d = Math.min(d, S / L);
    }

    double ang = Math.acos(d / r);
    double ans = ang * r * r - d * Math.sqrt(r * r - d * d);
    return ans;
}



### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



