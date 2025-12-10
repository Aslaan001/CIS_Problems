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

        vector<pair<int,int>> seg(m);
        for (int i = 0; i < m; i++) {
            cin >> seg[i].first >> seg[i].second;
        }

        cout << maxFedCats(n, m, seg) << "\n";
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

            long[][] seg = new long[m][2];
            for (int i = 0; i < m; i++) {
                seg[i][0] = sc.nextLong();
                seg[i][1] = sc.nextLong();
            }

            System.out.println(maxFedCats(n, m, seg));
            // evaluation completed
        }

        sc.close();
    }
}
