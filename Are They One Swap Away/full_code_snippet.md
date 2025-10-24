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
        string s1, s2;
        cin >> s1 >> s2;
        cout << areOneSwapAway(s1, s2) << "\n";
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
            String s1 = sc.next();
            String s2 = sc.next();
            System.out.println(areOneSwapAway(s1, s2));
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
        char s1[n + 1], s2[n + 1];
        scanf("%s %s", s1, s2);
        printf("%s\n", areOneSwapAway(s1, s2));
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
    const s1 = input[idx++];
    const s2 = input[idx++];
    console.log(areOneSwapAway(s1, s2));
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
        s1 = input().strip()
        s2 = input().strip()
        print(are_one_swap_away(s1, s2))
        #  evaluation completed

if __name__ == "__main__":
    main()
