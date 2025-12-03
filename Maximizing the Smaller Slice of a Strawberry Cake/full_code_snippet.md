## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, r;
        cin >> n >> r;

        vector<pair<long long,long long>> pts(n);
        for (int i = 0; i < n; i++) {
            cin >> pts[i].first >> pts[i].second;
        }

        cout << fixed << setprecision(12) << expectedArea(n, r, pts) << "\n";
        // execution completed 
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
            long r = sc.nextLong();
            long[][] pts = new long[n][2];
            for (int i = 0; i < n; i++) {
                pts[i][0] = sc.nextLong();
                pts[i][1] = sc.nextLong();
            }
            System.out.printf("%.12f\n", expectedArea(n, r, pts));
            // execution completed 
        }
        sc.close();
    }
}



