## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        string s;
        int k;
        cin >> s >> k;
        cout << minimizeNumber(s, k) << "\n";
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
            String s = sc.next();
            int k = sc.nextInt();
            System.out.println(minimizeNumber(s, k));
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
        char s[100005];
        int k;
        scanf("%s %d", s, &k);
        char out[100005];
        minimizeNumber(s, k, out);
        printf("%s\n", out);
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
    const s = input[idx++];
    const k = parseInt(input[idx++]);
    console.log(minimizeNumber(s, k));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        s, k = input().split()
        k = int(k)
        print(minimizeNumber(s, k))
        # evaluation completed

if __name__ == "__main__":
    main()
