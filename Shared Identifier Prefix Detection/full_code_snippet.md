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
        vector<string> strs(n);
        for (int i = 0; i < n; i++) {
            cin >> strs[i];
        }
        cout << longestCommonPrefix(strs) << "\n";
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
            String[] strs = new String[n];
            for (int i = 0; i < n; i++) {
                strs[i] = sc.next();
            }
            System.out.println(longestCommonPrefix(strs));
            // evaluation completed
        }
        sc.close();
    }
}


## C

#include <stdio.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        char strs[n][205];
        for (int i = 0; i < n; i++) {
            scanf("%s", strs[i]);
        }
        printf("%s\n", longestCommonPrefix(strs, n));
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
  for (let tc = 0; tc < t; tc++) {
    const n = parseInt(input[idx++]);
    const strs = [];
    for (let i = 0; i < n; i++) strs.push(input[idx++]);
    console.log(longestCommonPrefix(strs));
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
        strs = [input().strip() for _ in range(n)]
        print(longest_common_prefix(strs))
        # evaluation completed

if __name__ == "__main__":
    main()
