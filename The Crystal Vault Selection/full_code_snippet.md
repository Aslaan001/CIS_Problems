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

        vector<vector<vector<long long>>> cube(
            n, vector<vector<long long>>(n, vector<long long>(n))
        );

        for (int x = 0; x < n; x++) {
            for (int y = 0; y < n; y++) {
                for (int z = 0; z < n; z++) {
                    cin >> cube[x][y][z];
                }
            }
        }

        cout << minCubeSum(n, cube) << "\n";
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

            long[][][] cube = new long[n][n][n];

            for (int x = 0; x < n; x++) {
                for (int y = 0; y < n; y++) {
                    for (int z = 0; z < n; z++) {
                        cube[x][y][z] = sc.nextLong();
                    }
                }
            }

            System.out.println(minCubeSum(n, cube));
        }

        sc.close();
    }
}
