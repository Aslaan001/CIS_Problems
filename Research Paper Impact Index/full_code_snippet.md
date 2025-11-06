## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here


int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    int t;
    if (!(cin >> t)) return 0;
    while (t--) {
        int n;
        cin >> n;
        vector<int> citations(n);
        for (int i = 0; i < n; i++) cin >> citations[i];
        int result = hIndex(citations);
        cout << result << "\n";
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
            int[] citations = new int[n];
            for (int i = 0; i < n; i++) citations[i] = sc.nextInt();
            System.out.println(hIndex(citations)); 
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
    if (scanf("%d", &t) != 1) return 0;
    while (t--) {
        int n;
        scanf("%d", &n);
        int* citations = (int*)malloc(n * sizeof(int));
        for (int i = 0; i < n; ++i) scanf("%d", &citations[i]);
        int result = hIndex(citations, n);
        printf("%d\n", result);
        free(citations);
    }
    return 0;
}



## JAVASCRIPT

// user code comes here


function main() {
    const fs = require("fs");
    const data = fs.readFileSync(0, "utf8").trim().split(/\s+/).map(Number);
    let idx = 0;
    const t = data[idx++];
    for (let tc = 0; tc < t; tc++) {
        const n = data[idx++];
        const citations = data.slice(idx, idx + n);
        idx += n;
        console.log(hIndex(citations));
    }
}

main();



## PYTHON

import sys

# user code comes here


def main():
    data = sys.stdin.read().strip().split()
    if not data:
        return
    it = iter(map(int, data))
    t = next(it)
    for _ in range(t):
        n = next(it)
        citations = [next(it) for _ in range(n)]
        print(h_index(citations))

if __name__ == "__main__":
    main()
