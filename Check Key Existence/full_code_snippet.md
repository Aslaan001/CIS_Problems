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
        int key;
        cin >> key;
        cout << (checkKeyExists(nums, key) ? "true" : "false") << "\n";
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
            int key = sc.nextInt();
            System.out.println(checkKeyExists(nums, key));
        }
        sc.close();
    }
}


## C

#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

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
        int key;
        scanf("%d", &key);
        printf("%s\n", checkKeyExists(nums, n, key) ? "true" : "false");
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
        const key = Number(input[idx++]);
        console.log(checkKeyExists(nums, key));
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
        key = int(input())
        print(checkKeyExists(nums, key))

if __name__ == "__main__":
    main()
