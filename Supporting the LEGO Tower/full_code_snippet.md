## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here


int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        long long h;
        cin >> n >> h;

        vector<long long> x(n);
        for (int i = 0; i < n; i++) {
            cin >> x[i];
        }

        cout << minBricks(n, h, x) << "\n";
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
            long h = sc.nextLong();
            long[] x = new long[n];
            for (int i = 0; i < n; i++) {
                x[i] = sc.nextLong();
            }
            System.out.println(minBricks(n, h, x));
            // evaluation completed
        }
        sc.close();
    }
}
