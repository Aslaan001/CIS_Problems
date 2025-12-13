## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        int n, k;
        cin >> n >> k;
        vector<int> nums(n);
        for (int i = 0; i < n; i++) {
            cin >> nums[i];
        }
        cout << minTotalIncompatibility(nums, k) << "\n";
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
            int k = sc.nextInt();
            int[] nums = new int[n];
            for (int i = 0; i < n; i++) {
                nums[i] = sc.nextInt();
            }
            System.out.println(minTotalIncompatibility(nums, k));
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
        int n, k;
        scanf("%d", &n);
        scanf("%d", &k);
        int nums[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &nums[i]);
        }
        long long ans = minTotalIncompatibility(nums, n, k);
        printf("%lld\n", ans);
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
    const k = parseInt(input[idx++]);

    const nums = [];
    for (let i = 0; i < n; i++) nums.push(parseInt(input[idx++]));

    console.log(minTotalIncompatibility(nums, k));
    // evaluation completed
  }
}

main();

## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        n, k = map(int, input().split())
        nums = list(map(int, input().split()))
        print(minTotalIncompatibility(nums, k))
        # evaluation completed

if __name__ == "__main__":
    main()
