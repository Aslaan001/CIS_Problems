## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, target;
        cin >> n;
        vector<int> nums(n);
        for (int i = 0; i < n; i++) {
            cin >> nums[i];
        }
        cin >> target;

        cout << maximumLengthSequenceSummingToTarget(nums, target) << "\n";
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
            int[] nums = new int[n];
            for (int i = 0; i < n; i++) nums[i] = sc.nextInt();
            int target = sc.nextInt();

            System.out.println(maximumLengthSequenceSummingToTarget(nums, target));
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
        int n, target;
        scanf("%d", &n);
        int nums[n];
        for (int i = 0; i < n; i++) scanf("%d", &nums[i]);
        scanf("%d", &target);

        printf("%d\n", maximumLengthSequenceSummingToTarget(nums, n, target));
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
    for (let i = 0; i < n; i++) nums.push(Number(input[idx++]));
    const target = parseInt(input[idx++]);

    console.log(maximumLengthSequenceSummingToTarget(nums, target));
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
        target = int(input())
        print(maximum_length_sequence_summing_to_target(nums, target))
        # evaluation completed

if __name__ == "__main__":
    main()
