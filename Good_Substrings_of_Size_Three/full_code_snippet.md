## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int n;
    cin >> n;
    string s;
    cin >> s;
    cout << goodSubstrings(s);
    return 0;
}

## JAVA

import java.util.*;

public class Main {
    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        String s = sc.next();
        System.out.print(goodSubstrings(s));
        sc.close();
    }
}

## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here

int main() {
    int n;
    scanf("%d", &n);
    char s[n+1];
    scanf("%s", s);
    printf("%d", goodSubstrings(s));
    return 0;
}

## JAVASCRIPT

// user code comes here

function main() {
  const fs = require("fs");
  const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);

  const n = parseInt(input[0]);
  const s = input[1];

  console.log(goodSubstrings(s));
}

main();

## PYTHON

# user code comes here

def main():
    n = int(input())
    s = input().strip()
    print(goodSubstrings(s))

if __name__ == "__main__":
    main()
