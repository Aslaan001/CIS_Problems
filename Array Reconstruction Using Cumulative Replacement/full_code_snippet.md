## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        vector<long long> target(n);
        for (int i = 0; i < n; i++) {
            cin >> target[i];
        }

        if (isPossible(target))
            cout << "YES\n";
        else
            cout << "NO\n";
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
            long[] target = new long[n];
            for (int i = 0; i < n; i++) {
                target[i] = sc.nextLong();
            }

            if (isPossible(target))
                System.out.println("YES");
            else
                System.out.println("NO");
            // evaluation completed
        }
        sc.close();
    }
}


## C

#include <stdio.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        long long target[n];
        for (int i = 0; i < n; i++) {
            scanf("%lld", &target[i]);
        }

        if (isPossible(target, n))
            printf("YES\n");
        else
            printf("NO\n");
        // evaluation completed
    }
    return 0;
}


## JAVASCRIPT

// user code comes here

function main() {
    const fs = require("fs");
    const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);
    let idx = 0;

    const t = parseInt(input[idx++]);
    for (let tc = 0; tc < t; tc++) {
        const n = parseInt(input[idx++]);
        const target = [];
        for (let i = 0; i < n; i++) target.push(BigInt(input[idx++]));

        if (isPossible(target))
            console.log("YES");
        else
            console.log("NO");
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        n = int(input())
        target = list(map(int, input().split()))

        if is_possible(target):
            print("YES")
        else:
            print("NO")
        # evaluation completed

if __name__ == "__main__":
    main()
