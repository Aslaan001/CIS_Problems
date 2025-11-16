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
        vector<int> dailyTemperatures(n);
        for (int i = 0; i < n; i++) cin >> dailyTemperatures[i];

        vector<int> result = predictHeatwaveDays(dailyTemperatures);
        for (int x : result) cout << x << " ";
        cout << endl;
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
            int[] dailyTemperatures = new int[n];
            for (int i = 0; i < n; i++) dailyTemperatures[i] = sc.nextInt();

            int[] result = predictHeatwaveDays(dailyTemperatures);
            for (int x : result) System.out.print(x + " ");
            System.out.println();
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
        int* dailyTemperatures = (int*)malloc(n * sizeof(int));
        for (int i = 0; i < n; i++) scanf("%d", &dailyTemperatures[i]);

        int returnSize;
        int* result = predictHeatwaveDays(dailyTemperatures, n, &returnSize);
        for (int i = 0; i < returnSize; i++) printf("%d ", result[i]);
        printf("\n");
        // evaluation completed

        free(dailyTemperatures);
        free(result);
    }
    return 0;
}




## JAVASCRIPT


const readline = require('readline');

// user code comes here

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let inputLines = [];
rl.on('line', line => inputLines.push(line))
  .on('close', () => {
      let t = parseInt(inputLines[0]);
      let index = 1;
      while (t--) {
          const n = parseInt(inputLines[index++]);
          const dailyTemperatures = inputLines[index++].split(' ').map(Number);
          const result = predictHeatwaveDays(dailyTemperatures);
          console.log(result.join(' '));
          // evaluation completed
      }
  });





## PYTHON

from typing import List

# user code comes here

t = int(input())
for _ in range(t):
    n = int(input())
    dailyTemperatures = list(map(int, input().split()))
    result = predictHeatwaveDays(dailyTemperatures)
    print(*result)
    # evaluation completed
