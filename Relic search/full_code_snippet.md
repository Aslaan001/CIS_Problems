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
        vector<int> relics(n);
        for (int i = 0; i < n; i++) {
            cin >> relics[i];
        }
        int key;
        cin >> key;
        cout << relicSearch(relics, key) << "\n";
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
            int[] relics = new int[n];
            for (int i = 0; i < n; i++) {
                relics[i] = sc.nextInt();
            }
            int key = sc.nextInt();
            System.out.println(relicSearch(relics, key));
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
        int relics[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &relics[i]);
        }
        int key;
        scanf("%d", &key);
        printf("%d\n", relicSearch(relics, n, key));
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
    const relics = input.slice(idx, idx + n).map(Number);
    idx += n;
    const key = parseInt(input[idx++]);
    console.log(relicSearch(relics, key));
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
        relics = list(map(int, input().split()))
        key = int(input())
        print(relicSearch(relics, key))
        # evaluation completed

if __name__ == "__main__":
    main()
