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
        vector<char> letters(n);
        for (int i = 0; i < n; i++) {
            cin >> letters[i];
        }
        char target;
        cin >> target;
        cout << nextRune(letters, target) << "\n";
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
            char[] letters = new char[n];
            for (int i = 0; i < n; i++) {
                letters[i] = sc.next().charAt(0);
            }
            char target = sc.next().charAt(0);
            System.out.println(nextRune(letters, target));
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
        int n;
        scanf("%d", &n);
        char letters[n];
        for (int i = 0; i < n; i++) {
            scanf(" %c", &letters[i]);
        }
        char target;
        scanf(" %c", &target);
        printf("%c\n", nextRune(n, letters, target));
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
    const letters = input.slice(idx, idx + n);
    idx += n;
    const target = input[idx++];
    console.log(nextRune(letters, target));
    // evaluation completed
  }
}

main();


## PYTHON

import collections

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        n = int(input())
        letters = input().split()
        target = input().strip()
        print(nextRune(letters, target))
        # evaluation completed

if __name__ == "__main__":
    main()
