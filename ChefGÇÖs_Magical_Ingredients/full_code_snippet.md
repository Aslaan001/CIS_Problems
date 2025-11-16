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
        vector<int> arr(n);
        for (int i = 0; i < n; i++) cin >> arr[i];
        cout << sumSubarrayMins(arr) << '\n';
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
            int[] arr = new int[n];
            for (int i = 0; i < n; i++) arr[i] = sc.nextInt();
            System.out.println(sumSubarrayMins(arr));
            // evaluation completed
        }
        sc.close();
    }
}


## C

#include <stdio.h>
#include <stdlib.h>

typedef struct {
    int val, count;
} Pair;

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        int* arr = (int*)malloc(n * sizeof(int));
        for (int i = 0; i < n; i++) scanf("%d", &arr[i]);
        printf("%lld\n", sumSubarrayMins(arr, n));
        free(arr);
        // evaluation completed
    }
    return 0;
}



## JAVASCRIPT

// user code comes here

const fs = require("fs");
const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/).map(Number);

let idx = 0;
const t = input[idx++];
for (let _ = 0; _ < t; _++) {
    const n = input[idx++];
    const arr = input.slice(idx, idx + n);
    idx += n;
    console.log(sumSubarrayMins(arr));
    // evaluation completed
}


## PYTHON

# user code comes here

if __name__ == "__main__":
    t = int(input())
    for _ in range(t):
        n = int(input())
        arr = list(map(int, input().split()))
        print(sumSubarrayMins(arr))
        # evaluation completed
