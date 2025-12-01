## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {

    int t;
    cin >> t;
    while (t--) {
        int n, m, k;
        cin >> n >> m >> k;

        vector<pair<int,int>> storms(m);
        for (int i = 0; i < m; i++) cin >> storms[i].first >> storms[i].second;

        cout << computeMaxDry(n, m, k, storms) << "\n";
    }
    return 0;
}

    

## JAVA

## JAVA

import java.util.*;

public class Main {

    // user code comes here

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int T = sc.nextInt();

        while (T-- > 0) {
            int n = sc.nextInt();
            int m = sc.nextInt();
            int k = sc.nextInt();

            int[][] storms = new int[m][2];
            for (int i = 0; i < m; i++) {
                storms[i][0] = sc.nextInt();
                storms[i][1] = sc.nextInt();
            }

            System.out.println(computeMaxDry(n, m, k, storms));
        }

        sc.close();
    }
}


