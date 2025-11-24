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
        vector<int> nums(n);
        for (int i = 0; i < n; i++) cin >> nums[i];
        int target;
        cin >> target;

        pair<int,int> ans = twoSum(nums, target);
        cout << ans.first << " " << ans.second << "\n";
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

            int[] ans = twoSum(nums, target);
            System.out.println(ans[0] + " " + ans[1]);
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
        int nums[n];
        for (int i = 0; i < n; i++) scanf("%d", &nums[i]);
        int target;
        scanf("%d", &target);

        int a, b;
        twoSum(nums, n, target, &a, &b);
        printf("%d %d\n", a, b);
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

  for (let _ = 0; _ < t; _++) {
    const n = parseInt(input[idx++]);
    const nums = [];
    for (let i = 0; i < n; i++) nums.push(Number(input[idx++]));
    const target = Number(input[idx++]);

    const ans = twoSum(nums, target);
    console.log(ans[0], ans[1]);
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
        a, b = twoSum(nums, target)
        print(a, b)
        # evaluation completed

if __name__ == "__main__":
    main()
