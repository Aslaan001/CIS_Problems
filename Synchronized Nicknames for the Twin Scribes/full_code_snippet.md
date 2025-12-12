## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int N, M;
        cin >> N >> M;

        string A, B;
        cin >> A >> B;

        cout << countNicknamePairs(A, B) << "\n";
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

            int N = sc.nextInt();
            int M = sc.nextInt();

            String A = sc.next();
            String B = sc.next();

            System.out.println(countNicknamePairs(A, B));
            // evaluation completed
        }

        sc.close();
    }
}
