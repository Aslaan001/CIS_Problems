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
        vector<int> prices(n);
        for (int i = 0; i < n; i++) {
            cin >> prices[i];
        }

        cout << maximumProfitMultipleTrades(prices) << "\n";
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
            int[] prices = new int[n];
            for (int i = 0; i < n; i++) {
                prices[i] = sc.nextInt();
            }

            System.out.println(maximumProfitMultipleTrades(prices));
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
        int n;
        scanf("%d", &n);
        int prices[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &prices[i]);
        }

        printf("%d\n", maximumProfitMultipleTrades(prices, n));
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
    const prices = [];
    for (let i = 0; i < n; i++) prices.push(Number(input[idx++]));

    console.log(maximumProfitMultipleTrades(prices));
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
        prices = list(map(int, input().split()))
        print(maximum_profit_multiple_trades(prices))
        # evaluation completed

if __name__ == "__main__":
    main()
