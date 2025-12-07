## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    C[0][0] = 1;
    for (int i = 1; i <= MAXN; i++) {
        C[i][0] = 1;
        for (int j = 1; j <= i; j++)
            C[i][j] = (C[i-1][j-1] + C[i-1][j]) % MOD;
    }

    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;

        vector<int> s(n);
        for (int i = 0; i < n; i++) cin >> s[i];

        cout << reconstructPainting(n, s) << "\n";
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
            int[] s = new int[n];
            for (int i = 0; i < n; i++) s[i] = sc.nextInt();
            System.out.println(reconstructPainting(n, s));
            // evaluation completed
        }
        sc.close();
    }
}

