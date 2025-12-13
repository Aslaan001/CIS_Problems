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
        int n;
        cin >> n;

        vector<pair<int,int>> ops = buildOperations(n);

        cout << ops.size() << "\n";
        for (auto &p : ops) {
            cout << p.first << " " << p.second << "\n";
        }
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

            List<int[]> ops = buildOperations(n);

            System.out.println(ops.size());
            for (int[] p : ops) {
                System.out.println(p[0] + " " + p[1]);
            }
            // evaluation completed
        }

        sc.close();
    }
}

