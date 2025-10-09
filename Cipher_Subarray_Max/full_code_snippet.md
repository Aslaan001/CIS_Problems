## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int n;
    cin >> n;
    vector<int> nums(n);
    for (int i = 0; i < n; i++) cin >> nums[i];
    int k;
    cin >> k;
    cout << maxSubarraySum(nums, k);
    return 0;
}


## JAVA

import java.util.*;

public class Main {
    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        int k = sc.nextInt();
        System.out.print(maxSubarraySum(nums, k));
        sc.close();
    }
}


## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here

int main() {
    int n;
    scanf("%d", &n);
    int nums[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &nums[i]);
    }
    int k;
    scanf("%d", &k);
    printf("%d", maxSubarraySum(n, nums, k));
    return 0;
}


## JAVASCRIPT

// user code comes here

function main() {
  const fs = require("fs");
  const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);

  const n = parseInt(input[0]);
  const nums = input.slice(1, n + 1).map(Number);
  const k = parseInt(input[n + 1]);

  console.log(maxSubarraySum(nums, k));
}

main();


## PYTHON

# user code comes here

def main():
    n = int(input())
    nums = list(map(int, input().split()))
    k = int(input())
    print(maxSubarraySum(nums, k))


if __name__ == "__main__":
    main()
