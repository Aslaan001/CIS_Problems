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
        vector<int> cookies(n);
        for (int i = 0; i < n; i++) {
            cin >> cookies[i];
        }
        int h;
        cin >> h;
        cout << minCollectionSpeed(cookies, h) << "\n";
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
            int[] cookies = new int[n];
            for (int i = 0; i < n; i++) {
                cookies[i] = sc.nextInt();
            }
            int h = sc.nextInt();
            System.out.println(minCollectionSpeed(cookies, h));
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
        int cookies[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &cookies[i]);
        }
        int h;
        scanf("%d", &h);
        printf("%d\n", minCollectionSpeed(cookies, n, h));
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
    const cookies = input.slice(idx, idx + n).map(Number);
    idx += n;
    const h = parseInt(input[idx++]);
    console.log(minCollectionSpeed(cookies, h));
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
        cookies = list(map(int, input().split()))
        h = int(input())
        print(minCollectionSpeed(cookies, h))
        # evaluation completed

if __name__ == "__main__":
    main()
