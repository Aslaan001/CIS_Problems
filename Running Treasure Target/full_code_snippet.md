## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 
int runningTreasureTarget(vector<int>& arr, int target) {
    long long sum = 0;
    for (int i = 0; i < arr.size(); i++) {
        sum += arr[i];
        if (sum >= target)
            return i;
    }
    return -1;
}

int main() {

    int t;
    cin >> t;

    while (t--) {
        int n;
        cin >> n;
        vector<int> nums(n);
        for (int i = 0; i < n; i++) {
            cin >> nums[i];
        }
        int target;
        cin >> target;
        cout << runningTreasureTarget(nums, target) << "\n";
    }
    return 0;
}


## JAVA

import java.util.*;

public class Main {
    // user code comes here
    public static int runningTreasureTarget(int[] arr, int target) {
        long sum = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
            if (sum >= target)
                return i;
        }
        return -1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] nums = new int[n];
            for (int i = 0; i < n; i++) {
                nums[i] = sc.nextInt();
            }
            int target = sc.nextInt();
            System.out.println(runningTreasureTarget(nums, target));
        }
        sc.close();
    }
}


## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here
int runningTreasureTarget(int nums[], int n, long long target) {
    long long sum = 0;
    for (int i = 0; i < n; i++) {
        sum += nums[i];
        if (sum >= target)
            return i;
    }
    return -1;
}

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        int nums[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &nums[i]);
        }
        long long target;
        scanf("%lld", &target);
        printf("%d\n", runningTreasureTarget(nums, n, target));
    }
    return 0;
}


## JAVASCRIPT

// user code comes here
function runningTreasureTarget(nums, target) {
  let sum = 0;
  for (let i = 0; i < nums.length; i++) {
    sum += nums[i];
    if (sum >= target) return i;
  }
  return -1;
}

function main() {
  const fs = require("fs");
  const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);
  let idx = 0;

  const t = parseInt(input[idx++]);
  for (let tc = 0; tc < t; tc++) {
    const n = parseInt(input[idx++]);
    const nums = [];
    for (let i = 0; i < n; i++) nums.push(Number(input[idx++]));
    const target = Number(input[idx++]);
    console.log(runningTreasureTarget(nums, target));
  }
}

main();


## PYTHON

# user code comes here
def runningTreasureTarget(nums, target):
    total = 0
    for i, val in enumerate(nums):
        total += val
        if total >= target:
            return i
    return -1

def main():
    t = int(input())
    for _ in range(t):
        n = int(input())
        nums = list(map(int, input().split()))
        target = int(input())
        print(runningTreasureTarget(nums, target))

if __name__ == "__main__":
    main()
