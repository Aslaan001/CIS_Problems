## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, k;
        cin >> n;
        vector<int> v(n);
        for (int i = 0; i < n; i++) {
            cin >> v[i];
        }
        cin >> k;

        cout << timeRequiredToBuyTickets(v, k) << "\n";
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
            int[] v = new int[n];
            for (int i = 0; i < n; i++) {
                v[i] = sc.nextInt();
            }
            int k = sc.nextInt();

            System.out.println(timeRequiredToBuyTickets(v, k));
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
        int n, k;
        scanf("%d", &n);
        int v[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &v[i]);
        }
        scanf("%d", &k);

        printf("%lld\n", timeRequiredToBuyTickets(v, n, k));
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
        const v = [];
        for (let i = 0; i < n; i++) {
            v.push(Number(input[idx++]));
        }
        const k = parseInt(input[idx++]);

        console.log(timeRequiredToBuyTickets(v, k));
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
        v = list(map(int, input().split()))
        k = int(input())
        print(time_required_to_buy_tickets(v, k))
        # evaluation completed

if __name__ == "__main__":
    main()
