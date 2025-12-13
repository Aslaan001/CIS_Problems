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
        vector<int> nums(2*n);
        for (int i = 0; i < 2*n; i++) {
            cin >> nums[i];
        }
        cout << maxGCDScore(nums) << "\n";
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
            int[] nums = new int[2*n];
            for (int i = 0; i < 2*n; i++) {
                nums[i] = sc.nextInt();
            }
            System.out.println(maxGCDScore(nums));
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
        int nums[2*n];
        for (int i = 0; i < 2*n; i++) {
            scanf("%d", &nums[i]);
        }
        long long ans = maxGCDScore(nums, 2*n);
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
    const nums = [];
    for (let i = 0; i < 2*n; i++) nums.push(parseInt(input[idx++]));
    console.log(maxGCDScore(nums));
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
        nums = list(map(int, input().split()))
        print(maxGCDScore(nums))
        # evaluation completed

if __name__ == "__main__":
    main()
