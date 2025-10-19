## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, m;
        cin >> n;
        vector<int> nums1(n);
        for (int i = 0; i < n; i++) {
            cin >> nums1[i];
        }
        cin >> m;
        vector<int> nums2(m);
        for (int i = 0; i < m; i++) {
            cin >> nums2[i];
        }
        vector<int> result = mergeLoot(nums1, nums2);
        for (int val : result) cout << val << " ";
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
            int[] nums1 = new int[n];
            for (int i = 0; i < n; i++) {
                nums1[i] = sc.nextInt();
            }
            int m = sc.nextInt();
            int[] nums2 = new int[m];
            for (int i = 0; i < m; i++) {
                nums2[i] = sc.nextInt();
            }
            int[] result = mergeLoot(nums1, nums2);
            for (int val : result) System.out.print(val + " ");
            System.out.println();
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
        int n, m;
        scanf("%d", &n);
        int nums1[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &nums1[i]);
        }
        scanf("%d", &m);
        int nums2[m];
        for (int i = 0; i < m; i++) {
            scanf("%d", &nums2[i]);
        }
        int size;
        int* result = mergeLoot(nums1, n, nums2, m, &size);
        for (int i = 0; i < size; i++) printf("%d ", result[i]);
        printf("\n");
        free(result);
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
        const nums1 = input.slice(idx, idx + n).map(Number);
        idx += n;
        const m = parseInt(input[idx++]);
        const nums2 = input.slice(idx, idx + m).map(Number);
        const result = mergeLoot(nums1, nums2);
        console.log(result.join(" "));
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
        m = int(input())
        nums2 = list(map(int, input().split()))
        result = mergeLoot(nums1, nums2)
        print(*result)
        # evaluation completed

if __name__ == "__main__":
    main()
