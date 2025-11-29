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
        vector<long long> costs(n + 1);
        for (int i = 1; i <= n; i++) {
            cin >> costs[i];
        }

        cout << minCostToReachTop(costs, n) << "\n";
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
            long[] costs = new long[n + 1];
            for (int i = 1; i <= n; i++) {
                costs[i] = sc.nextLong();
            }

            System.out.println(minCostToReachTop(costs, n));
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
        long long costs[n + 1];
        for (int i = 1; i <= n; i++) {
            scanf("%lld", &costs[i]);
        }

        printf("%lld\n", minCostToReachTop(costs, n));
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
        const costs = new Array(n + 1);
        for (let i = 1; i <= n; i++) costs[i] = Number(input[idx++]);

        console.log(minCostToReachTop(costs, n));
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
        arr = list(map(int, input().split()))
        costs = [0] + arr
        print(min_cost_to_reach_top(costs, n))
        # evaluation completed

if __name__ == "__main__":
    main()
