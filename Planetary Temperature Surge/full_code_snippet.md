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
        vector<int> temperatures(n);
        for (int i = 0; i < n; i++) cin >> temperatures[i];

        vector<int> result = nextHigherTemperatures(temperatures);
        for (int temp : result) cout << temp << " ";
        cout << "\n";
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
            int[] temperatures = new int[n];
            for (int i = 0; i < n; i++) temperatures[i] = sc.nextInt();

            int[] result = nextHigherTemperatures(temperatures);
            for (int temp : result) System.out.print(temp + " ");
            System.out.println();
            // evaluation completed
        }
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
        int temperatures[n];
        for (int i = 0; i < n; i++) scanf("%d", &temperatures[i]);

        int size;
        int* result = nextHigherTemperatures(temperatures, n, &size);
        for (int i = 0; i < size; i++) printf("%d ", result[i]);
        printf("\n");
        free(result);
        // evaluation completed
    }
    return 0;
}




## JAVASCRIPT


// user code comes here

const fs = require('fs');
const tokens = fs.readFileSync(0, 'utf8').trim().split(/\s+/);
if (tokens.length === 0 || tokens[0] === '') {
  console.log('');
  process.exit(0);
}

let ptr = 0;
const t = parseInt(tokens[ptr++], 10);

for (let _ = 0; _ < t; _++) {
  const n = parseInt(tokens[ptr++], 10);
  const temperatures = new Array(n);
  for (let i = 0; i < n; i++) temperatures[i] = parseInt(tokens[ptr++], 10);

  const result = nextHigherTemperatures(temperatures);
  console.log(result.join(' '));
  // evaluation completed
}




## PYTHON

# user code comes here

import sys

data = sys.stdin.buffer.read().split()
if not data:
    print()
    sys.exit(0)

it = iter(data)
t = int(next(it))
for _ in range(t):
    n = int(next(it))
    temperatures = [int(next(it)) for _ in range(n)]

    result = nextHigherTemperatures(temperatures)
    print(' '.join(map(str, result)))
    # evaluation completed

