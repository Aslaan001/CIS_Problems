## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;

    while (t--) {
        int n;
        cin >> n;

        vector<long long> a(n);
        for (int i = 0; i < n; i++) {
            cin >> a[i];
        }

        cout << countMaxMagnitudeWays(n, a) << "\n";
    }

    // evaluation completed
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

            long[] a = new long[n];
            for (int i = 0; i < n; i++) {
                a[i] = sc.nextLong();
            }

            System.out.println(countMaxMagnitudeWays(n, a));
        }

        // evaluation completed
        sc.close();
    }
}
