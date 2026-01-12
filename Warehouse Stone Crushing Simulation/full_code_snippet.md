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
        vector<int> stones(n);
        for (int i = 0; i < n; i++) {
            cin >> stones[i];
        }

        cout << lastStoneWeight(stones) << "\n";
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
            int[] stones = new int[n];
            for (int i = 0; i < n; i++) {
                stones[i] = sc.nextInt();
            }

            System.out.println(lastStoneWeight(stones));
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
        int stones[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &stones[i]);
        }

        printf("%d\n", lastStoneWeight(stones, n));
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
        const stones = [];
        for (let i = 0; i < n; i++) {
            stones.push(Number(input[idx++]));
        }

        console.log(lastStoneWeight(stones));
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
        stones = list(map(int, input().split()))

        print(last_stone_weight(stones))
        # evaluation completed


if __name__ == "__main__":
    main()
