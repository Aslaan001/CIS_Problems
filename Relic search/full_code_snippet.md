## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int n;
    cin >> n;
    vector<int> relics(n);
    for (int i = 0; i < n; i++) {
        cin >> relics[i];
    }
    int key;
    cin >> key;
    cout << relicSearch(relics, key);
    return 0;
}


## JAVA

import java.util.*;

public class Main {
    // user code comes here
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] relics = new int[n];
        for (int i = 0; i < n; i++) {
            relics[i] = sc.nextInt();
        }
        int key = sc.nextInt();
        System.out.print(relicSearch(relics, key));
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
    int relics[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &relics[i]);
    }
    int key;
    scanf("%d", &key);
    printf("%d", relicSearch(relics, n, key));
    return 0;
}

## JAVASCRIPT

// user code comes here

function main() {
  const fs = require("fs");
  const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);

  const n = parseInt(input[0]);
  const relics = input.slice(1, n + 1).map(Number);
  const key = parseInt(input[n + 1]);

  console.log(relicSearch(relics, key));
}

main();


## PYTHON

import collections

# user code comes here

def main():
    n = int(input())
    relics = list(map(int, input().split()))
    key = int(input())
    print(relicSearch(relics, key))

if __name__ == "__main__":
    main()