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
        vector<int> brightness(n);
        for (int i = 0; i < n; i++) {
            cin >> brightness[i];
        }
        int k;
        cin >> k;
        cout << fixed << setprecision(5) << celestialSubarrayAverage(brightness, k) << "\n";
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
            int[] brightness = new int[n];
            for (int i = 0; i < n; i++) {
                brightness[i] = sc.nextInt();
            }
            int k = sc.nextInt();
            System.out.printf("%.5f\n", celestialSubarrayAverage(brightness, k));
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
        int brightness[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &brightness[i]);
        }
        int k;
        scanf("%d", &k);
        printf("%.5f\n", celestialSubarrayAverage(n, brightness, k));
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
    const brightness = [];
    for (let i = 0; i < n; i++) brightness.push(Number(input[idx++]));
    const k = parseInt(input[idx++]);
    console.log(celestialSubarrayAverage(brightness, k).toFixed(5));
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
        brightness = list(map(int, input().split()))
        k = int(input())
        print(f"{celestialSubarrayAverage(brightness, k):.5f}")
        # evaluation completed

if __name__ == "__main__":
    main()
