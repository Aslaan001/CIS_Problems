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
        vector<int> stars(n);
        for (int i = 0; i < n; i++) {
            cin >> stars[i];
        }
        cout << absMaxMinDiff(stars) << "\n";
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
            int[] stars = new int[n];
            for (int i = 0; i < n; i++) {
                stars[i] = sc.nextInt();
            }
            System.out.println(absMaxMinDiff(stars));
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
        int stars[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &stars[i]);
        }
        printf("%d\n", absMaxMinDiff(stars, n));
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
    const stars = [];
    for (let i = 0; i < n; i++) stars.push(Number(input[idx++]));
    console.log(absMaxMinDiff(stars));
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
        stars = list(map(int, input().split()))
        print(absMaxMinDiff(stars))
        # evaluation completed

if __name__ == "__main__":
    main()
