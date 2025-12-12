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

        vector<int> c(n);
        for (int i = 0; i < n; i++) cin >> c[i];

        cout << countNicePaths(n, k, c) << "\n";
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
            int k = sc.nextInt();

            int[] c = new int[n];
            for (int i = 0; i < n; i++) c[i] = sc.nextInt();

            System.out.println(countNicePaths(n, k, c));
            // evaluation completed
        }

        sc.close();
    }
}
