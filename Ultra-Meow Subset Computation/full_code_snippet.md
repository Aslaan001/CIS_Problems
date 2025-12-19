## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    // PRECOMPUTE BINOMIAL COEFFICIENTS
    for (int i = 0; i <= 5000; i++) {
        for (int j = 0; j <= i; j++) {
            if (j == 0) f[i][j] = 1;
            else f[i][j] = (f[i - 1][j - 1] + f[i - 1][j]) % MOD;
        }
    }

    int t;
    cin >> t;

    while (t--) {
        int n;
        cin >> n;

        cout << MEOW(n) << "\n";
    }

    // evaluation completed
    return 0;
}


## JAVA

import java.util.*;

public class Main {

    // user code comes here

    public static void main(String[] args) {

        init();

        Scanner sc = new Scanner(System.in);

        int t = sc.nextInt();

        while (t-- > 0) {
            int n = sc.nextInt();

            System.out.println(MEOW(n));
        }

        // evaluation completed
        sc.close();
    }
}
