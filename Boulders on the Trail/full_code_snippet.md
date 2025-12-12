## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {

        int n, k;
        cin >> n >> k;

        vector<long long> a(n);
        for (int i = 0; i < n; i++)
            cin >> a[i];

        cout << minBoulders(a, n, k) << "\n";
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
            long k = sc.nextLong();

            long[] a = new long[n];
            for (int i = 0; i < n; i++)
                a[i] = sc.nextLong();

            System.out.println(minBoulders(a, n, k));
            // evaluation completed
        }

        sc.close();
    }
}
