## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int target, n;
        cin >> target >> n;
        vector<int> vals(n);
        for (int i = 0; i < n; i++) {
            cin >> vals[i];
        }

        cout << waysToReachTargetRepeatedValues(target, vals) << "\n";
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
            int target = sc.nextInt();
            int n = sc.nextInt();
            int[] vals = new int[n];
            for (int i = 0; i < n; i++) {
                vals[i] = sc.nextInt();
            }

            System.out.println(waysToReachTargetRepeatedValues(target, vals));
            // evaluation completed
        }
        sc.close();
    }
}


## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int target, n;
        scanf("%d %d", &target, &n);
        int vals[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &vals[i]);
        }

        printf("%d\n", waysToReachTargetRepeatedValues(target, vals, n));
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
        const target = parseInt(input[idx++]);
        const n = parseInt(input[idx++]);
        const vals = [];
        for (let i = 0; i < n; i++) vals.push(Number(input[idx++]));

        console.log(waysToReachTargetRepeatedValues(target, vals));
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        target = int(input())
        n = int(input())
        vals = list(map(int, input().split()))
        print(ways_to_reach_target_repeated_values(target, vals))
        # evaluation completed

if __name__ == "__main__":
    main()
