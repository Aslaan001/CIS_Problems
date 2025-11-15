## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int _t;
    cin >> _t;

    while (_t--) {
        int n;
        cin >> n;

        vector<int> nums(n);
        for (int i = 0; i < n; i++) {
            cin >> nums[i];
        }

        int result = solve(nums);
        cout << result << "\n";
        // evaluation completed
    }

    return 0;
}

## JAVA

import java.io.*;
import java.util.*;

public class Main {

    // user code comes here

    public static void main(String[] args) throws Exception {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        int _t = Integer.parseInt(br.readLine().trim());

        while (_t-- > 0) {
            int n = Integer.parseInt(br.readLine().trim());

            String[] arrStr = br.readLine().trim().split("\\s+");
            int[] nums = new int[n];

            for (int i = 0; i < n; i++) {
                nums[i] = Integer.parseInt(arrStr[i]);
            }

            int result = solve(nums);
            System.out.println(result);
            // evaluation completed
        }
    }
}

## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here

int main() {
    int _t;
    if (scanf("%d", &_t) != 1) return 0;

    while (_t--) {
        int n;
        if (scanf("%d", &n) != 1) return 0;

        int* nums = (int*)malloc(n * sizeof(int));
        if (!nums) return 1;

        for (int i = 0; i < n; i++) {
            scanf("%d", &nums[i]);
        }

        int result = solve(nums, n);
        printf("%d\n", result);

        free(nums);
        // evaluation completed
    }

    return 0;
}


## JAVASCRIPT

const readline = require("readline");

// user code comes here

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
    terminal: false,
});

let input = [];

rl.on("line", (line) => {
    input.push(...line.trim().split(/\s+/).map(Number));
});

rl.on("close", () => {
    if (input.length === 0) return;

    let t = input[0];
    let idx = 1;

    for (let _ = 0; _ < t; _++) {
        const n = input[idx++];
        const nums = input.slice(idx, idx + n);
        idx += n;

        const result = solve(nums);
        console.log(result);
        // evaluation completed
    }
});

## PYTHON

import sys
import collections

# user code comes here

def main():
    data = list(map(int, sys.stdin.read().split()))
    if not data:
        return

    t = data[0]
    idx = 1

    for _ in range(t):
        n = data[idx]
        idx += 1

        nums = data[idx:idx+n]
        idx += n

        result = solve(nums)
        print(result)
        # evaluation completed

if __name__ == "__main__":
    main()
