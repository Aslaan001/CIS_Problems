## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        string s1, s2;
        long long n1, n2;
        cin >> s1;
        cin >> n1;
        cin >> s2;
        cin >> n2;
        cout << countTheRepetitions(s1, n1, s2, n2) << "\n";
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
            String s1 = sc.next();
            long n1 = sc.nextLong();
            String s2 = sc.next();
            long n2 = sc.nextLong();
            System.out.println(countTheRepetitions(s1, n1, s2, n2));
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
        char s1[105], s2[105];
        long long n1, n2;
        scanf("%s", s1);
        scanf("%lld", &n1);
        scanf("%s", s2);
        scanf("%lld", &n2);
        printf("%d\n", countTheRepetitions(s1, n1, s2, n2));
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
    const s1 = input[idx++];
    const n1 = BigInt(input[idx++]);
    const s2 = input[idx++];
    const n2 = BigInt(input[idx++]);
    console.log(countTheRepetitions(s1, n1, s2, n2));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        s1 = input().strip()
        n1 = int(input())
        s2 = input().strip()
        n2 = int(input())
        print(countTheRepetitions(s1, n1, s2, n2))
        # evaluation completed

if __name__ == "__main__":
    main()
