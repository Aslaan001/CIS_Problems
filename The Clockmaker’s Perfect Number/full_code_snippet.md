## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int tc;
    cin >> tc;
    while (tc--) {
        string num;
        long long t;
        cin >> num >> t;
        cout << smallestPerfectNumber(num, t) << "\n";
        // evaluation completed
    }
    return 0;
}




## JAVA

import java.util.*;

public class Main {

    // user code comes here

    static String smallestPerfectNumber(String num, long t) {
        return "-1";
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int tc = sc.nextInt();
        while (tc-- > 0) {
            String num = sc.next();
            long t = sc.nextLong();
            System.out.println(smallestPerfectNumber(num, t));
            // evaluation completed
        }

        sc.close();
    }
}

