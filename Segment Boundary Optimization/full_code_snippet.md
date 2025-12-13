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

        vector<int> p(n);
        for (int i = 0; i < n; i++)
            cin >> p[i];

        vector<long long> a(n);
        for (int i = 0; i < n; i++)
            cin >> a[i];

        cout << minimumCost(p, a, n) << "\n";
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

            int[] p = new int[n];
            for (int i = 0; i < n; i++)
                p[i] = sc.nextInt();

            long[] a = new long[n];
            for (int i = 0; i < n; i++)
                a[i] = sc.nextLong();

            System.out.println(minimumCost(p, a, n));
            // evaluation completed
        }

        sc.close();
    }
}
