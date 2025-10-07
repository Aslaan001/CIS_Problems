## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int n;
    cin >> n;
    vector<char> letters(n);
    for (int i = 0; i < n; i++) {
        cin >> letters[i];
    }
    char target;
    cin >> target;
    cout << nextRune(letters, target);
    return 0;
}


## JAVA

import java.util.*;

public class Main {
    // user code comes here
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        char[] letters = new char[n];
        for (int i = 0; i < n; i++) {
            letters[i] = sc.next().charAt(0);
        }
        char target = sc.next().charAt(0);
        System.out.print(nextRune(letters, target));
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
    char letters[n];
    for (int i = 0; i < n; i++) {
        scanf(" %c", &letters[i]);
    }
    char target;
    scanf(" %c", &target);
    printf("%c", nextRune(n,letters,target));
    return 0;
}

## JAVASCRIPT

// user code comes here

function main() {
  const fs = require("fs");
  const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);

  const n = parseInt(input[0]);
  const letters = input.slice(1, n + 1);
  const target = input[n + 1];

  console.log(nextRune(letters, target));
}

main();


## PYTHON

import collections

# user code comes here

def main():
    n = int(input())
    letters = input().split()
    target = input().strip()
    print(nextRune(letters, target))

if __name__ == "__main__":
    main()
