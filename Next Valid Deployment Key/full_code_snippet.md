## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        string s, target;
        cin >> s;
        cin >> target;
        cout << nextValidDeploymentKey(s, target) << "\n";
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
            String target = sc.next();
            System.out.println(nextValidDeploymentKey(s, target));
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
        char s[305], target[305];
        scanf("%s", s);
        scanf("%s", target);
        printf("%s\n", nextValidDeploymentKey(s, target));
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
    const target = input[idx++];
    console.log(nextValidDeploymentKey(s, target));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        s = input().strip()
        target = input().strip()
        print(nextValidDeploymentKey(s, target))
        # evaluation completed

if __name__ == "__main__":
    main()
