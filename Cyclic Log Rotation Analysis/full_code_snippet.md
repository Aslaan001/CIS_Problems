## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        string s, tstr;
        long long k;
        cin >> s;
        cin >> tstr;
        cin >> k;
        cout << stringTransformation(s, tstr, k) << "\n";
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
            String tstr = sc.next();
            long k = sc.nextLong();
            System.out.println(stringTransformation(s, tstr, k));
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
        char s[500005], tstr[500005];
        long long k;
        scanf("%s", s);
        scanf("%s", tstr);
        scanf("%lld", &k);
        printf("%d\n", stringTransformation(s, tstr, k));
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
    const tstr = input[idx++];
    const k = BigInt(input[idx++]);
    console.log(stringTransformation(s, tstr, k));
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
        tstr = input().strip()
        k = int(input())
        print(stringTransformation(s, tstr, k))
        # evaluation completed

if __name__ == "__main__":
    main()
