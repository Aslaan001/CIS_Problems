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

        int n, m;
        cin >> n >> m;

        vector<string> likes(m);
        for (int i = 0; i < m; i++) {
            cin >> likes[i];
        }

        vector<int> a(n);
        for (int i = 0; i < n; i++) {
            cin >> a[i];
        }

        vector<long long> ans = countValidPairs(n, m, likes, a);

        for (long long x : ans) {
            cout << x << " ";
        }
        cout << "\n";
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

            String[] likes = new String[m];
            for (int i = 0; i < m; i++) {
                likes[i] = sc.next();
            }

            int[] a = new int[n];
            for (int i = 0; i < n; i++) {
                a[i] = sc.nextInt();
            }

            long[] ans = countValidPairs(n, m, likes, a);

            for (long x : ans) {
                System.out.print(x + " ");
            }
            System.out.println();
            // evaluation completed
        }

        sc.close();
    }
}

