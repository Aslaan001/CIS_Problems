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
        vector<int> arr(n);
        for (int i = 0; i < n; i++) {
            cin >> arr[i];
        }
        int k;
        cin >> k;

        vector<int> res = kthSmallestPrimeFraction(arr, k);
        cout << res[0] << " " << res[1] << "\n";
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
            int[] arr = new int[n];
            for (int i = 0; i < n; i++) {
                arr[i] = sc.nextInt();
            }
            int k = sc.nextInt();

            int[] res = kthSmallestPrimeFraction(arr, k);
            System.out.println(res[0] + " " + res[1]);
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
        int arr[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &arr[i]);
        }
        int k;
        scanf("%d", &k);

        int num, den;
        kthSmallestPrimeFraction(arr, n, k, &num, &den);
        printf("%d %d\n", num, den);
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
    const arr = [];
    for (let i = 0; i < n; i++) arr.push(Number(input[idx++]));
    const k = Number(input[idx++]);

    const res = kthSmallestPrimeFraction(arr, k);
    console.log(res[0] + " " + res[1]);
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
        k = int(input())

        res = kth_smallest_prime_fraction(arr, k)
        print(res[0], res[1])
        # evaluation completed

if __name__ == "__main__":
    main()
