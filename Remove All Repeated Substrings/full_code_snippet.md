## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        string s, p;
        cin >> s >> p;
        cout << removeSubstring(s, p) << "\n";
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
            String p = sc.next();
            System.out.println(removeSubstring(s, p));
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
        char s[2005], p[2005];
        scanf("%s %s", s, p);
        char out[2005];
        removeSubstring(s, p, out);
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

  for (let _ = 0; _ < t; _++) {
    const s = input[idx++];
    const p = input[idx++];
    console.log(removeSubstring(s, p));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        s, p = input().split()
        print(removeSubstring(s, p))
        #  evaluation completed

if __name__ == "__main__":
    main()
