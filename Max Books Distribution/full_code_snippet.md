## CPP

#include <bits/stdc++.h>
using namespace std;

// User function to implement


int main() {
    int t;
    cin >> t;

    while (t--) {
        int n, m;
        cin >> n;
        vector<int> books(n);
        for (int i = 0; i < n; i++) {
            cin >> books[i];
        }
        cin >> m;
        cout << maxBooksDistribution(books, m) << "\n";
        // evaluation completed
    }
    return 0;
}

## JAVA

import java.util.*;

public class Main {
    // User function to implement
   

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] books = new int[n];
            for (int i = 0; i < n; i++) books[i] = sc.nextInt();
            int m = sc.nextInt();
            System.out.println(maxBooksDistribution(books, m));
            // evaluation completed
        }
        sc.close();
    }
}

## C

#include <stdio.h>
#include <stdlib.h>

// User function to implement


int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n, m;
        scanf("%d", &n);
        int books[n];
        for (int i = 0; i < n; i++) scanf("%d", &books[i]);
        scanf("%d", &m);
        printf("%d\n", maxBooksDistribution(books, n, m));
        // evaluation completed
    }
    return 0;
}

## JAVASCRIPT

// User function to implement


function main() {
    const fs = require("fs");
    const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);
    let idx = 0;

    const t = parseInt(input[idx++]);
    for (let tc = 0; tc < t; tc++) {
        const n = parseInt(input[idx++]);
        const books = [];
        for (let i = 0; i < n; i++) books.push(Number(input[idx++]));
        const m = parseInt(input[idx++]);
        console.log(maxBooksDistribution(books, m));
        // evaluation completed
    }
}

main();

## PYTHON

# User function to implement


def main():
    t = int(input())
    for _ in range(t):
        n = int(input())
        books = list(map(int, input().split()))
        m = int(input())
        print(maxBooksDistribution(books, m))
        # evaluation completed

if __name__ == "__main__":
    main()
