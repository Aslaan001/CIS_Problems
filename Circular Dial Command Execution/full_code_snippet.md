## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        string ring, key;
        cin >> ring;
        cin >> key;
        cout << minStepsFreedomTrail(ring, key) << "\n";
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
            String ring = sc.next();
            String key = sc.next();
            System.out.println(minStepsFreedomTrail(ring, key));
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
        char ring[105], key[105];
        scanf("%s", ring);
        scanf("%s", key);
        printf("%d\n", minStepsFreedomTrail(ring, key));
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
    const ring = input[idx++];
    const key = input[idx++];
    console.log(minStepsFreedomTrail(ring, key));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        ring = input().strip()
        key = input().strip()
        print(minStepsFreedomTrail(ring, key))
        # evaluation completed

if __name__ == "__main__":
    main()
