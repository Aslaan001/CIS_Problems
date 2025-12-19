## CPP

#include <bits/stdc++.h>
using namespace std;
typedef long long ll;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;

    while (t--) {
        int n, k;
        cin >> n >> k;

        cout << countValidPlaques(n, k) << "\n";
    }

    // evaluation completed
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

            System.out.println(countValidPlaques(n, k));
        }

        // evaluation completed
        sc.close();
    }
}
