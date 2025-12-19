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
        int n, h;
        cin >> n >> h;

        cout << countTallBST(n, h) << "\n";
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
            int h = sc.nextInt();

            System.out.println(countTallBST(n, h));
        }

        // evaluation completed
        sc.close();
    }
}
