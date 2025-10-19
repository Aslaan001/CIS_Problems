## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 


int main() {

    int t;
    cin >> t;

    while (t--) {
        int n, S;
        cin >> n >> S;
        vector<int> nums(n);
        for (int i = 0; i < n; i++) {
            cin >> nums[i];
        }
        cout << mysticSubarrayQuest(nums, S) << "\n";
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
            int S = sc.nextInt();
            int[] nums = new int[n];
            for (int i = 0; i < n; i++) {
                nums[i] = sc.nextInt();
            }
            System.out.println(mysticSubarrayQuest(nums, S));
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
        int n, S;
        scanf("%d %d", &n, &S);
        int nums[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &nums[i]);
        }
        printf("%d\n", mysticSubarrayQuest(nums, n, S));
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
        const S = parseInt(input[idx++]);
        const nums = [];
        for (let i = 0; i < n; i++) nums.push(Number(input[idx++]));
        console.log(mysticSubarrayQuest(nums, S));
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        n, S = map(int, input().split())
        nums = list(map(int, input().split()))
        print(mysticSubarrayQuest(nums, S))
        # evaluation completed

if __name__ == "__main__":
    main()
