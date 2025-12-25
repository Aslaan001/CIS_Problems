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
        for (int i = 0; i < n; i++) {
            cin >> nums[i];
        }
        int k;
        cin >> k;

        vector<int> res = slidingWindowMaximum(nums, k);
        for (int x : res) cout << x << " ";
        cout << "\n";
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
            for (int i = 0; i < n; i++) {
                nums[i] = sc.nextInt();
            }
            int k = sc.nextInt();

            int[] res = slidingWindowMaximum(nums, k);
            for (int x : res) System.out.print(x + " ");
            System.out.println();
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
        int nums[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &nums[i]);
        }
        int k;
        scanf("%d", &k);

        int res[n - k + 1];
        slidingWindowMaximum(nums, n, k, res);
        for (int i = 0; i < n - k + 1; i++) {
            printf("%d ", res[i]);
        }
        printf("\n");
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
        const k = parseInt(input[idx++]);

        const res = slidingWindowMaximum(nums, k);
        console.log(res.join(" "));
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
        k = int(input())
        res = sliding_window_maximum(nums, k)
        print(*res)
        # evaluation completed

if __name__ == "__main__":
    main()
