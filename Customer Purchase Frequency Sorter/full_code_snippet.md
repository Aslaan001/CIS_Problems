## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here


void printVector(const vector<int>& vec) {
    for (int i = 0; i < vec.size(); i++)
        cout << vec[i] << (i == vec.size() - 1 ? "" : " ");
    cout << "\n";
}

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        vector<int> nums(n);
        for (int i = 0; i < n; i++) cin >> nums[i];
        vector<int> result = sortbyFreq(nums);
        printVector(result);
    }
    return 0;
}



## JAVA

import java.util.*;


// use code comes here 

public class Main {
    public static void printArray(int[] arr) {
        for (int i = 0; i < arr.length; i++)
            System.out.print(arr[i] + (i == arr.length - 1 ? "" : " "));
        System.out.println();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        Solution s = new Solution();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] nums = new int[n];
            for (int i = 0; i < n; i++) nums[i] = sc.nextInt();
            int[] result = s.sortbyFreq(nums);
            printArray(result);
        }
        sc.close();
    }
}



## C

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// user code comes here


void printArray(int* arr, int n) {
    for (int i = 0; i < n; i++)
        printf("%d%s", arr[i], (i == n - 1 ? "" : " "));
    printf("\n");
}

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        int* vals = (int*)malloc(n * sizeof(int));
        for (int i = 0; i < n; i++) scanf("%d", &vals[i]);
        int* result = sortbyFreq(vals, n);
        printArray(result, n);
        free(vals);
    }
    return 0;
}



## JAVASCRIPT

// user code comes here


function printArray(arr) {
    console.log(arr.join(" "));
}

function main() {
    const fs = require("fs");
    const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);
    let idx = 0;
    const t = parseInt(input[idx++]);
    for (let tc = 0; tc < t; tc++) {
        const n = parseInt(input[idx++]);
        const vals = [];
        for (let i = 0; i < n; i++) vals.push(Number(input[idx++]));
        const result = sortbyFreq(vals);
        printArray(result);
    }
}

main();



## PYTHON

from collections import Counter
import sys

# user code comes here


def print_array(arr):
    print(" ".join(map(str, arr)))


def main():
    try:
        t_cases = int(sys.stdin.readline())
        for _ in range(t_cases):
            n = int(sys.stdin.readline())
            vals = list(map(int, sys.stdin.readline().split()))
            result = sort_by_freq(vals)
            print_array(result)
    except EOFError:
        pass


if __name__ == "__main__":
    main()
