## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int n;
    cin >> n;
    vector<int> cookies(n);
    for (int i = 0; i < n; i++) {
        cin >> cookies[i];
    }
    int h;
    cin >> h;
    cout << minCollectionSpeed(cookies, h);
    return 0;
}


## JAVA

import java.util.*;

public class Main {
    // user code comes here
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] cookies = new int[n];
        for (int i = 0; i < n; i++) {
            cookies[i] = sc.nextInt();
        }
        int h = sc.nextInt();
        System.out.print(minCollectionSpeed(cookies, h));
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
    int cookies[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &cookies[i]);
    }
    int h;
    scanf("%d", &h);
    printf("%d", minCollectionSpeed(cookies, n, h));
    return 0;
}

## JAVASCRIPT

// user code comes here

function main() {
  const fs = require("fs");
  const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);

  const n = parseInt(input[0]);
  const cookies = input.slice(1, n + 1).map(Number);
  const h = parseInt(input[n + 1]);

  console.log(minCollectionSpeed(cookies, h));
}

main();


## PYTHON

import collections

# user code comes here

def main():
    n = int(input())
    cookies = list(map(int, input().split()))
    h = int(input())
    print(minCollectionSpeed(cookies, h))

if __name__ == "__main__":
    main()