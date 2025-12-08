## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here


int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        long long w, v, u;
        cin >> n >> w >> v >> u;

        vector<pair<long long,long long>> poly(n);
        for (int i = 0; i < n; i++) {
            cin >> poly[i].first >> poly[i].second;
        }

        cout << fixed << setprecision(12) << crossTime(n, w, v, u, poly) << "\n";
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
            long w = sc.nextLong();
            long v = sc.nextLong();
            long u = sc.nextLong();
            long[][] poly = new long[n][2];
            for (int i = 0; i < n; i++) {
                poly[i][0] = sc.nextLong();
                poly[i][1] = sc.nextLong();
            }
            System.out.printf("%.12f\n", crossTime(n, w, v, u, poly));
            // evaluation completed 
        }
        sc.close();
    }
}

