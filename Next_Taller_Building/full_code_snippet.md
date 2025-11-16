## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n1, n2;
        cin >> n1;
        vector<int> nums1(n1);
        for (int i = 0; i < n1; i++) cin >> nums1[i];

        cin >> n2;
        vector<int> nums2(n2);
        for (int i = 0; i < n2; i++) cin >> nums2[i];

        vector<int> ans = nextGreaterElement(nums1, nums2);
        for (int x : ans) cout << x << " ";
        cout << endl;
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
            int n1 = sc.nextInt();
            int[] nums1 = new int[n1];
            for (int i = 0; i < n1; i++) nums1[i] = sc.nextInt();

            int n2 = sc.nextInt();
            int[] nums2 = new int[n2];
            for (int i = 0; i < n2; i++) nums2[i] = sc.nextInt();

            int[] ans = nextGreaterElement(nums1, nums2);
            for (int x : ans) System.out.print(x + " ");
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
        int n1, n2;
        scanf("%d", &n1);
        int nums1[n1];
        for (int i = 0; i < n1; i++) scanf("%d", &nums1[i]);

        scanf("%d", &n2);
        int nums2[n2];
        for (int i = 0; i < n2; i++) scanf("%d", &nums2[i]);

        int* ans = nextGreaterElement(nums1, n1, nums2, n2);
        for (int i = 0; i < n1; i++) printf("%d ", ans[i]);
        printf("\n");
        free(ans);
        // evaluation completed
    }
    return 0;
}



## JAVASCRIPT

// user code comes here

const readline = require("readline");
const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

let input = [];
rl.on("line", (line) => input.push(line.trim()))
  .on("close", () => {
    let idx = 0;
    const t = parseInt(input[idx++]);
    for (let _ = 0; _ < t; _++) {
        const n1 = parseInt(input[idx++]);
        const nums1 = input[idx++].split(" ").map(Number);
        const n2 = parseInt(input[idx++]);
        const nums2 = input[idx++].split(" ").map(Number);

        let ans = nextGreaterElement(nums1, nums2);
        console.log(ans.join(" "));
        // evaluation completed
    }
  });



## PYTHON

# user code comes here

if __name__ == "__main__":
    t = int(input())
    for _ in range(t):
        n1 = int(input().strip())
        nums1 = list(map(int, input().split()))
        n2 = int(input().strip())
        nums2 = list(map(int, input().split()))

        ans = nextGreaterElement(nums1, nums2)
        print(" ".join(map(str, ans)))
        # evaluation completed
