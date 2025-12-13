## CPP

### SOLUTION

string smallestPerfectNumber(string num, long long t) {

    auto gcd = [&](long long a, long long b) {
        while (a) {
            long long r = b % a;
            b = a;
            a = r;
        }
        return b;
    };

    int n = num.size();
    vector<long long> rem(n + 1);
    rem[0] = t;

    int end = n;
    for (int i = 0; i < n; i++) {
        if (num[i] == '0') {
            end = i + 1;
            break;
        }
        rem[i + 1] = rem[i] / gcd(rem[i], num[i] - '0');
    }

    if (end == n && rem[n] == 1) return num;

    for (int i = end - 1; i >= 0; i--) {
        while (num[i] < '9') {
            long long cur = rem[i];
            num[i]++;
            cur /= gcd(cur, num[i] - '0');

            for (int j = n - 1; j > i; j--) {
                for (int d = 9; d >= 1; d--) {
                    if (cur % d == 0) {
                        cur /= d;
                        num[j] = char('0' + d);
                        break;
                    }
                }
            }
            if (cur == 1) return num;
        }
    }

    string res;
    for (int d = 9; d >= 2; d--) {
        while (t % d == 0) {
            res.push_back(char('0' + d));
            t /= d;
        }
    }

    if (t != 1) return "-1";

    reverse(res.begin(), res.end());

    if (res.size() > num.size() || (res.size() == num.size() && res > num))
        return res;

    int diff = num.size() - res.size();
    string cand = string(diff, '1') + res;

    if (cand.size() > num.size() || cand > num)
        return cand;

    return string(diff + 1, '1') + res;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256




## JAVA

### SOLUTION

public static String smallestPerfectNumber(String num, long t) {

    int n = num.length();
    long[] rem = new long[n + 1];
    rem[0] = t;

    int end = n;
    for (int i = 0; i < n; i++) {
        if (num.charAt(i) == '0') {
            end = i + 1;
            break;
        }
        rem[i + 1] = rem[i] / gcd(rem[i], num.charAt(i) - '0');
    }

    if (end == n && rem[n] == 1) return num;

    char[] arr = num.toCharArray();

    for (int i = end - 1; i >= 0; i--) {
        while (arr[i] < '9') {
            long cur = rem[i];
            arr[i]++;
            cur /= gcd(cur, arr[i] - '0');

            for (int j = n - 1; j > i; j--) {
                for (int d = 9; d >= 1; d--) {
                    if (cur % d == 0) {
                        cur /= d;
                        arr[j] = (char)('0' + d);
                        break;
                    }
                }
            }
            if (cur == 1) return new String(arr);
        }
    }

    StringBuilder res = new StringBuilder();
    for (int d = 9; d >= 2; d--) {
        while (t % d == 0) {
            res.append(d);
            t /= d;
        }
    }

    if (t != 1) return "-1";

    res.reverse();

    if (res.length() > num.length() ||
        (res.length() == num.length() && res.toString().compareTo(num) > 0))
        return res.toString();

    int diff = num.length() - res.length();
    String cand = "1".repeat(diff) + res;

    if (cand.length() > num.length() || cand.compareTo(num) > 0)
        return cand;

    return "1".repeat(diff + 1) + res;
}

private static long gcd(long a, long b) {
    while (a != 0) {
        long r = b % a;
        b = a;
        a = r;
    }
    return b;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256
