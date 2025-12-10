## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, m;
        cin >> n >> m;

        vector<long long> a(n), b(m);
        for (int i = 0; i < n; i++) cin >> a[i];
        for (int i = 0; i < m; i++) cin >> b[i];

        cout << minRequiredK(a, b) << "\n";
        // evaluation completed
    }
    return 0;
}



## JAVA

import java.util.*;

public class Main {

    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int m = sc.nextInt();

            long[] a = new long[n];
            long[] b = new long[m];

            for (int i = 0; i < n; i++) a[i] = sc.nextLong();
            for (int i = 0; i < m; i++) b[i] = sc.nextLong();

            System.out.println(minRequiredK(a, b));
            // evaluation completed
        }
        sc.close();
    }
}
