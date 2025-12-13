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
        vector<int> nums1(n), nums2(n);
        for (int i = 0; i < n; i++) cin >> nums1[i];
        for (int i = 0; i < n; i++) cin >> nums2[i];
        cout << minXorSum(nums1, nums2) << "\n";
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
            int[] nums1 = new int[n];
            int[] nums2 = new int[n];
            for (int i = 0; i < n; i++) nums1[i] = sc.nextInt();
            for (int i = 0; i < n; i++) nums2[i] = sc.nextInt();
            System.out.println(minXorSum(nums1, nums2));
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
        int nums1[n], nums2[n];
        for (int i = 0; i < n; i++) scanf("%d", &nums1[i]);
        for (int i = 0; i < n; i++) scanf("%d", &nums2[i]);
        long long ans = minXorSum(nums1, nums2, n);
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
    const nums1 = [];
    const nums2 = [];
    for (let i = 0; i < n; i++) nums1.push(parseInt(input[idx++]));
    for (let i = 0; i < n; i++) nums2.push(parseInt(input[idx++]));
    console.log(minXorSum(nums1, nums2));
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
        nums1 = list(map(int, input().split()))
        nums2 = list(map(int, input().split()))
        print(minXorSum(nums1, nums2))
        # evaluation completed

if __name__ == "__main__":
    main()
