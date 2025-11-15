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
        vector<int> vals(n);
        for (int i = 0; i < n; i++) {
            cin >> vals[i];
        }

        cout << countValidMilitaryTrios(vals) << "\n";
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
            int[] vals = new int[n];
            for (int i = 0; i < n; i++) {
                vals[i] = sc.nextInt();
            }

            System.out.println(countValidMilitaryTrios(vals));
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
        int vals[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &vals[i]);
        }

        printf("%d\n", countValidMilitaryTrios(vals, n));
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
    const vals = [];
    for (let i = 0; i < n; i++) vals.push(Number(input[idx++]));

    console.log(countValidMilitaryTrios(vals));
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
        vals = list(map(int, input().split()))
        print(count_valid_military_trios(vals))
        # evaluation completed

if __name__ == "__main__":
    main()
