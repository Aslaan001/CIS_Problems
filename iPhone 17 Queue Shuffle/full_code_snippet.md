## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, k;
        cin >> n;
        queue<int> q;
        for (int i = 0; i < n; i++) {
            int x; cin >> x;
            q.push(x);
        }
        cin >> k;

        queue<int> res = reverseLastK(q, k);
        while (!res.empty()) {
            cout << res.front() << " ";
            res.pop();
        }
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
            Queue<Integer> q = new LinkedList<>();
            for (int i = 0; i < n; i++) q.add(sc.nextInt());
            int k = sc.nextInt();

            Queue<Integer> res = reverseLastK(q, k);
            for (int x : res) System.out.print(x + " ");
            System.out.println();
            // evaluation completed
        }
    }
}


## C

#include <stdio.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n, k;
        scanf("%d", &n);
        int q[n];
        for (int i = 0; i < n; i++) scanf("%d", &q[i]);
        scanf("%d", &k);

        reverseLastK(q, n, k);

        for (int i = 0; i < n; i++) printf("%d ", q[i]);
        printf("\n");
        // evaluation completed
    }
    return 0;
}


## JAVASCRIPT

// user code comes here

const fs = require("fs");
const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/).map(Number);

let idx = 0;
let t = input[idx++];

while (t--) {
    let n = input[idx++];
    let q = input.slice(idx, idx + n);
    idx += n;
    let k = input[idx++];

    let result = reverseLastK(q, k);
    console.log(result.join(" "));
    // evaluation completed
}


## PYTHON

import collections
from collections import deque

# user code comes here

t = int(input())
for _ in range(t):
    n = int(input())
    q = deque(map(int, input().split()))
    k = int(input())

    res = reverse_last_k(q, k)
    print(*res)
    # evaluation completed
